# evcc Supercharged

A drop-in replacement for the evcc add-on. Configure evcc in its own web UI as usual; the
**Load management** tab holds the whole-house balancing.

## Install

1. Settings, Add-ons, Add-on store, ⋮, Repositories: add `https://github.com/felipefc10/hassio-evcc-supercharged`.
2. Install **evcc Supercharged** and start it. evcc creates a new database at `/config/evcc.db`.

Only one evcc may drive the chargers: stop any other evcc add-on first.

## Coming from the stock evcc add-on

Stop the old add-on and copy its `evcc.db` into this add-on's folder
(`addon_configs/<slug>_evcc_supercharged/`, reachable through the Samba add-on) before the first
start. Chargers, meters, vehicles and sessions come along unchanged.

## Moving load management between installations

Load management, Settings, **Export and import** writes one file with the installation, every
setting, the learned car behaviour and the burst log, and reads it back on another evcc.
The same data lives in `evcc.db`, so a Home Assistant backup of this add-on covers it.

## Requirements

- A single-phase installation. A loadpoint charging on more than one phase is refused and every
  loadpoint is held to the fail-safe limit.
- A grid meter in evcc, or a Shelly EM read directly (Gen1 `http://…/emeter/0`, Gen2
  `http://…/rpc/EM1.GetStatus?id=0`). The Shelly reports reactive power, so the apparent power the
  ICP trips on is exact.
- With a PV meter in evcc, cars may use solar surplus on top of the never-trip line; the solar
  modes of evcc keep working as usual.
