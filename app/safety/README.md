# app/safety

Safety handling in software.

- `monitor.py`: watches e-stop and door status from Klipper, pauses the run, flags interrupted runs (ER-06).

The hardware relay chain cuts motor power on its own; this layer only reacts and reports.
