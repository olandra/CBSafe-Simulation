# Raising an Event

[README](../../README.md) / [Documentation](../Documentation.md)

---

## Table of Contents

- [Raising a command event](#raising-a-command-event)
- [Command charts](#event-system-command-charts)
	- Task
	- Method
	- Search pattern

---

## Raising a command event

The AI itself is made autonomous, but it does rely on commands given by the squad leaders. These events should be raised in the script that is responsible of the player inputs. To use the events, you should create an AIEvent object and then call it's `SendOrderEvent()` method.

1. Declare an AIEvent:
	`CBSafe.Simulation.AI.AIEvent aiEvent;`
2. Create a new object in `Start()`:
	`aiEvent = new CBSafe.Simulation.AI.AIEvent();`
3. Call the method to raise an event:
	`aiEvent.SendOrderEvent("Player1", "Surface", BellaBoat.transform.position);`

The declaration of the method is: `public void SendOrderEvent(string leader, string order, Vector3 target)`

- The first argument is the unique identifier of the sending team leader
- The second argument is the command string. This is a combination of words defined in the charts below. The words can be in any order - Case sensitive
- The third argument is the target given with the command. Use Vector3.zero if no target is required

Examples  

Please refer to the AI Testing file: 
`./Assets/Scripts/AI/Testing/StateMachine/AITesting/TestingUI/TestingUI.cs`

---

## Event system command charts

Include the words in any order into the command string given to the `AIEvent.SendOrderEvent()` method. You can combine Tasks and Methods. If a task requires extra definition, include that one too (e.x. Search needs a Pattern)

| Task | Description |
| --- | --- |
| Surface | Task for surface rescue principle |
| Search | Task to order a search pattern (see Search Pattern table for extra definitions) |
| Fire | Task to extinguish fire |
| Surface | The new principle for surface rescue |
| Return (Boat only) | Return task for the boat |

| Method | Description |
| --- | --- |
| Water | Use water inventory for extinguishing |
| Foam | Use foam inventory for extinguishing |

| Search Pattern | Description |
| --- | --- |
| Shoreline + Direction | Search along the shoreline, moving outwards each turn - **Requires** "**Left**" or "**Right**" for the direction |
| Sector + Direction | Search a sector from the target position. Angle is defined in ScenarioVariables - **Requires** **"Left"**, **"Right"**, **"In"** or **"Out"** for the direction |

