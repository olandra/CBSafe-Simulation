# Required when adding to the simulation

[< Back](../Documentation.md)

---

## Adding an unit

When adding a firefighting unit to the simulation it's required to:
- *Tag* the firetruck as "RescueVehicle"
- By design the simulation allows and requires three members in the unit. These must be *tagged* as:
	- "Driver"
	- "Member1"
	- "Member2"
	- All of these members will need their character mesh as a child of the object and *tagged* as "CharacterMesh"
- If the unit contains a raft, it must be *named* as "Raft". This raft needs to:
	- Be on the ground
	- Active
	- Has two targets for the members to use *named* as:
		- "RaftTargetMember1"
		- "RaftTargetMember2"
	- Have two "dummies" to show the members using the raft *named* as:
		- "FireFighter_Boat1"
		- "FireFighter_Boat2"
- The raft has to have a duplicate that has a *tag* of "Boat" and is:
	- Active
	- Shown in the transport position

Things to list later:
- AIUnitInfo script linking
- Adding NavMeshAgent component
- Rescuables
- Boat

## Adding a state maching



## Adding a state



## Adding global variables

All global AI and navigation related variables are added to the ScenarioVariables.cs file. These should be private and have a corresponding Property. All variables are initially set in the ScenarioVariables.Start() but can be read and set by other scripts (e.g. weather).

## Adding unit variables

Unit variables should be added to the AIUnitInfo.cs and follow the same principles than global variables.