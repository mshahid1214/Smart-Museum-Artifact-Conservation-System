# Task 1: Identify Operations

## Smart Museum Artifact Conservation System

The Smart Museum Artifact Conservation System continuously monitors the conservation chamber and performs different operations to protect valuable historical artifacts.

The operations identified from the given scenario are listed below.

| No. | Operation | Description |
|-----|-----------|-------------|
| 1 | `performSelfCheck()` | Performs a self-check of all essential sensors and environmental-control devices. |
| 2 | `validateSensorStatus()` | Verifies that all essential sensors are working correctly. |
| 3 | `registerArtifact()` | Records the identification information of the artifact placed inside the chamber. |
| 4 | `loadEnvironmentalProfile()` | Loads the environmental limits required for the artifact. |
| 5 | `monitorArtifact()` | Continuously monitors the artifact and chamber conditions. |
| 6 | `checkDoorStatus()` | Checks whether the chamber door is open or closed. |
| 7 | `activateConservation()` | Starts normal conservation activities when all required conditions are satisfied. |
| 8 | `measureTemperature()` | Measures the current temperature inside the chamber. |
| 9 | `measureHumidity()` | Measures the current humidity inside the chamber. |
| 10 | `compareEnvironmentalLimits()` | Compares the actual temperature and humidity with the artifact's required limits. |
| 11 | `correctTemperature()` | Attempts to restore the temperature to the permitted range. |
| 12 | `correctHumidity()` | Attempts to restore the humidity to the permitted range. |
| 13 | `verifyEnvironmentalRecovery()` | Verifies through sensor readings that the environmental condition has returned to the permitted range. |
| 14 | `startRecoveryTimer()` | Starts and monitors the allowed recovery period for an environmental problem. |
| 15 | `activateProtectionControls()` | Activates additional environmental controls to protect the artifact. |
| 16 | `generateOperatorAlert()` | Generates an alert for the museum operator when protection is required. |
| 17 | `detectVibration()` | Detects significant vibration while an artifact is inside the chamber. |
| 18 | `suspendRiskyActivities()` | Temporarily suspends activities that could increase the risk to the artifact. |
| 19 | `verifyVibrationStabilization()` | Verifies that vibration remains below the permitted threshold for the required stabilization period. |
| 20 | `suspendConservation()` | Immediately suspends normal conservation activities when the chamber door is opened. |
| 21 | `verifySafeResumption()` | Verifies the artifact's environmental conditions and sensor status before conservation resumes. |
| 22 | `switchToEmergencyPower()` | Switches the system to an emergency power source when normal power is lost. |
| 23 | `recordPowerFailure()` | Records the power failure incident when emergency power is unavailable. |
| 24 | `shutdownSafely()` | Places the system into a safe shutdown condition when continued operation is not possible. |
| 25 | `verifyArtifactRemovalSafety()` | Verifies that the chamber is safe and that no active protection response is underway before artifact removal. |
| 26 | `authorizeArtifactRemoval()` | Authorizes the operator to remove the artifact after safety conditions have been verified. |

## Operations Grouped by Function

| Category | Operations |
|----------|------------|
| System Initialization | `performSelfCheck()`, `validateSensorStatus()` |
| Artifact Management | `registerArtifact()`, `loadEnvironmentalProfile()` |
| Monitoring | `monitorArtifact()`, `checkDoorStatus()`, `measureTemperature()`, `measureHumidity()` |
| Environmental Control | `compareEnvironmentalLimits()`, `correctTemperature()`, `correctHumidity()`, `verifyEnvironmentalRecovery()`, `startRecoveryTimer()` |
| Protection | `activateProtectionControls()`, `generateOperatorAlert()` |
| Vibration Handling | `detectVibration()`, `suspendRiskyActivities()`, `verifyVibrationStabilization()` |
| Door Handling | `suspendConservation()`, `verifySafeResumption()` |
| Power Handling | `switchToEmergencyPower()`, `recordPowerFailure()`, `shutdownSafely()` |
| Artifact Removal | `verifyArtifactRemovalSafety()`, `authorizeArtifactRemoval()` |

## States / Modes That Are Not Operations

The following names are states or modes of the system. They are not included as operation names.

| State / Mode | Description |
|--------------|-------------|
| `MONITORING` | The system continuously monitors the chamber and artifact. |
| `CONSERVATION_ACTIVE` | Normal conservation activities are active. |
| `PROTECTION_MODE` | The system prioritizes protecting the artifact after an environmental recovery failure. |
| `VIBRATION_RESPONSE` | The system responds to significant vibration and suspends risky activities. |
| `SAFE_SHUTDOWN` | The system has entered a safe shutdown condition after a serious power failure. |

## Conclusion

A total of **26 operations** have been identified from the scenario. These operations describe actions performed by the system rather than system states or modes.

The identified operations cover:

- System self-checking
- Sensor validation
- Artifact registration
- Environmental profile loading
- Environmental monitoring
- Temperature correction
- Humidity correction
- Recovery verification
- Protection control
- Operator notification
- Vibration response
- Door handling
- Emergency power handling
- Safe shutdown
- Artifact removal safety
