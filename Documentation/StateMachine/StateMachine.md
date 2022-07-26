# Finite State Machine

[README](../../README.md) / [Documentation](../Documentation.md)

---

## StateMachines

- [AIStateMachineBoat](AIStateMachineBoat.md)
- [AIStateMachineCar](AIStateMachineCar.md)
- [AIStateMachineFirefighter](AIStateMachineFirefighter.md)
- [AIStateMachineRaft](AIStateMachineRaft.md)
- [AIStateMachineRescuable](AIStateMachineRescuable.md)

## States from parent to children

[State](States/State.md)

## Master list of the states

- [AITestingState](States/AITestingState.md)

- [BoatArrival](States/Vehicles/BoatStates/BoatArrival.md)
- [BoatDamageControl](States/Vehicles/BoatStates/BoatDamageControl.md)
- [BoatDivingGear](States/Vehicles/BoatStates/BoatDivingGear.md)
- [BoatDrive](States/Vehicles/BoatStates/BoatDrive.md)
- [BoatExtinguish](States/Vehicles/BoatStates/BoatExtinguish.md)
- [BoatIdle](States/Vehicles/BoatStates/BoatIdle.md)
- [BoatSearch](States/Vehicles/BoatStates/BoatSearch.md)
- [BoatSetup](States/Vehicles/BoatStates/BoatSetup.md)
- [BoatState](States/Vehicles/BoatStates/BoatState.md)
- [BoatSurface](States/Vehicles/BoatStates/BoatSurface.md)

- [CarCrewExit](States/Vehicles/CarStates/CarCrewExit.md)
- [CarDrive](States/Vehicles/CarStates/CarDrive.md)
- [CarDropBoat](States/Vehicles/CarStates/CarDropBoat.md)
- [CarIdle](States/Vehicles/CarStates/CarIdle.md)
- [CarState](States/Vehicles/CarStates/CarState.md)

- [FirefighterIdle](States/Humans/FirefighterStates/FirefighterIdle.md)
- [FirefighterState](States/Humans/FirefighterStates/FirefighterState.md)
- [FirefighterWalk](States/Humans/FirefighterStates/FirefighterWalk.md)

- [FirefighterBoatIdle](States/Humans/FirefighterStates/BoatCrew/FirefighterBoatIdle.md)
- [FirefighterBoatNewTask](States/Humans/FirefighterStates/BoatCrew/FirefighterBoatNewTask.md)
- [FirefighterBoatRescue](States/Humans/FirefighterStates/BoatCrew/FirefighterBoatRescue.md)
- [FirefighterBoatSearch](States/Humans/FirefighterStates/BoatCrew/FirefighterBoatSearch.md)
- [FirefighterBoatStartRescue](States/Humans/FirefighterStates/BoatCrew/FirefighterBoatStartRescue.md)
- [FirefighterBoatSurface](States/Humans/FirefighterStates/BoatCrew/FirefighterBoatSurface.md)
- [FirefighterBoatTaskDone](States/Humans/FirefighterStates/BoatCrew/FirefighterBoatTaskDone.md)

- [FirefighterExtinguishFires](States/Humans/FirefighterStates/Extinguish/FirefighterExtinguishFires.md)
- [FirefighterFindFires](States/Humans/FirefighterStates/Extinguish/FirefighterFindFires.md)
- [FirefighterGetHose](States/Humans/FirefighterStates/Extinguish/FirefighterGetHose.md)
- [FirefighterReturnHose](States/Humans/FirefighterStates/Extinguish/FirefighterReturnHose.md)

- [FirefighterAssistRescue](States/Humans/FirefighterStates/SurfaceRescue/FirefighterAssistRescue.md)
- [FirefighterDivingRescue](States/Humans/FirefighterStates/SurfaceRescue/FirefighterDivingRescue.md)
- [FirefighterRaftSectorSearch](States/Humans/FirefighterStates/SurfaceRescue/FirefighterRaftSectorSearch.md)
- [FirefighterRescue](States/Humans/FirefighterStates/SurfaceRescue/FirefighterRescue.md)
- [FirefighterSectorSearch](States/Humans/FirefighterStates/SurfaceRescue/FirefighterSectorSearch.md)
- [FirefighterShorelinePhase1](States/Humans/FirefighterStates/SurfaceRescue/FirefighterShorelinePhase1.md)
- [FirefighterShorelinePhase2](States/Humans/FirefighterStates/SurfaceRescue/FirefighterShorelinePhase2.md)
- [FirefighterStartRescue](States/Humans/FirefighterStates/SurfaceRescue/FirefighterStartRescue.md)
- [FirefighterSwimmingSuit](States/Humans/FirefighterStates/SurfaceRescue/FirefighterSwimmingSuit.md)
- [FirefighterTakeDivingGear](States/Humans/FirefighterStates/SurfaceRescue/FirefighterTakeDivingGear.md)
- [FirefighterUsingRaft](States/Humans/FirefighterStates/SurfaceRescue/FirefighterUsingRaft.md)
- [SectorSearchAnchorController](States/Humans/FirefighterStates/SurfaceRescue/SectorSearchAnchorController.md)

- [RaftCarriedToWater](States/Vehicles/RaftStates/RaftCarriedToWater.md)
- [RaftDrive](States/Vehicles/RaftStates/RaftDrive.md)
- [RaftGoToRescuable](States/Vehicles/RaftStates/RaftGoToRescuable.md)
- [RaftIdle](States/Vehicles/RaftStates/RaftIdle.md)
- [RaftRescue](States/Vehicles/RaftStates/RaftRescue.md)
- [RaftSectorSearch](States/Vehicles/RaftStates/RaftSectorSearch.md)
- [RaftStartRescue](States/Vehicles/RaftStates/RaftStartRescue.md)
- [RaftStartSectorSearch](States/Vehicles/RaftStates/RaftStartSectorSearch.md)
- [RaftState](States/Vehicles/RaftStates/RaftState.md)
- [RaftStopSectorSearch](States/Vehicles/RaftStates/RaftStopSectorSearch.md)
- [SectorSearchRaftAnchorController](States/Vehicles/RaftStates/SectorSearchRaftAnchorController.md)

- [RescuableDeath](States/Humans/RescuableStates/RescuableDeath.md)
- [RescuableDrowning](States/Humans/RescuableStates/RescuableDrowning.md)
- [RescuableIdle](States/Humans/RescuableStates/RescuableIdle.md)
- [RescuableInRescue](States/Humans/RescuableStates/RescuableInRescue.md)
- [RescuableRescued](States/Humans/RescuableStates/RescuableRescued.md)
- [RescuableSetup](States/Humans/RescuableStates/RescuableSetup.md)
- [RescuableState](States/Humans/RescuableStates/RescuableState.md)
- [RescuableSubmerge](States/Humans/RescuableStates/RescuableSubmerge.md)
- [RescuableUnconscious](States/Humans/RescuableStates/RescuableUnconscious.md)
- [RescuableWalk](States/Humans/RescuableStates/RescuableWalk.md)

- [State](States/State.md)