# Task 2: Complete Operation Schemas

## Smart Museum Artifact Conservation System

An operation schema describes the operation, its purpose, inputs, preconditions, processing, outputs, postconditions, and exceptions.

---

## 1. performSelfCheck()

| Attribute | Description |
|-----------|-------------|
| Operation | `performSelfCheck()` |
| Purpose | Performs a self-check of all essential sensors and environmental-control devices. |
| Inputs | Sensor status, control-device status, power availability |
| Preconditions | Chamber is powered on. |
| Processing | Tests all essential sensors and environmental-control devices. |
| Output | Self-check result and diagnostic information |
| Postconditions | System can proceed toward normal monitoring only if all essential components pass. |
| Exception | If an essential sensor or control device fails, normal conservation cannot begin. |

---

## 2. validateSensorStatus()

| Attribute | Description |
|-----------|-------------|
| Operation | `validateSensorStatus()` |
| Purpose | Verifies that all essential sensors are working correctly. |
| Inputs | Temperature, humidity, vibration, door, light and artifact-condition sensor status |
| Preconditions | Sensors have been initialized. |
| Processing | Checks the availability and validity of all essential sensors. |
| Output | Valid or invalid sensor status |
| Postconditions | The system knows whether the sensors are suitable for conservation. |
| Exception | A failed essential sensor prevents normal conservation operation. |

---

## 3. registerArtifact()

| Attribute | Description |
|-----------|-------------|
| Operation | `registerArtifact()` |
| Purpose | Records the identification information of an artifact placed inside the chamber. |
| Inputs | Artifact identification information |
| Preconditions | An artifact has been placed inside the chamber. |
| Processing | Records and stores the artifact identification information. |
| Output | Artifact record |
| Postconditions | The artifact is registered for monitoring. |
| Exception | Missing or invalid artifact information prevents complete registration. |

---

## 4. loadEnvironmentalProfile()

| Attribute | Description |
|-----------|-------------|
| Operation | `loadEnvironmentalProfile()` |
| Purpose | Loads the environmental requirements specified for the artifact. |
| Inputs | Artifact environmental profile, temperature limits, humidity limits |
| Preconditions | Artifact has been registered. |
| Processing | Validates and stores the required environmental limits. |
| Output | Loaded environmental profile |
| Postconditions | Temperature and humidity limits are available for monitoring. |
| Exception | Invalid or missing environmental limits prevent active conservation. |

---

## 5. monitorArtifact()

| Attribute | Description |
|-----------|-------------|
| Operation | `monitorArtifact()` |
| Purpose | Continuously monitors the artifact and chamber conditions. |
| Inputs | Temperature, humidity, light, vibration, door and artifact-condition readings |
| Preconditions | System self-check has successfully completed. |
| Processing | Continuously collects and evaluates sensor readings. |
| Output | Current chamber and artifact-condition information |
| Postconditions | The system has updated information about the chamber and artifact. |
| Exception | Invalid sensor information triggers appropriate fault handling. |

---

## 6. checkDoorStatus()

| Attribute | Description |
|-----------|-------------|
| Operation | `checkDoorStatus()` |
| Purpose | Determines whether the chamber door is open or closed. |
| Inputs | Door sensor |
| Preconditions | Door sensor is operational. |
| Processing | Reads and validates the current door status. |
| Output | Door status |
| Postconditions | The system knows whether normal conservation activities can operate. |
| Exception | Invalid door status prevents safe conservation operation. |

---

## 7. activateConservation()

| Attribute | Description |
|-----------|-------------|
| Operation | `activateConservation()` |
| Purpose | Starts normal conservation activities. |
| Inputs | Door status, artifact profile, sensor status |
| Preconditions | Artifact is registered, environmental profile is loaded, door is closed, and essential sensors are operational. |
| Processing | Activates the normal environmental-control mechanisms. |
| Output | Conservation activation status |
| Postconditions | Normal conservation activities begin. |
| Exception | Conservation remains inactive if any required condition is not satisfied. |

---

## 8. measureTemperature()

| Attribute | Description |
|-----------|-------------|
| Operation | `measureTemperature()` |
| Purpose | Measures the current temperature inside the chamber. |
| Inputs | Temperature sensor |
| Preconditions | Temperature sensor is operational. |
| Processing | Reads and validates the current temperature. |
| Output | Current temperature value |
| Postconditions | Current temperature is available for comparison with the artifact's limits. |
| Exception | Invalid temperature reading requires sensor-fault handling. |

