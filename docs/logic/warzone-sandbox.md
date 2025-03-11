# tsg warzone-sandbox library

Documentation about the tsg warzone-sandbox library used for the scripting logic.

## Changelog

### 0.8.1
- Vehicle Grant logic queue update from every 1 second -> every 0.10 seconds.
- Vehicle Grant queue only spawns vehicle if the requesting unit is not dead.
- [13] Valkyrie: Motion tracker stays visible while zoomed.
- [41] Go At: Adjusted projectile velocity from 100 -> 120.
- Loadout hardlight weapons [3], [4], [5] & [9]: Adjusted reload speed scalar from 1.00 -> 0.75.
- [25] The Final Token: Ammo adjustment +50 (14+84)
- [6] ONI Battle Rifle: Remove movement speed trait, Weapon Damage 0.60, Ammo adjustment +34 (14+70)

### 0.8.2
- [25] The Final Token: Weapon Damage 0.52 -> 0.70, VFX: Beta Infected.
- [13] Valkyrie: Motion tracker disabled while zoomed.

### 0.8.3
- [11] Rush Bulldog: Weapon Damage 1.00 -> 1.01.

### 0.8.4
- Updated weaponGrant to have an extra 0.00 s delay in order to allow the event to be ran back-to-back without extra wait delays.
- Added listener for on-level Legendary Equipment detection for initial gathering of their object references. @@@@@@@@@
- Updated Legendary Equipment granting logic so they can be remotely granted to players via the grantEquipment event and the corresponding equipment number, instead of requiring a direct object reference.
- Updated debug brain to be more compartmentalized.
- Added setObjectVariables event to "Variable declarations" brain, in order to offload on-level Object Variable declarations by setting them inside a mode brain.
- Renamed Speed Boost traits to speedBoost1 & speedBoost2.
- Removed old weapon combination at index 45 from weaponTypes list, as it's currently an unallocated weapon.
- Updated grantAbilityBoost logic for Loadout Ammo to pull from weaponTypes list instead of manually set weapon type combinations.
- Updated enterVehicle logic (in grantVehicle) to only fire multiple times if the unit did not enter the vehicle after the first try.
