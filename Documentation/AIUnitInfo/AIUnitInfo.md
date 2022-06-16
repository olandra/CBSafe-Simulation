# AIUnitInfo

[< Back](../Documentation.md)

---

This script contains the information about the unit and sets the unit up when the unit is loaded. It also acts as an event listener for the orders given by the team leader (player).

| Variable | Description |
| --- | --- |
| Order | The order given via event |
| Target | The target given via event |
| TargetObject | (Obsolete) |
| Leader | The player who leads the team |
| GivenTask | The task given to the team |
| GivenMethod | The method to be used by the team |
| GivenSearchPattern | If a search is tasked, the type of the search |
| GivenShorelineDirection | Direction for the shoreline search pattern |
| GivenSectorDirection | Direction for the sector search pattern |
| SectorSearchAnchor | Helper game object for the sector search |
| SectorSearchAnchorTarget | Target object for the helper object |
| RaftStatus | The status of the raft |
| Driver | The driver NPC of the team |
| Member1 | The first rescue member of the team |
| MeshMember1 | The outlook mesh of the first member |
| HasDivingGearMember1 | Does the fisrt member have diving gear equipped |
| UsingRaftMember1 | Is the first member using the raft |
| Member2 | The second rescue member of the team |
| MeshMember2 | The outlook mesh of the second member |
| HasDivingGearMember2 | Does the second member have diving gear equipped |
| UsingRaftMember2 | Is the second member using the raft |
| Boat | Boat assigned to the team |
| Raft | Raft assigned to the team |
| ScenarioVariables | Reference to the ScenarioVariables object |

_void OnEnable()_
- Activates the event listener

_void OnDisable()_
- Deactivates the event listener

_void OnEvent(EventData)_
- The event listener

_void SerupNPC(GameObject)_
- Setup an NPC

_void SetupRaft(GameObject)_
- Setup the raft

_IEnumerator RaftDown()_
- Coroutine to wait for the raft to be taken down from the vehicle

_ void SetTask(string)_
- Sets the given task by the event

_void SetMethod(string)_
- Sets the given method by the event

_void SetSearchDefinition(string)_
- Sets the given search pattern by the event

_void SetShorelineDirection(string)_
- Sets the given direction for the shoreline search pattern by the event

_void SetSectorDirection(string)_
- Sets the given direction for the sector search pattern by the event

