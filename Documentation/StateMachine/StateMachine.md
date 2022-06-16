# Finite State Machine

[< Back](Documentation.md)

---



---

## Rescue States

#### FirefighterIdle
- The base of the firefighter states
- Handles setting up all possible state chains


| FirefighterWalk |  |
| --- | --- |
| Task | RESCUE |
| Method | SWIM |
| Search Pattern |  |
| Shoreline Direction |  |
| Sector Direction |  |
| Target | Not Vector3.zero |
|  |  |
| Task | RESCUE |
| Method | RAFT |
| Search Pattern |  |
| Shoreline Direction |  |
| Sector Direction |  |
| Target |  |
|  |  |
| Task | RESCUE |
| Method | RAFT |
| Search Pattern |  |
| Shoreline Direction |  |
| Sector Direction |  |
| Target |  |
|  |  |
| Task | SEARCH |
| Method | DIVE |
| Search Pattern | SHORELINE |
| Shoreline Direction | Not SHORELINEDIRECTION.NULL |
| Sector Direction |  |
| Target | Not Vector3.zero |
|  |  |
| Task | SEARCH |
| Method | DIVE |
| Search Pattern | SECTOR |
| Shoreline Direction |  |
| Sector Direction | Not SECTORDIRECTION.NULL |
| Target | Not Vector3.zero |

