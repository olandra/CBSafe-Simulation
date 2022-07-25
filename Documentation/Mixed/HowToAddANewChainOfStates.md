# How to add a new chain of states

[README](../../README.md) / [Documentation](../Documentation.md)

---

## Table of Content

1. [Design](#1.-design)
2. [Add the event call](#2.-add-the-event-call)
3. [Adding the event to the event listener](#3.-adding-the-event-to-the-event-listener)
4. [Adding a state machine](#4.-adding-a-state-machine)
5. [Adding the states](#5.-adding-the-states)
	- [Base State class](#base-state-class)
	- [Adding your state](#adding-your-state)
	- [The chain of events (states)](#the-chain-of-events-(states))
	- [The flow of actions](#the-flow-of-actions)

---

## 1. Design

- List all the details you know about the chain of events. Don't forget to include tools and co-operation with others
- Think about what's the required information for the AI to get the job done
	- E.g. Extinguishing fires would require
		- The team who does it
		- The area where the fires are
		- A command to let them know their task
		- If the fire needs something else than water (note: don't need to know if water is enough)
- List what the NPCs should do automatically without instructions from the player. These include things like:
	- Where to find their tools
	- How to use their tools
	- How to move to the tools, partner, target

## 2. Add the event call

The event call should follow the instructions at [Raising an Event](../Event/RaisingAnEvent.md). Remember to add the event call options to the documentation.

## 3. Adding the event to the event listener

There are different event listeners for different tasks. The most common one is the event listener in  [AIUnitInfo.cs](../AIUnitInfo/AIUnitInfo.md) which responds to the orders given to the teams by the player. Please refer to it's documentation for more information.

## 4. Adding a state machine

[Wikipedia: Finite-state machine](https://en.wikipedia.org/wiki/Finite-state_machine)
[Wikipedia: Automata-based programming](https://en.wikipedia.org/wiki/Automata-based_programming)

This simulation uses a very simple, yet extremely flexible, finite-state machine to represent the AI of the NPCs. A finite-state machine was chosen for the simplicity of creating instructed patterns which can be defined by a common goal. It also allows individual patterns based on the same goal by defining different roles. By adding status representation, it's possible to synchronize the state machines and let the state machines communicate with each other.

A lot of possibilities and small things for a "very simple" concept, right?

Right. The finite-state machine implementation at it's bare form consists of three things:

- A state machine
- A base state class
- Derived state classes

The base structure is also very simple. The base state class defines three stages: ENTER, UPDATE and EXIT. The base state class also implements a Process() method which uses the stages to move through those three phases. The state machine sets up the variables for the state classes and runs the base state class' Process() method.

There's not much to it, really...When looking just the bare core of the system. What brings the flexibility and versatility, is the possibility of adding and chaining states derived from the base state class.

But first, the state machine implementation. The state machine sets up two base variables for the state classes:

- agent: The NavMeshAgent component of the NPC
- anim: The Animator component of the NPC's mesh

It also provides two variables and their properties:

- Target: A Vector3 position to be used as a target for moving and actions
- TargetObject: A GameObject representation of the target. This can be used to distinquish moving from other targets

After setting the forementioned variables, the initial state is called by creating a new instance of the class. And lastly, the state machine moves to MonoBehaviour.Update() loop and repeatedly runs the Process() method of the related state class.

```
using UnityEngine;
using UnityEngine.AI;

namespace CBSafe.Simulation.AI
{
    public class BasicStateMachine : MonoBehaviour
    {
        NavMeshAgent agent;
        Animator anim;
        State currentState;

        private Vector3 target = Vector3.zero;
        private GameObject targetObject = null;
        public Animator Anim { get => anim; set => anim = value; }

        public Vector3 Target
        {
            get { return target; }
            set {
                NavMesh.SamplePosition(value, out NavMeshHit hit, 5.0f, NavMesh.AllAreas);
                target = hit.position;
            }
        }
        public GameObject TargetObject { get => targetObject; set => targetObject = value; }

        void Start()
        {
            agent = GetComponent<NavMeshAgent>();
            anim = GetComponent<Animator>();
            
            currentState = new InitialStateClass(gameObject, agent, anim);
        }

        void Update()
        {
            currentState = currentState.Process();
        }
    }
}
```

## 5. Adding the states

Now it's time to see how good your design is. If you created your three lists well, you should see the states you need from the lists. However, if you didn't plan so carefully, you might need to spend some extra time with this phase.

First thing is to realize that the states this far all start from the corresponding Idle state. The Idle state sets the target for the first step on the chain and passes the control to Walk/Drive state. The Walk/Drive state makes sure the NPC gets to the initial location for the chain to begin from.

For the Idle and Walk/Drive states, you'll need to add conditions based on the new TASK and METHOD you're adding. The check for new order relies on these two enums, so be sure to use them or prepare to rewrite the check.

When the exit condition (NPC arriving to the starting location) is met in the Walk/Drive state, you can move to your new state by setting the `nextState` to a `new <yourstateclass>(npc, agent, anim)` and setting the `stage = EVENT.EXIT;`

Wait, what is that `<yourstateclass()`? It's a class we need to make. More specifically, it's a class that represents one state.

### Base State class

A state class has a basic definition in the `State.cs` and it's derived to each group of NPCs via a group parent class (e.g. FirefighterState). The base state defines the structure for three stage event driven states.

**Constructor** sets the common values for the states. These include the npc (GameObject), agent (NavMeshAgent) and anim (Animator). The constructor also sets the initial stage to be `EVENT.ENTER` and creates a reference to the common config objects.

**Enter()** This method defines what happens when the state is entered. The code here runs only once before moving on to the next phase.

**Update()** This method defines what happens during the state and which are the exit conditions for moving to another state. It's the event loop of the state, so it runs in a loop until an exit condition is met.

**Exit()** This method is run when an exit condition is met, before moving on to the next state.

**Process()** The very base for the state machine. This method is responsible of updating the phase inside a state. The EVENT enum is used to move through the Process() method until reaching the end of the state.

### Adding your state

As said earlier, a state should derive from a group state class. A group state class should define three things:

- stateMachine: This is the state machine that runs the state group. It's main responsibility is to set up the npc, agent and anim, call the initial state and run the Process() method on update
- aiUnitInfo: The unit's event listener which contains the information the unit needs to function
- enum STATE: This is a container which lists all states to identify them from each other

It's possible that the group state class already exists for you, so just add in the STATE identifier for your new state.

The new state itself is where you should define the behaviour of your state. You should do four things in the state. Write it's constructor and overrides for Enter(), Update() and Exit(). The template for the state could look like this:

```
using UnityEngine;
using UnityEngine.AI;

// Note: The AI has been written inside a namespace
namespace CBSafe.Simulation.AI
{
    public class FirefighterCustomState : FirefighterState
    {
        public FirefighterCustomState(GameObject _npc, NavMeshAgent _agent, Animator _anim)
            : base(_npc, _agent, _anim)
        {
            name = STATE.CUSTOM;
        }

        public override void Enter()
        {
	        // The logging of the team, npc's parent, npc and state helps debugging and should always be called first on Enter()
            Debug.Log(aiUnitInfo.Leader + " " + npc.transform.parent.name + " " + npc.name + " " + "Firefighter Custom State");

			// Your state initialization here

            base.Enter();
        }

        public override void Update()
        {
			// Note: You shouldn't call base.Update()

			// What the state does and it's exit conditions here
        }

        public override void Exit()
        {
	        // Cleanup and next state preparations here
	       
            base.Exit();
        }
    }
}
```

### The chain of events (states)

The idea is not to write random states, but to use the states as building blocks to create chains of events. A single state should be used for a single responsibility for clarity, but it doesn't mean that a state should be a simple few line script. Take a look into `FirefighterIdle.cs`, for example. It serves a single responsibility of initializing the next state of events and usually does this via `FirefighterWalk.cs`.

A state can have as many exits as you need, but don't make one state handle several responsibilities. For example, you should not combine Idle with Walk. Even though the Idle could move and exit only when the npc has reached it's destination.

To make things harder to understand, it should be noted that the Idle already has a hidden second responsibility which comes by design. While the Idle state seemingly initializes a chain of events, it also keeps the npcs in place, waiting. This hidden responsibility is the reason why the chains of events always return to this specific state. It's also natural for us humans to understand this flow where we stop when getting a new task. We might not stop walking, but we do stop to think.

This brings us to the final step of adding new states

### The flow of actions

When designing and adding your new states and creating chains of events with them, remember to consider the flow of actions. This helps you to define the exit conditions for each state. Each state doesn't have to have an exit to Idle, for example.

To clarify, as you wouldn't just drop your phone after a call, your states shouldn't either. The follow up would normally be to end the call and then lower the phone and place it on the table or in your pocket. The states should follow a normal flow like this to create the illusion of reality.

Another example would be that the surface rescue chain in the simulation doesn't just leave the rescuable  when a new order is given. They do bring the rescuable to the shore first.

A better example of forking the chains would be the surface rescue chains with the raft. If a rescue task with a raft is given and then changed to search task before the unit has reached the rescuable, they have an additional condition to meet. The search task requires diving gear. Thus, they should get the gear before continuing on the task despite already beeing in the water.