---

## 9. measureHumidity()

| Attribute | Description |
|-----------|-------------|
| Operation | `measureHumidity()` |
| Purpose | Measures the current humidity inside the chamber. |
| Inputs | Humidity sensor |
| Preconditions | Humidity sensor is operational. |
| Processing | Reads and validates the current humidity. |
| Output | Current humidity value |
| Postconditions | Current humidity is available for comparison with the artifact's limits. |
| Exception | Invalid humidity reading requires sensor-fault handling. |

---

## 10. compareEnvironmentalLimits()

| Attribute | Description |
|-----------|-------------|
| Operation | `compareEnvironmentalLimits()` |
| Purpose | Compares actual temperature and humidity with the permitted limits of the artifact. |
| Inputs | Current temperature, current humidity, environmental profile |
| Preconditions | Valid sensor readings and environmental profile are available. |
| Processing | Compares actual environmental readings against the required ranges. |
| Output | Within-limit or out-of-limit result |
| Postconditions | The system identifies whether environmental correction is required. |
| Exception | Missing or invalid sensor readings prevent reliable comparison. |

---

## 11. correctTemperature()

| Attribute | Description |
|-----------|-------------|
| Operation | `correctTemperature()` |
| Purpose | Attempts to restore temperature to the permitted range. |
| Inputs | Current temperature, required temperature range |
| Preconditions | Temperature is outside the permitted range and control equipment is available. |
| Processing | Activates the appropriate environmental-control mechanism. |
| Output | Temperature correction command |
| Postconditions | The system begins attempting to restore the required temperature. |
| Exception | If temperature does not recover within the allowed period, protection handling is initiated. |

---

## 12. correctHumidity()

| Attribute | Description |
|-----------|-------------|
| Operation | `correctHumidity()` |
| Purpose | Attempts to restore humidity to the permitted range. |
| Inputs | Current humidity, required humidity range |
| Preconditions | Humidity is outside the permitted range and control equipment is available. |
| Processing | Activates the appropriate humidity-control mechanism. |
| Output | Humidity correction command |
| Postconditions | The system begins attempting to restore the required humidity. |
| Exception | If humidity does not recover within the allowed period, protection handling is initiated. |

---

## 13. verifyEnvironmentalRecovery()

| Attribute | Description |
|-----------|-------------|
| Operation | `verifyEnvironmentalRecovery()` |
| Purpose | Verifies that an environmental correction has actually returned the condition to the permitted range. |
| Inputs | New temperature and humidity readings, environmental limits |
| Preconditions | A temperature or humidity correction command has been issued. |
| Processing | Obtains new sensor readings and compares them with the permitted limits. |
| Output | Recovery successful or recovery unsuccessful |
| Postconditions | Normal operation continues only when sensor readings confirm recovery. |
| Exception | Continued out-of-range conditions after the allowed recovery period trigger protection handling. |

---

## 14. startRecoveryTimer()

| Attribute | Description |
|-----------|-------------|
| Operation | `startRecoveryTimer()` |
| Purpose | Tracks the allowed period for correcting an environmental condition. |
| Inputs | Allowed recovery duration |
| Preconditions | Environmental correction has been initiated. |
| Processing | Starts and monitors the recovery timer. |
| Output | Elapsed recovery time |
| Postconditions | The system can determine whether environmental recovery occurred within the allowed period. |
| Exception | Timer expiration without successful recovery triggers protection handling. |

---

## 15. activateProtectionControls()

| Attribute | Description |
|-----------|-------------|
| Operation | `activateProtectionControls()` |
| Purpose | Activates additional measures to protect the artifact when normal environmental recovery fails. |
| Inputs | Environmental fault information |
| Preconditions | An environmental condition could not be corrected within the allowed recovery period. |
| Processing | Reduces light exposure and activates additional environmental controls. |
| Output | Protection-control activation status |
| Postconditions | Artifact protection is prioritized over normal conservation operation. |
| Exception | Failure of critical protection controls requires operator intervention. |

---

## 16. generateOperatorAlert()

