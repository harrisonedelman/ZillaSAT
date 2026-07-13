# Sensor Node

## Communication Protocol
I chose to use UART as my communication protocol as all three of my sensors combined stay well under 115200 baud rate.
Ex. In a ~30ms shock event, 10 samples come out to be ~400Hz

## IMU
- Flight phase detection
    Each phase of flight has a distinct acceleration, think free fall, apogee, and descent under parachute. This data will power our state machine and trigger phase transitions.
- Fault detection
    If the rocket loses stability or a deployment fails, the gyroscope will allow this behavior to be detected.
- Shock-event capture
    We can record the parachute deployment shock and will allow us to graph the exact G-force curve of the flight

## Magnetometer
- Attitude determination
    Used to calculate orientation in space.

## Power monitor
- Telemetry Data Logging
    Tracks energy consumption, current, and voltage during flight.
- Fault Detection
    Shuts down subsystems if transient power conditions or overcurrent spikes are detected.

# Onboard Computer (OBC)
Receives, validates, and decodes sensor frames
Runs flight-phase and fault-detection state machine
Sends telemetry to ground station

# Ground Station
Displays live telemetry from OBC
- Flight Phase
- Mode
- Sensor Stats
- Event log
Sends commands to OBC
- Clear SAFE mode


BOM:

