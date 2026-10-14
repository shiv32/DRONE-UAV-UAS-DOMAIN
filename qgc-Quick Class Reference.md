

# QGroundControl V5.1 — Quick Class Reference

For your custom QGC build, focus on these existing C++ classes first. They cover the main path from connecting a UAV to reading telemetry, sending commands, and planning missions.

## 1. Classes by functionality

| Function                    | Class / interface names to study                               |
| --------------------------- | -------------------------------------------------------------- |
| Connection management       | `LinkInterface`, `LinkManager`                                 |
| MAVLink communication       | `MAVLinkProtocol`                                              |
| Vehicle discovery           | `MultiVehicleManager`                                          |
| Connected UAV               | `Vehicle`                                                      |
| Telemetry values            | `Vehicle`, `Fact`, `FactGroup`                                 |
| Autopilot parameters        | `ParameterManager`                                             |
| Flight commands             | `Vehicle`, MAVLink command definitions                         |
| Firmware-specific behavior  | `FirmwarePlugin`                                               |
| Mission planning            | `PlanMasterController`, `MissionController`                    |
| Mission upload/download     | `MissionManager`, `PlanManager`                                |
| Mission item representation | `VisualMissionItem`, `SimpleMissionItem`, `ComplexMissionItem` |
| Custom application behavior | `QGCCorePlugin`                                                |
| Main application            | `QGCApplication`                                               |

## 2. Open these files first

- [Connection — ](https://github.com/mavlink/qgroundcontrol/tree/v5.1.5/src/Comm)[`LinkManager`](https://github.com/mavlink/qgroundcontrol/tree/v5.1.5/src/Comm)
- [Vehicle — ](https://github.com/mavlink/qgroundcontrol/blob/v5.1.5/src/Vehicle/Vehicle.h)[`Vehicle.h`](https://github.com/mavlink/qgroundcontrol/blob/v5.1.5/src/Vehicle/Vehicle.h)
- [Telemetry / Facts — ](https://github.com/mavlink/qgroundcontrol/tree/v5.1.5/src/FactSystem)[`FactSystem`](https://github.com/mavlink/qgroundcontrol/tree/v5.1.5/src/FactSystem)
- [Mission planning — ](https://github.com/mavlink/qgroundcontrol/tree/v5.1.5/src/MissionManager)[`MissionManager`](https://github.com/mavlink/qgroundcontrol/tree/v5.1.5/src/MissionManager)
- [Custom build guide](https://github.com/mavlink/qgroundcontrol/blob/v5.1.5/docs/en/qgc-dev-guide/custom_build/custom_build.md)

## 3. Quick learning sequence

1. `LinkManager` → understand connection setup.
2. `MAVLinkProtocol` → understand MAVLink message processing.
3. `MultiVehicleManager` → understand vehicle discovery.
4. `Vehicle` → read telemetry and issue supported commands.
5. `Fact` / `FactGroup` → understand telemetry values exposed to QML.
6. `PlanMasterController` → understand mission planning and upload flow.
7. `MissionController` / `MissionManager` → understand mission items and transfer.

Start with `Vehicle.h` if you want to build your own telemetry dashboard and command interface. 
It is the most useful central class to understand before modifying QGC's UI.