| Attribute | Description |
|-----------|-------------|
| Operation | `generateOperatorAlert()` |
| Purpose | Generates an alert for the museum operator. |
| Inputs | Fault information, event information |
| Preconditions | A protection or emergency event has occurred. |
| Processing | Creates and sends an alert containing information about the abnormal condition. |
| Output | Operator alert |
| Postconditions | Museum operator is notified of the condition. |
| Exception | Failure to deliver the alert is recorded for later investigation. |

---

## 17. detectVibration()

| Attribute | Description |
|-----------|-------------|
| Operation | `detectVibration()` |
| Purpose | Detects significant vibration while an artifact is inside the chamber. |
| Inputs | Vibration sensor, permitted vibration threshold |
| Preconditions | Artifact is inside the chamber and vibration sensor is operational. |
| Processing | Measures vibration and compares it with the permitted threshold. |
| Output | Vibration event or no vibration event |
| Postconditions | Significant vibration causes the system to begin vibration-response handling. |
| Exception | Invalid vibration readings prevent reliable vibration verification. |

---

## 18. suspendRiskyActivities()

| Attribute | Description |
|-----------|-------------|
| Operation | `suspendRiskyActivities()` |
| Purpose | Temporarily suspends activities that could increase the risk to the artifact. |
| Inputs | Significant vibration event |
| Preconditions | Significant vibration has been detected. |
| Processing | Stops or suspends activities that could increase risk to the artifact. |
| Output | Suspended-activity status |
| Postconditions | Risk-increasing activities remain suspended during vibration response. |
| Exception | Failure to suspend required activities becomes a safety fault. |

---

## 19. verifyVibrationStabilization()

| Attribute | Description |
|-----------|-------------|
| Operation | `verifyVibrationStabilization()` |
| Purpose | Verifies that vibration has remained below the permitted threshold for the required stabilization period. |
| Inputs | Vibration readings, vibration threshold, stabilization duration |
| Preconditions | A significant vibration event has occurred. |
| Processing | Continuously monitors vibration during the required stabilization period. |
| Output | Stabilized or not stabilized result |
| Postconditions | Normal conservation can be considered for resumption only after successful stabilization and other safety checks. |
| Exception | Continued or renewed vibration keeps normal conservation suspended. |

---

## 20. suspendConservation()

| Attribute | Description |
|-----------|-------------|
| Operation | `suspendConservation()` |
| Purpose | Immediately suspends normal conservation activities when the chamber door is opened. |
| Inputs | Door-open event |
| Preconditions | Artifact is inside and normal conservation is active. |
| Processing | Suspends normal environmental operation while the chamber is open. |
| Output | Conservation-suspended status |
| Postconditions | Normal conservation does not continue while the chamber door is open. |
| Exception | Failure to suspend required activities becomes a safety fault. |

---

## 21. verifySafeResumption()

| Attribute | Description |
|-----------|-------------|
| Operation | `verifySafeResumption()` |
| Purpose | Verifies that conservation can safely resume after the chamber door is closed or another interruption ends. |
| Inputs | Door status, temperature, humidity, sensor status, artifact condition |
| Preconditions | Chamber door has been closed after an interruption. |
| Processing | Verifies sensor status and checks the artifact's environmental conditions. |
| Output | Safe or unsafe resumption result |
| Postconditions | Conservation resumes only if all required safety conditions are satisfied. |
| Exception | Conservation remains suspended if any verification fails. |

---

## 22. switchToEmergencyPower()

| Attribute | Description |
|-----------|-------------|
| Operation | `switchToEmergencyPower()` |
| Purpose | Switches the system to an emergency power source after normal power is lost. |
| Inputs | Normal power status, emergency power availability |
| Preconditions | Normal power has failed and emergency power is available. |
| Processing | Transfers critical system functions to the emergency power source. |
| Output | Emergency-power status |
| Postconditions | Critical system functions continue using emergency power. |
| Exception | If emergency power is unavailable, power-failure handling proceeds to safe shutdown. |

---

## 23. recordPowerFailure()

| Attribute | Description |
|-----------|-------------|
| Operation | `recordPowerFailure()` |
| Purpose | Records a power failure incident. |
| Inputs | Power status, time, system condition |
| Preconditions | Power failure has been detected and emergency power is unavailable. |
| Processing | Records the details of the power failure. |
| Output | Power-failure record |
| Postconditions | The power failure is documented for operators and later review. |
| Exception | Failure to record the incident is itself recorded if possible. |

