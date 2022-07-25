# State

[README](../../../README.md) / [Documentation](../../Documentation.md) / [State Machine](../StateMachine.md)

---

## Table of Content

- [Fields](#fields)
- [Constructor](#constructor)
- [Methods](#methods)
- [Derived classes](#derived-classes)

---

The State class is the base for all states used by the state machines. It contains the basic information shared by all states. It's also responsible of providing the three stages for each state: Enter, Update and Exit. This gives greater control over each individual state as one can do setup in Enter, actions and exit conditions in Update and cleanup in Exit.

## Members

### Fields

| Field | Description |
| --- | --- |
| enum EVENT | The three possible stages a state can be in: ENTER, UPDATE and EXIT |
| EVENT stage | This variable is used to store the current stage |
| State nextState | Reference to the next state |
| GameObject npc | The parent object of the NPC |
| Animator anim | The animator of the NPC mesh |
| NavMeshAgent agent | The NavMesh Agent of the npc |
| ScenarioVariables scenarioVariables | Reference to the ScenarioVariables component on the scene |

### Constructor

_public State(GameObject, NavMeshAgent, Animator)_
- Sets npc, agent and anim
- Sets the reference for ScenarioVariables
- Sets the stage to EVENT.ENTER

### Methods

_public virtual void Enter()_
- Virtual method that is called from the constructor
- Sets stage to EVENT.UPDATE

_public virtual void Update()_
- Virtual method that is called from the Enter()
- Sets stage to EVENT.UPDATE

_public virtual void Exit()_
- Virtual method called from the Update()
- Sets stage to EVENT.EXIT

_public State Process()_
- The workhorse for the state machine
- Handles moving from stage to another (Enter -> Update (loop) -> Exit)
- Moves to the next state once Exit stage is done

## Derived classes

| Class | Description |
| --- | --- |
| [FirefighterState](Humans/FirefighterStates/FirefighterState.md) | Common parent for all firefighter states |
| RescuableState | Common parent for all rescuable states |
| BoatState | Common parent for all boat states |
| CarState | Common parent for all CarStates |
| RaftState | Common parent for all Raft states |