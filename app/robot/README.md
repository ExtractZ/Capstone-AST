# app/robot

The only layer that talks to Klipper.

- `moonraker.py`: client for the Moonraker API (send G-code and macros, read status).
- `motion.py`: homing and moving to a deck slot or well.
- `pipette.py`: pick tips, aspirate, dispense, mix, eject.

Everything else in the app calls these functions instead of sending G-code directly.
