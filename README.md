# TomTom for Conquest of Azeroth

TomTom (2010 release for WotLK 3.3.5a) with changes that make it work on the **Conquest of Azeroth** (Ascension-based) client.

This is an unofficial compatibility fix. TomTom is by Cladhaire (with jnwhiteh); all credit for the addon goes to them.

## Install

1. Close the game.
2. Download this repository (Code → Download ZIP).
3. Copy the `TomTom` folder into `<your client>\Interface\AddOns\`, replacing any existing copy.

## What's changed for CoA

| Problem on CoA | Fix |
|---|---|
| The client ships its own `Astrolabe-0.4` (version = infinity) that numbers zones by **area ID** (Sunstrider Isle = 1241). It replaces TomTom's copy, so TomTom mixed area IDs with zone indexes | TomTom translates between the two (`TomTom:ZoneID`, `TomTom:CurrentCZ`) in `TomTom.lua`, `TomTom_Corpse.lua` and `TomTom_POIIntegration.lua` |
| Right-clicking the world map in CoA zones crashed TomTom (area ID looked up as a zone index) | Area-ID lookups above, plus a guard against a missing map name |
| The arrow disappeared while moving | Fixed together with the changes above |

Use it together with the CoA version of Zygor Guides Viewer (the `coa-zygor` repository) if you use Zygor: Zygor hands waypoints to TomTom in the zone numbering this version expects.

## Credits

TomTom by Cladhaire and jnwhiteh. The arrow model's license is in `TomTom/Images/ArrowLicense.txt`.

TomTom ships without a license file, so its authors keep their rights to it. This repository only exists to share the CoA compatibility changes. If you're one of the authors and want it taken down, please open an issue.
