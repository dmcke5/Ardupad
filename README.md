# Ardupad

Ardupad USB Joypad

Default configuration - 2 Joysticks, 13 Buttons, 1 Dpad.

Joystick calibration:
1: Press the buttons on pins D0 and D3 simultaneously to put the controller into calibration mode. /n
2: Centre both joysticks and press the button on pin D1 to record mid position, RX LED will blink once to confirm step complete.
3: Move both joysticks to full extents of travel several times to record maximum axis values.
4: Press button on D1 again. RX LED will blink once more to confirm.
5: Calibration is now complete and stored.

If you're using this controller with Windows, you will also need to run the windows joypad calibration once you've completed the internal calibration.
If you change joysticks or your centerpoint drifts re-running the internal calibration should solve the problem.

Note: Whilst controller is in calibration mode all USB control output will cease until calibration is complete or controller is restarted.

Created by - Daniel McKenzie
23-06-2021
