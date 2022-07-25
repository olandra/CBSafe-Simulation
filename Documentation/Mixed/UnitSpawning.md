# Unit spawning

---

## Requirements

- Room property with scenario index -> Read to scenarioVariables.ScenarioIndex
- Room property with Dictionary\<int, Dictionary\<string, float\>\>
	- Read to scenarioVariables.AvailableUnits
	- int: scenario index
	- string: unit prefab name
	- float: timer for spawning (0 if not timed)
- Prefabs of each unit ready to use
- Prefabs added to the DefaultPool list in ScenarioSetup
	- The names have to match with the available units
- Information about waiting players in order of arrival
	- Need at least their player name to bind to the unit

## How it works

**ScenarioSetup:**
- Sets the values from room properties
- Runs the timer and makes an unit call event if timer is met

**VehicleCallController:**
- Instantiates and sets up the vehicle
- Compares if the call is valid (unit is available and not in use)
- Removes the unit from the scenarioVariables.AvailableUnits
- If there's a free player -> Unit leader
- If no free players -> DoRO becomes the unit leader

**Spawn markers:**
- Might want to add a cooldown between spawns
- Need to figure out how to use multiple spawns in a scenario
	- Maybe tag each destination and use the spawn to list it's related destinations

### Issues

- Unity cannot serialize dictionaries -> Cannot preview in inspector
	- Maybe unpack the dictionary into two lists with shared index?
	- Another option would be to unpack the dictionary into an object list
		- Requires the object with the values to represent the dictionary