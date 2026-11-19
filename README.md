# Capstone-AST

A compact, benchtop robot that automates the MIC (minimum inhibitory concentration) antimicrobial susceptibility testing workflow: an 8-channel pipette on an X/Y/Z gantry, inside a transparent enclosure, run from a touchscreen.

## System overview

| Part | Choice |
|---|---|
| Main computer | Raspberry Pi 5 (Pi OS Lite) |
| Motion controller | BTT Octopus V1.1 running Klipper |
| Gantry motors | NEMA 17 steppers (X, Y, Z) |
| Pipette | NEMA 17 linear stepper (plunger), volume dial and tip-eject motors |
| Homing | Omron optical endstops |
| Power | 24 V supply, 5 V buck for the Pi |
| Safety | Hardware e-stop and door interlock cutting motor power through a relay |
| User interface | 5 in Raspberry Pi Touch Display 2, PySide6 app |

```
Touchscreen UI (PySide6)  →  Moonraker API  →  Klipper (Pi)  →  USB  →  Octopus  →  motors / endstops
```

## Repository structure

| Folder | Contents |
|---|---|
| `app/` | Python application on the Pi |
| `app/config/` | Deck layout and settings (YAML) |
| `app/robot/` | Moonraker client, motion and pipette commands |
| `app/protocol/` | MIC protocol steps and the run state machine |
| `app/safety/` | E-stop / door monitoring and run interruption |
| `app/data/` | Run logging (SQLite) |
| `app/ui/` | PySide6 touchscreen app; `screens/` holds each screen |
| `klipper/` | Klipper config files, copied to `~/printer_data/config` on the Pi |
| `cad/drawings/` | Mechanical drawings and the extrusion cut list |
| `cad/stl/` | 3D-printable parts |
| `docs/architecture/` | System and software architecture diagrams |
| `docs/electrical/` | Wiring diagram, Octopus pin map, cable list |
| `docs/testing/` | Accuracy and end-to-end test results |
| `docs/requirements/` | Requirements document |
| `legacy/` | Previous team's code, kept for reference while porting |
| `tests/` | Automated tests (run without hardware using a fake Moonraker) |
| `deploy/` | Pi setup: systemd service and install script |

## Getting started

Setup steps will be added as the software is built (see the GitHub issues). The planned flow:

1. Flash Raspberry Pi OS Lite (64-bit) to the Pi.
2. Install Klipper and Moonraker, and flash Klipper firmware to the Octopus.
3. Copy `klipper/` to `~/printer_data/config/`.
4. Install the Python dependencies and enable the UI service from `deploy/`.

## Working on the project

- Tasks are tracked as GitHub issues, grouped into three milestones: design freeze, bench bring-up, and prototype.
- Create a branch per issue and link pull requests with `Closes #N`.
- Do not commit secrets, local virtual environments or run databases (see `.gitignore`).

## Team

Tyler, Alison, Kevin, Karen, Celine, Mary