---

## 24. shutdownSafely()

| Attribute | Description |
|-----------|-------------|
| Operation | `shutdownSafely()` |
| Purpose | Places the chamber into a safe shutdown condition. |
| Inputs | Power status, system condition |
| Preconditions | Normal power and emergency power are unavailable or continued operation is unsafe. |
| Processing | Disables nonessential operations and preserves artifact safety as far as possible. |
| Output | Safe-shutdown status |
| Postconditions | Normal conservation operation is stopped and the system remains in a safe condition. |
| Exception | Critical shutdown failure requires operator intervention. |

---

## 25. verifyArtifactRemovalSafety()

| Attribute | Description |
|-----------|-------------|
| Operation | `verifyArtifactRemovalSafety()` |
| Purpose | Verifies whether the artifact can safely be removed from the chamber. |
| Inputs | Chamber condition, environmental readings, protection status, sensor status |
| Preconditions | Artifact is registered and an operator has requested removal. |
| Processing | Checks chamber safety, environmental conditions and confirms that no active protection response is underway. |
| Output | Safe or unsafe removal result |
| Postconditions | Artifact removal can be authorized only if all safety conditions are satisfied. |
| Exception | Artifact remains inside the chamber if conditions are unsafe. |

---

## 26. authorizeArtifactRemoval()

| Attribute | Description |
|-----------|-------------|
| Operation | `authorizeArtifactRemoval()` |
| Purpose | Authorizes the operator to remove the artifact after safety verification. |
| Inputs | Successful artifact-removal safety verification |
| Preconditions | Chamber is confirmed safe and no active protection response is underway. |
| Processing | Grants permission for the operator to remove the artifact. |
| Output | Artifact-removal authorization |
| Postconditions | Operator is permitted to remove the artifact. |
| Exception | Authorization is denied if any safety condition is not satisfied. |

---

# Operation Schema Summary

| No. | Operation | Main Purpose |
|-----|-----------|--------------|
| 1 | `performSelfCheck()` | Check system components |
| 2 | `validateSensorStatus()` | Validate essential sensors |
| 3 | `registerArtifact()` | Register artifact |
| 4 | `loadEnvironmentalProfile()` | Load artifact requirements |
| 5 | `monitorArtifact()` | Monitor artifact and chamber |
| 6 | `checkDoorStatus()` | Check chamber door |
| 7 | `activateConservation()` | Start normal conservation |
| 8 | `measureTemperature()` | Measure temperature |
| 9 | `measureHumidity()` | Measure humidity |
| 10 | `compareEnvironmentalLimits()` | Compare environmental conditions |
| 11 | `correctTemperature()` | Correct temperature |
| 12 | `correctHumidity()` | Correct humidity |
| 13 | `verifyEnvironmentalRecovery()` | Verify environmental recovery |
| 14 | `startRecoveryTimer()` | Track recovery time |
| 15 | `activateProtectionControls()` | Activate protection measures |
| 16 | `generateOperatorAlert()` | Alert museum operator |
| 17 | `detectVibration()` | Detect significant vibration |
| 18 | `suspendRiskyActivities()` | Suspend risky activities |
| 19 | `verifyVibrationStabilization()` | Verify vibration stabilization |
| 20 | `suspendConservation()` | Suspend conservation |
| 21 | `verifySafeResumption()` | Verify safe conservation resumption |
| 22 | `switchToEmergencyPower()` | Switch to emergency power |
| 23 | `recordPowerFailure()` | Record power failure |
| 24 | `shutdownSafely()` | Perform safe shutdown |
| 25 | `verifyArtifactRemovalSafety()` | Verify safe artifact removal |
| 26 | `authorizeArtifactRemoval()` | Authorize artifact removal |

---

# Conclusion

The operation schemas define how the Smart Museum Artifact Conservation System performs its major operations.

Each schema identifies:

- The operation being performed
- Its purpose
- Required inputs
- Preconditions
- Processing steps
- Outputs
- Postconditions
- Possible exceptions

The schemas ensure that environmental corrections are verified, abnormal conditions are handled safely, power failures are managed appropriately, and artifact removal is allowed only after safety conditions have been confirmed.
