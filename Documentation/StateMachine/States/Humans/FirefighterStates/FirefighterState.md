# FirefighterState

[README](../../../../../README.md) / [Documentation](../../../../Documentation.md) / [State Machine](../../../StateMachine.md) / [State](../../State.md)

---

## Table of Content

- [Fields](#fields)
- [Constructor](#constructor)
- [Methods](#methods)
- [Derived classes](#derived-classes)

---


## Members

### Fields

| Field | Description |
| --- | --- |
| enum STATE | Contains the identifiers for each possible state derived from this class |
| STATE name | The identifier for this state. This can be used to control external systems like separating animation control from the AI |
| AIStateMachineFirefighter stateMachine | Reference to the AIStateMachineFirefighter component of this NPC |
| AIUnitInfo aiUnitInfo | Reference to the AIUnitInfo of this NPC |

### Constructor

_public FirefighterState(GameObject, NavMeshAgent, Animator)_
- Passes npc, agent and anim to the parent
- Sets the reference for the AIStateMachineFirefighter
- Sets the reference for the AIUnitInfo

### Methods

_public bool NeedsSwimmingSuit()_
- Returns true if the npc doesn't have swimming suit on

## Derived classes

| Class | Description |
| --- | --- |
| [FirefighterIdle](FirefighterIdle.md) | Idle state for the firefighter |