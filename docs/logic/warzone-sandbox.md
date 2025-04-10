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

### 0.9.0

- Updated weaponGrant to have an extra 0.00 s delay in order to allow the event to be ran back-to-back without extra wait delays.
- Added listener for on-level Legendary Equipment detection for initial gathering of their object references.
- Updated Legendary Equipment granting logic so they can be remotely granted to players via the grantEquipment event and the corresponding equipment number, instead of requiring a direct object reference.
- Updated debug brain to be more compartmentalized.
- Added setObjectVariables event to "Variable declarations" brain, in order to offload on-level Object Variable declarations by setting them inside a mode brain.
- Renamed Speed Boost traits to speedBoost1 & speedBoost2.
- Removed old weapon combination at index 45 from weaponTypes list, as it's currently an unallocated weapon.
- Updated grantAbilityBoost logic for Loadout Ammo to pull from weaponTypes list instead of manually set weapon type combinations.
- Updated enterVehicle logic (in grantVehicle) to only fire multiple times if the unit did not enter the vehicle after the first try.

### 0.9.1

- Reorganized code in the init brains to make isolating parts of the code easier by deleting entire mode brains.

### 0.9.2

- [1] Marksman Sidekick: Weapon Type Mk50 Sidekick + Impact Commando, Weapon Damage 0.60, Ammo Adjustment -50 (40+60).
- [8] Banished Bandit -> Tovarus Artifice.
- [10] Lost Commando -> ONI Commando.
- [11] Rush Bulldog: Weapon Damage 1.15.
- [12] Valor Off Dinh: VFX Beta Infected.
- [28] ONI Ranger: Weapon Damage 0.38.
- [42] Forklift Warrior -> ONI Assault Rifle: Weapon Type MA40 Assault Rifle + Impact Commando, Weapon Damage 0.38, Ammo Adjustment -70 (40+100). Remove all other traits.
- Fixed an inconsistency with Legendary Equipment gathering at round start by adding a delay to the initial gathering logic.

### 0.9.3

- [1] Marksman Sidekick: Corrected Weapon Damage from 1.10 to 0.60.
- [13] Valkyrie: Ammo Adjustment 42 (4+12).
- [26] Phantom Assassin: Ammo Adjustment: -35 (6+0).
- [34] Sentry Off Writh 'Kul: Camo trait while normal and more intense while zoomed.
- [36] Power Off Jega Rdomnai: Sprint speed increase.
- [39] Knight Off Zeretus: Ammo Adjustment: 70 (2+6)
- [44] Broken Installation: Projectile shot count: 2, config: 2, Ammo Adjustment: -20 (20+0)
- [8] Tovarus Artifact: VFX: VIP
- [15] Exterminating Hazard: VFX: VIP
- [40] Guard Off Doisac: VFX: Alpha Infected
- [46] Reward Off Hyperius: VFX: VIP
- [47] Scorpion Shot: VFX: Alpha Infected
- [48] Headhunter: VFX: VIP
- [49] Artifact Off Tremonius: VFX: Beta Infected
- Remove [22] Stunning Bounty from sandbox

### 0.9.4

- Made stacking Speed Boost powerups possible up to 4.
- Adjusted Speed Boost traits.
- Adjusted Upgraded Walking traits.
- Adjusted Upgraded Sprinting traits.
- [32] Spartan Sandwich: Melee Damage 2.00 -> 0.70.
- Updated VFX removal logic order to see if it fixes some inconsistencies with VFX removal.

### 0.10.0

- Overhauled skinless weapon grant system so each player has their own "weapon carrier clone", which allows for skinless weapons to be granted simultaneously to multiple players with no queue. Also the risk of incorrect weapon grants due to the queue is negated.
- Added a 1/59 s delay in the weaponGrant event to reduce order weapon grant order issues per player.

### 0.10.1

- Reorganized mode brains so there's no blue brains, which indicate actions that use the events from the library, as the library in itself shouldn't have events like that.

### 0.10.2

- [21] Decaying World: Weapon Damage 1.87 -> 1.89
- [35] Cutlass Off Doomfruit: Multiple adjustments to make UX communication better, and to buff the weapon

### 0.10.3

- [12] Power Arm -> Allied Monitor: Overhauled powerup to be a third person powerup.
- [14] Headhunter Guard: VFX VIP -> Beta Infected.
- [3] Expert Marksman: Melee Recovery Speed 1.10 -> 1.60.
- Accounted for resetting multiple variables to make multiple rounds not break functionality.

### 0.11.0

- Added DummyObject variables for an object, player and weapon clones. This addition can double the DummyObject creation from other scripts and needs to be accounted for, so a major change.

### 0.11.1

- Changed `projectilesEnabled` Boolean Variable scope from Global to Object, which somehow hasn't caused noticeable issues with the wrong scope.

### 0.11.2

- Adjusted the amount of created Weapon Carrier Clones from 24 to 28 due to some players getting a higher than 24 index if the match has more than 24 total players due to bots being present. Capped at 28 instead of 32, as this is a rare occasion, and not standard. Adding more clone bipeds on the map reduces the amount of total units that can be present on the map including vehicles.