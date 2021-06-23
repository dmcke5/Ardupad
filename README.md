# Ardupad USB Joypad

Default configuration - 2 Joysticks, 13 Buttons, 1 Dpad.

## Requirements
- An Atmega32u4 based Arduino board with enough pins to suit the type of controller you want to build. I'd reccomend an Arduino Micro: https://store.arduino.cc/usa/arduino-micro
- The Arduino Joystick Library: https://github.com/MHeironimus/ArduinoJoystickLibrary

## Joystick calibration:
1. Press "Start" and "R3" simultaneously to put the controller into calibration mode (pins D0 and D3). USB Controller output will cease.
2. Centre both joysticks and press the button "A" (D1) to record middle position, RX LED will blink once to confirm step complete.
3. Move both joysticks to full extents of travel several times to record maximum axis values.
4. Press button "A" (D1) again. RX LED will blink once more to confirm.
5. Calibration is now complete and stored and USB controller output will begin again.

## Joystick Configuration Options
The following configuration options are available for the joysticks:
- invertLeftY, invertLeftX, invertRightY, invertRightX -- Does what it says, inverts the axis specified.
- deadBandLeft, deadBandRight -- Default 10 -- How much movement to ignore at the middle of the joystick. Increase if you're having drift/centering problems.
- useDeadband -- Enable/disable deadband.
- earlyLeftX, earlyLeftY, earlyRightX, earlyRightY -- Default 30 -- Axis travel limits. This reduces the end points of each axis to help "square out" the response of the joysticks. 
- scaledJoystickOutput -- Scale both axis to make the travel the same. Needed on switch joysticks but should work fine on any, I'd leave it on unless you have a good reason not to.

Joystick calibration stores raw values and the code calculates the look up tables on start up, so no need to re-calibrate your joysticks after changing any of the configuration options.

## General Configuration
The following general configuration options are available:
- baudrate -- Used only for the cpu cycle test. This value needs to match your serial monitor to be able to read the results.
- cycleTimeTest -- Use if you want to test the cpu cycle time of the controller. This will print a sample of the current CPU cycle speed out every second over the serial port. I do not recommend leaving this option enabled whilst using the controller, this is only for testing.

## Wiring
Connect all buttons between their corresponding pin and GND. Buttons should be normally open.
Connect the signal output of the joystick to the pins listed. Joysticks will also need a power and GND connection to function.

##### Buttons:
- A = D1
- B = D5
- X = D2
- Y = D4
- L1 = D15
- L2 = D13
- L3 = D16
- R1 = D7
- R2 = D6
- R3 = D0
- Start = D3
- Select = D12
- Up = D8
- Down = D9
- Left = D10
- Right = D11

##### Joysticks:
- Left X = A3
- Left Y = A2
- Right X = A1
- Right Y = A0


## Notes
If you're using this controller with Windows, you will also need to run the windows joypad calibration once you've completed the internal calibration.
If you change joysticks or your centerpoint drifts re-running the internal calibration should solve the problem.

The code has some defaults baked into it based on Nintendo Switch joysticks so the joysticks should at least respond before the first calibration.

If you plan to change the DPad wiring, ensure you keep them in the same order in the code otherwise your dpad will not function correctly.

Created by - Daniel McKenzie
23-06-2021
