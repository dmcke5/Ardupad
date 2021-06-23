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

## Wiring
Connect all buttons between their corresponding pin and GND. Buttons should be normally open.
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
- Left X = A3
- Left Y = A2
- Right X = A1
- Right Y = A0

## Notes
If you're using this controller with Windows, you will also need to run the windows joypad calibration once you've completed the internal calibration.
If you change joysticks or your centerpoint drifts re-running the internal calibration should solve the problem.

Created by - Daniel McKenzie
23-06-2021
