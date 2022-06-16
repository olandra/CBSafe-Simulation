# General Unity utilities
CBSafe.Simulation.AI.UtilUnity

[< Back](UtilsIndex.md)

---

_void RemoveFixedJoint(GameObject)_
- Removes the FixedJoint component from the given GameObject

_bool CheckForNewOrder(AIUnitInfo, AIUnitInfo.TASK, AIUnitInfo.METHOD, AIUnitInfo.SEARCHPATTERN, AIUnitInfo.SHORELINEDIRECTION, AIUnitInfo.SECTORDIRECTION)_
- Checks if the team leader has given a new order for the team

_void ChangeForwardDerection(GameObject, GameObject)_
- Turns the GameObject around while keeping the given child GameObject facing the original direction

_void ChangeForwardDerection(GameObject)_
- Turns the GameObject around while keeping all child GameObject facing the original direction

_bool CanSeeTarget(GameObject, Transform, bool)_
- Can the NPC see it's target

_List\<GameObject\> GetVisibleRescuables(GameObject, List\<GameObject\>, bool)_
- Gets a list of all rescuables the NPC can see

_GameObject FindClosestRescuable(GameObject, List\<GameObject\>)_
- Gets the closest rescuable the NPC can see

_GameObject CanSeeRescuables(GameObject, GameObject, bool)_
- Checks if the NPC can see a rescuable and returns the closest one

