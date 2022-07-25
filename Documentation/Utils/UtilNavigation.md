# Navigation utilities
CBSafe.Simulation.AI.UtilNavigation

[README](../../README.md) / [Documentation](../Documentation.md) / [Utility classes](UtilsIndex.md)

---

_bool InWater(GameObject)_
- Checks if the GameObject is in the water

_Vector3 GetNormalVector(Vector3, Vector3)_
- Gets the normal vector from start towards end

_NavMeshHit FindClosestNavMeshAreaSamplePosition(NavMeshAgent, Vector3, string, float)_
- Gets the closest position to the given NavMesh area

_NavMeshHit GetShorelinePositionFromWater(NavMeshAgent, Vector3)_
- Gets a position on the land one unit from the shoreline when target is in the water

_NavMeshHit GetCurrentNavMeshArea(NavMeshAgent)_
- Gets the current NavMesh area for the agent

_NavMeshHit GetLinkPosition(Vector3, int)_
- Gets a position for the NavMesh Link (start or end)

_NavMeshLinkInstance CreateNavMeshLink(NavMeshAgent)_
- Gets the NavMeshLinkInstance of the created NavMesh Link

