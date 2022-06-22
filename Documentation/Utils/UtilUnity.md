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

_List\<GameObject\> RemoveNullsFromListGameObject(List\<GameObject\>)_
- Removes nulls from the provided list of GameObjects

_bool CanSeeTarget(GameObject, Transform, float)_
- Can the NPC see it's target

_List\<GameObject\> GetVisibleObjects(GameObject, List\<GameObject\>, float)_
- Gets a list of all objects the NPC can see

_GameObject FindClosestObject(GameObject, List\<GameObject\>)_
- Gets the closest object the NPC can see

_GameObject CanSeeRescuables(GameObject, GameObject, bool)_
- Checks if the NPC can see a rescuable and returns the closest one

_GameObject CanSeeFires(GameObject, GameObject)_
- Checks if the NPC can see a fire and returns the closest one

_GameObject FindWithTag(Transform, string)_
- Finds the child object with the given tag

