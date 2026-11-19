# app/protocol

The MIC workflow, independent of hardware.

- `mic_protocol.py`: protocol steps (serial dilution, inoculation within 5 minutes).
- `run_controller.py`: run state machine: setup → running → paused → done / interrupted.

Testable without the robot using `tests/fake_moonraker.py`.
