# Smart Energy Meter with Billing Alert

An Arduino Uno based educational prototype that reads a current-sensor signal and sends readings to a laptop dashboard over USB serial. The dashboard is intended to show live readings, estimate energy use and cost using a configured tariff, and display an alert when the estimated cost reaches a user-set billing limit.

> **Project status:** Add the actual firmware, dashboard source, verified wiring diagram, and measured test results before presenting this repository as a completed implementation. Do not enter simulated readings as test results.

## Team

- **Sanskriti Tomar** - BTEL25O1097
- **Priyanshu Kushwaha** - BTEL25O1134
- **Mentor:** Dr. Vikas Mahor
- **Group:** 50
- **Branch:** Electronics Engineering

## Components

- Arduino Uno
- Current-sensing module (**record the exact model and range from the module label/datasheet**)
- Laptop or computer for the dashboard
- USB cable for Arduino programming and serial communication
- Relay module, if used in the final build (**verify its exact model and ratings**)
- Test load, such as a lamp, suitable low-voltage wiring, and an enclosure appropriate to the build
- Power source(s) appropriate to each module, as specified by its manufacturer

## How the system works

1. The current-sensing module produces a signal related to the load current.
2. The Arduino Uno reads the sensor signal and processes it using the calibration values in the firmware.
3. The Arduino sends readings to the laptop through USB serial communication.
4. The dashboard displays readings and estimates energy/cost using the tariff and assumptions entered in the application.
5. The dashboard displays an alert when the estimated cost reaches the configured billing limit.
6. If a relay is included, the Arduino can control its low-voltage input according to the firmware. The relay's load-side wiring must match the module's rating and be installed safely.

## Setup

### Arduino

1. Install the Arduino IDE from the official Arduino website.
2. Connect the Arduino Uno to the computer using USB.
3. Open the project's `.ino` firmware file in the Arduino IDE.
4. Select **Tools > Board > Arduino Uno** and select the correct port under **Tools > Port**.
5. Confirm that the sensor input pin, relay output pin (if used), calibration constants, and serial baud rate in the firmware match the actual hardware and dashboard configuration.
6. Compile and upload the firmware.

### Laptop dashboard

1. Add the actual dashboard source files and its programming language/runtime to this repository.
2. Follow the dashboard's own install/run instructions (add the exact commands here once the implementation is known).
3. Connect the Arduino by USB and choose the serial port shown by the operating system.
4. Set the dashboard's baud rate to the same value used by the Arduino firmware, then start the data stream.
5. Enter the tariff and billing-alert threshold used for the demonstration.
6. Confirm that fresh serial data appears before connecting or switching any load.

**Serial message format:** Document the exact format emitted by the firmware here. For example, if the implementation uses comma-separated fields, record their order and units (such as `current_A,energy_kWh,cost`). The example is illustrative only; it must match the actual firmware and dashboard parser.

## Calibration and test record

Record actual measurements in `data/test_readings.csv` (or another documented file). Include the date/time, test load, sensor raw value, sensor-derived value, reference instrument reading, tariff assumption, estimated cost, and whether the alert triggered. State the reference instrument and test conditions. Do not report accuracy until repeated measurements have been compared with a suitable reference.

## Measurement limitations

A current sensor alone does not directly measure real energy for every load. If the project estimates power using an assumed voltage or power factor, state those assumptions in the dashboard and report. More accurate billing estimates require suitable voltage and power measurement, calibration, and the applicable electricity tariff rules. This prototype is for education and demonstration; it is not a certified utility billing meter.

## Safety

Mains electricity can cause fatal shock or fire. Do not work on exposed or energized mains wiring. Keep mains connections enclosed and have the mains-side circuit, relay contacts, load rating, and isolation checked by a qualified electrician. Verify module voltage, pinout, and ratings from the exact part documentation before wiring.

## Repository contents

Add the files that actually exist in the project:

```text
.
|-- README.md
|-- firmware/
|   `-- smart_energy_meter.ino
|-- dashboard/
|   `-- (dashboard source files)
|-- hardware/
|   `-- (verified circuit diagram and module details)
`-- data/
    `-- (actual calibration and test readings, if collected)
```

Remove any example path above that does not exist, or replace it with the real project filename.

## Project details to complete

- Current sensor model and datasheet: **[]**
- Relay model and ratings, if used: **[add exact model/link]**
- Dashboard language/application and version: **[add details]**
- Arduino serial baud rate and message format: **[copy from working code]**
- Tariff value/source and alert threshold: **[add the values used for testing]**
- Wiring diagram, source-code URL, and demonstration video: **[add links when available]**
