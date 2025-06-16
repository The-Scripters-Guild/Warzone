# Changelog

Changes between various updates to the Warzone mode, libraries and modules.

## Warzone

Changelog of the main Warzone mode.

### 0.3.2

Current state: Mode working fully, with some notable missing features:
- No REQ Room logic; loadouts given by random based on REQ Points
- No Core destroying logic
- No vehicles (on-level)

### 0.4.0

- Added custom 10-second soft kill boundary logic, as we can't use Soft Kill Volumes on Warzone maps due to a bug that hides the Objective Banner UI element when entering a Soft Kill Volume.
- Respawn time adjusted from 4 -> 8 s.
- Cleaned up zone AI nav creation code.

### 0.4.1

- Added a feature where staying close to a REQ station will grant players +7% ammo for their loadout weapons every second.

### 0.4.2

- Added Base Core destroying feature to be able to end the game after a team has control of all three zones.
- Adjusted boss kill audio when killing a Mythic 100-point boss to play the Mythic kill audio instead of the Legendary kill audio.
- Made the scenario nav marker text change to "Clear The Enemy Units" once the boss of the scenario has been killed. Known issue persists where killing just one boss in a two-boss scenario still changes the nav marker text.
- Added different icons for Silver, Legendary, and Mythic boss incoming nav markers.

### 0.5.0

- Changed base mode from Minigame to Minigame BTB in order to force a 30 tick rate due to facing performance concerns. The tickrate near the end of a match with a full lobby seems to drop to around 20, so keeping a low tick rate to begin with should lessen the visual impact of a dropped tick rate.

### 0.5.1

- Updated warzone-sandbox to 0.11.3.
- Added a check to prevent Marine spawn in a zone if the amount of players on the opposite team of the captured zone is greater than the amount of players of the zone's team are present within the zone boundary. This prevents Marines from constantly spawning in the zone, which made the capturing process very difficult.
- Added debug player index number display to custom soft kill docked nav marker to try and understand an issue where the death loop persists for players when someone joins in progress.
- Added debug print to killfeed upon zone capture showing the number of zones each team has captured to try and understand an issue where the core would get exposed in a situation where a team does not control all three zones.

### 0.5.2

- Updated warzone-sandbox to 0.11.4.
- Grunt Ultra damage adjusted from 1.00 to 0.01, as they are shooting a custom projectile weapon and shouldn't deal other damage than what the projectile does.
- Updated custom soft kill feature to use Generic Zones instead of Area Monitors; reduced node count and improved ease of use.

### 0.5.3

- Added feature to make specified objects change their team based on the captured zone's team.

### 0.5.4

- Updated warzone-sandbox to 0.11.5.
- Added audio for damaging the core, and contesting and capturing zones. Added explosion effects to destroying the core.

### 0.5.5

- Changed core damaging logic to account for new core being made out of Boss Choppers.

### 0.6.0

- Updated warzone-sandbox to 0.11.6.
- Attempted fix at custom soft kill player join in progress issue.
- Excluded players joining in progress from any player execution scripts that need to track only valid players.

### 0.6.1

- Updated warzone-sandbox to 0.14.0
- Renamed DummyObject events to be more readable

### 0.6.2

- Updated warzone-sandbox to 0.14.1
- Fixed custom soft kill player join in progress issue.

## tsg warzone-sandbox library

Changelog for the tsg warzone-sandbox library used for the sandbox scripting logic.

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

### 0.11.3

- [7] ONI Bandit: Weapon Type: M392 Bandit + Impact Commando -> M392 Bandit + MA40 Longshot, Weapon Damage: 1.41 -> 2.19, Ammo Adjustment: -27 -> 0
- Adjusted requestWeapon event artificial ending time from 0.016 seconds to 0.05 seconds to account for the server tick rate dropping to a minimum of 20 ticks per second. This ensures proper functioning of granting two custom weapons with ammo adjustment back-to-back.
- Prevented Rocket Hog projectile gathering area monitor from accidentally gathering a grenade.

### 0.11.4

- Made setPlayerIndex event trigger an async event to update the player index, as without an async event, players joining in progress would freeze the execution of the For Each Player loop of setting the index. This caused bad data if players tried to call their index at the time when it was being updated and frozen.

### 0.11.5

- Made setPlayerIndex event only trigger for players who are not in the progress of joining the game. Event triggers when a player spawns, and indexes players not in the progress of joining to prevent execution freezes.

### 0.11.6

- Added listing of players still joining into a match, and excluded them from any player execution scripts that need to track only valid players.
- Removed debug location teleport; still kept debugCounter logic.

### 0.12.0

- Added Mutilator
- Added Mutilator variant: [22] Myriad Arm (REQ 5)
- Updated mislabeled Fuel Rod weapon types due to update breaking them
- Removed Ability Boost: [7] Loadout Ammo
- Added Ability Boost: [7] Spy

### 0.13.0

- Added five new vehicle variants
  - [13] Extermination Gungoose (REQ 4)
  - [14] Fusion Rocket Hog (REQ 7)
  - [15] Plasma Warthog (REQ 6)
  - [16] Phantom Wasp (REQ 8)
  - [17] Banishing Wasp (REQ 9)
- Added seven new weapon configs to support new vehicle variants
  - [119] Rocket Hog Weapon
  - [120] Wasp Weapon
  - [121] Rocket Hog Weapon + Backdraft Cindershot
  - [122] Rocket Hog Weapon + Rapidfire Pulse Carbine
  - [123] Rocket Hog Weapon + Ravager Rebound
  - [124] Rocket Hog Weapon + Unbound Plasma Pistol
  - [125] Wasp Weapon + Scatterbound Heatwave
- Added UI message names for all vehicles
- Added UI message names for all remaining weapons

### 0.14.0

- Fixed powerup timers so that applying multiple powerups don't overlap, and their timer can be extended if the same powerup is activated whilist it's already active.
- Added lists for weapon, equipment, ability boost, and vehicle REQ and Game State values.
- Turned off weapon name splash as it was getting annoying.
- Extended weaponGrantActive bool duration from 0.4 to 0.6 s to try and avoid accidental firing issues in high latency matches with projectile weapons that need an instant reload such as the Banish Off Balaho.
- Removed custom preventEquipmentUsage logic as it's redundant.
- Renamed DummyObject events to be more readable.

### 0.14.1

- Fixed custom soft kill freezing when players were joining in progress.
  - Replaced playersJoining list with joinedPlayers, so reverse logic. JOIP players were still being caught by Get All Players otherwise, and freezing the thread.
- Added everyNTicks loop.
- Made checkHeldWeapon loop be every 2 ticks instead of 1 to see if it's the main impact for low tick rate in 15+ player matches.
