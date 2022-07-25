# Scenario variables

[README](../../README.md) / [Documentation](../Documentation.md)

---

This file lists the common scenario variables used by the AI and the navigation. The file also contains methods directly related to these variables.

| Variable | Description |
| --- | --- |
| InNeedOfHelp | A list of rescuables who are in need for help |
| InRescue | A list of rescuables who are currently beeing rescued |
| ErCheckupLine | A list of rescuables who are waiting for a medical check up |
|||
| VisibilityDiving | The visibility in meters while diving |
| VisibilityNormal | General visibility in meters |
| VisibilityAngle | Half of the angle the NPC can see - Field of view |
| DivingDepth | The depth the rescuers dive (from the surface of the water) |
| SearchAreaWidth | How wide is the shoreline search area |
| SectorSearchAngle | The angle for sector search |
| SectorSearchMaxIterations | How far the search goes (iterations times visibility) |
|||
| SwimRescueContactTime | How many seconds it takes to start rescue after reaching the rescuable |
| CarCrewExitTime | How many seconds it takes for the crew to exit the vehicle |
| RaftDownTime | How many seconds it takes to take the raft down from the roof of the vehicle |
| DivingGearwearTime | How many seconds it takes to equip the diving gear |
| StartRaftSectorSearchTime | How many seconds it takes for the diver to prepare for the search |
|||
| CloseToTargetNormal |  |
| CloseToTargetSwimming |  |
| StoppingDistanceNormal |  |
| StoppingDistanceSwimming |  |
| NPCHidingPosition |  |
||| 
| DivingGearLocation |  |
| NPCMeshTag |  |
| DriverObjectTag |  |
| Member1ObjectTag |  |
| Member2ObjectTag |  |
| RaftInactiveObjectName |  |
| RaftActiveObjectName |  |
| RescueVehicleObjectTag |  |
| SectorSearchAnchorObjectName |  |
| SectorSearchAnchorTargetObjectName |  |
| RaftMeshObjectName |  |
| RaftMember1TargetObjectName |  |
| RaftMember2TargetObjectName |  |
| BackOfCarObjectName |  |
| LeftOfCarObjectName |  |
| FrontOfCarObjectName |  |
| RaftMember1DummyObjectName |  |
| RaftMember2DummyObjectName |  |
| ErTargetLocation |  |
|||
| SamplePositionRange | Range for the NavMesh.SamplePosition() |
|||
| Speed | A dictionary containing the speed values for the NPCs |

_void MoveRescuableInLine(GameObject)_
- Move the rescuable to the next list in their path to salvation

