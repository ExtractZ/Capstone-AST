# klipper

Klipper configuration, copied to `~/printer_data/config/` on the Pi.

- `printer.cfg`: main file; includes the others.
- `octopus_pins.cfg`: MCU connection and pin aliases from the electrical pin map.
- `motion.cfg`: X, Y, Z steppers, endstops, travel limits, homing.
- `pipette.cfg`: plunger, volume dial and tip-eject steppers.
- `macros.cfg`: PICK_TIPS, ASPIRATE, DISPENSE, MIX, EJECT_TIPS.
- `safety.cfg`: e-stop and door inputs, pause behaviour.

Klipper's automatic backups (`printer-<date>.cfg`) are ignored by git.
