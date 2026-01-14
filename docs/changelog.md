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

- Updated warzone-sandbox to 0.14.0.
- Renamed DummyObject events to be more readable.

### 0.6.2

- Updated warzone-sandbox to 0.14.1.
- Fixed custom soft kill player join in progress issue.

### 0.6.3

- Updated warzone-sandbox to 0.14.2.
- Fixed an issue that made the tick rate drop to 15 due to a continuous event looping too large of a list.
- Changed base mode to Arena to utilize a 60 tick dedicated server.
- Fixed an issue where players would be frozen at Gameplay Start due to a large event loop running.

### 0.6.4

- Updated warzone-sandbox to 0.14.3.
- Added Marines spawning in base when the core is exposed.
- Fixed non-human AI stragglers in Armory or Fortress not dying if it was captured when they were still alive.
- Removed zone capture number debug.
- Added Generic Zones for bases (on-level script).

### 0.6.5

- Updated warzone-sandbox to 0.14.5.
- Updated core mode to BTB, 30 tick.

### 0.6.6

- Updated warzone-sandbox to 0.14.6.

### 0.6.7

- Force kill Marines in home Base 10 seconds after an exposed core is covered to save on AI count.
- Made any AI that drop the AI variant of the [37] Spike Off Thav 'Sebarim be granted it back to them so they don't use the wrong guns and fire the spike projectile.
  - Same can't be done for the Fuel Rod Grunt's weapon, as if they go in the Plasma Grenade Grunt Hug mode and drop their weapon, it can't be granted back to them with the same logic. The Fuel Rod Grunts don't seem to pick up other weapons luckily.
- Added a feature for players stuck inside enemy bases to escape by getting close to the inside of the shield doors.

### 0.6.8

- Updated warzone-sandbox to 0.14.7

### 0.6.9

- Updated warzone-sandbox to 0.14.8
- Added two new AI: [25] Boss Chak 'Lok & [26] Boss Hyperius
- Added new AI Encounter: [12] Elite Encounter, Mythic.
- Adjusted AI: [16] Brute Berserker, Chosen.
- Adjusted AI Encounter: [7] Brute 2 Encounter, Legendary.
- Added REQ scoring for capturing a zone (currently on-level).

### 0.6.10

- Adjusted resistance values of Hyperius and Berserker Brute, Chosen.
- Decreased Chak 'Lok weapon damage.

### 0.6.11

- Adjusted resistance and weapon damage values of Hyperius and Berserker Brute, Chosen.

### 0.7.0

- Updated warzone-sandbox to 0.15.1
- Adapted new weapon grant at position variables.
- Made any dropped Brute Scrap Cannon turn into a [31] The Champion. Escharum drops the weapon.

### 0.7.1

- Updated warzone-sandbox to 0.15.2

### 0.7.2

- Updated warzone-sandbox to 0.15.3
- Replaced AI [18] Brute Sniper, Heavy with [18] Brute Chieftain Turret.
- Replaced AI [22] Boss Tremonius with [22] Hunter, Banished.
- Replaced weapon of AI [12] Boss Thav 'Sebarim from [37] Spike Off Thav 'Sebarim with [16] Pulse Wave.
- Replaced Boss Tremonius in AI Encounter [6] with two Hunter, Banished AI.
- Added [18] Brute Chieftain Turret AIs to encounters [6], [9], [10] and [11].

### 0.7.3

- Updated warzone-sandbox to 0.16.0

### 0.7.4

- Updated warzone-sandbox to 0.16.1
- Made Boss AI drop predetermined loot on death.

### 0.8.0

- Updated warzone-sandbox to 0.17.0
- Changed respawn delay from 8 s to Instant.
  - To support spawn selection logic and custom respawn delay via script.
- Changed base mode to BTB, 30 tick rate.
  - After extensive testing, we've found 30 tick to be the most reliable for the experience.

### 0.9.0

- Updated warzone-sandbox to 0.20.0
- Updated AI spawn overrides to have the AI active from the beginning.
- Accounted for +10 change in weapon config values in the loadout ammo grant near REQ stations.
- Removed "custom soft kill" code, and replaced related objects on-level with Soft Kill volumes.
  - Changed due to new "Prompt Widget" messaging location that isn't affected by an issue with the Objective Banner message disappearing when exiting a Soft Kill volume.
- Updated some icons.
- Added AI Spawner array to Mode Prefab. Will require only one AI Spawner on-level in an area with Nav Mesh. (All AI will spawn on this so it should be hidden from the gameplay area)
- Adjusted coreDestructionSpawner to be the same Dummy Spawner that's used for the rest of the AI as a spawn location.
- Reduced REQ point grant amounts by 50%; kept point drip value the same.
- Made REQ Station loadout weapon ammo grant only work for players who can access the station.

### 0.9.1

- Adjusted Point grant amounts: Player kill: 0.15 → 0.10, AI kill: 0.08 → 0.05, every second drip: 0.03 → 0.02.

### 0.9.2

- Made AI be inactive until Gameplay Start so players don't die in the intro sequence.

### 0.9.3

- Updated warzone-sandbox to 0.21.0
- Increased passive Point grant amount every second: 0.02 → 0.023.

### 0.9.4

- Made AI inactive before Gameplay Start so they don't move around too much from their intended spawn locations before Gameplay Start.

### 0.9.5

- Updated warzone-sandbox to 0.21.1
- Changed AI inactivity before Gameplay Start to being deaf and blind as they were still moving in similar ways after Gameplay Start.

### 0.9.6

- Added warning docked nav marker for players whose core is being damaged.
- Increased density of warning sounds when a core is being damaged.

### 0.9.7

- Added an alternating Prompt Widget message while dead that shows between "Open Menu" and "Points X/Y" with the player points and Game State, just like it shows while alive.
- Made core destroying docked nav marker disappear if core health reaches 0%.
- Removed debug print to killfeed when AI count reached max of 32.

### 0.10.0

- Updated warzone-sandbox to 0.21.3
- Added failsafes to coreDestruction event that kill two first AI so the Sentry Bosses (explosion) can spawn, and used For N Iterations function to hopefully not cause a thread freeze if something in the AI spawning process fails, so the game at least ends.
- Adjusted wait time between spawning an AI and assigning the AI's squad to the closest Move Zone from 2 → 5 seconds in an effort to fix the Eagle Armory AI sometimes getting assigned to the Move Zone under Eagle Armory.
- Adjusted setClosestSpawnPoint to look through all spawn points instead of just Team 8 ones as some spawn points designated for AI are on Neutral team.
- Added a fallback for teleporting AI back to their designated spawn point if they teleport back to the AI Spawner platform for some reason such as the Harbinger during its scripted sequence that's pulled from the Campaign.
- Added audio ques for damaging the core past thresholds of 75%, 50% and 25%.
- Added music to the start of the game, and Legendary and Mythic boss fights.
- Overhaul to the amount of Game States:
  - "gameState" changed to "level".
  - First level starts at 1 instead of 0
  - Last level is 9 instead of 6.
  - Total 9 levels instead of 7.
- Overhaul to the total team point thresholds per Game State/Level:
  - 1: 0
  - 2: 50
  - 3: 100 → 200
  - 4: 250 → 400
  - 5: 375 → 600
  - 6: 625 → 750
  - 7: 800 → 850
  - 8: --- → 950
  - 9: --- → 1000

### 0.10.1

- Updated warzone-sandbox to 0.21.4
- Adjusted custom starting music to start after Gameplay Start as othewise it overlaps with the built-in starting music. The built-in mode music needs to stay in the mode to reduce custom scripted music logic.

### 0.10.2

- Adjusted starting music to stay on until the 20 second mark.
- Fixed issue in boss music that was causing a singular music to always play when any encounter value under 5 started.

### 0.10.3

- Adjusted Thav 'Sebarim's Weapon Damage trait from 0.40 → 0.80 so the Pulse Wave he wields does more damage; seems like AI have lowered damage by default.
- Adjusted personal score grant from killing a "Brute Chieftain Turret" from 200 → 300.

### 0.10.5

- Updated warzone-sandbox to 0.21.5
- Replaced custom weapon types that are given to bosses to be the ones pulled from the weaponTypes list instead of custom weapon type combinations so they update correctly with changes.
- Added "Level: x" display to Objective Banner to provide more communication on what the global Level is.
- 0.10.4 is an invalid string in Halo Infinite.

### 0.10.6

- Major fix to loot drops where 0-values were not being accounted for and the secondary weapon, equipment and grenade drops were not being correctly given. This issue caused Mk50 Sidekicks to be dropped in every loot drop, which were persisting throughout the entire match as they have a 10000 second despawn time in the code, and were most likely causing issues that resulted in the total dropped weapon limit being reached earlier than expected.

### 0.10.7

- Changed AI Spawners to Team 8 (Hazard) and excluded other teams than Eagle and Cobra from gaining boss kill benefits. This fixes boss loot drops on for automatically killed AI.
- Changed weapon despawn time for loose granted weapons from 10000 s to 120 s.

### 0.10.8

- Fixed core 25% health audio playing swapped voice lines for each team.

### 0.10.9

- Fixed issue with marines not being able to spawn after enemies had been in the zone when the capturable zone logic was changed from TotalControl to Stronghold.

### 0.10.10

- Updated warzone-sandbox to 0.21.6.

### 0.10.11

- Adjusted "Enemy Destroying Core" message to "Enemy Destroying the Core" when your team's core is being damaged.
- Changed the AI encounter UI Nav Markers to Neutral team with an enemy colored outline so that the nav markers are more distinguishable from enemy captured base nav markers. The new nav markers now display the progress bar as the AI count out of 10, as the max AI count in a Warzone encounter is 10.
- Added decimal accuracy to the "Level" display in the Objective Banner, so players can get a more accurate idea on the level progression.

### 0.10.12

- Updated warzone-sandbox to 0.21.7.
- Made nav markers displaying remining AI in a zone to correctly update for players in vehicles.


### 0.10.13

- Updated warzone-sandbox to 0.21.8.
- Optimized remaining AI nav marker in zone logic.
- Optimized allowMarineSpawn logic for detecting players in a zone.

### 0.10.14

- Updated warzone-sandbox to 0.21.9.
- Updated warzone-radial to 0.6.1.

### 0.10.15

- Updated warzone-sandbox to 0.22.0.
- Updated warzone-radial to 0.6.2.
- Decreased Hunter grenade resistance from 4.00 to 2.00 so they need 3 Frag Grenades to kill.

### 0.10.16

- Added support for changing between normal Warzone and Warzone Ultra with one number variable "progressionMultiplier"; 1.00 is normal and higher values trigger Warzone Ultra game progression.

### 0.10.17

- Updated warzone-sandbox to 0.22.1.
- Added feature to force players on teams other than Eagle or Cobra to be put on either team at random.
- Fixed players being able to damage their own core with cloned projectiles.

### 0.10.18

- Updated warzone-sandbox to 0.22.2.

### 0.10.19

- Updated warzone-sandbox to 0.22.3.

### 0.10.20

- Updated warzone-sandbox to 0.22.4.
- Adjusted starting music to play for longer.
- Adjusted end fade time of boss music to be longer.

### 0.10.21

- Updated warzone-sandbox to 0.22.5.
- Updated warzone-radial to 0.6.4.

### 0.10.22

- Updated warzone-sandbox to 0.22.6.
- Increased passive and active personal point gain:
  - Passive point gain: Every 43.5 s → 35.1 s (0.023 → 0.0285). Level increase 0.00 → 1.00.
  - Active point gain: Player Kill 0.10 → 0.12. AI kill 0.08 → 0.10

### 0.11.0

- Updated warzone-sandbox to 0.22.7.
- Added a docker nav marker on the left side of the screen displaying the Level.
- Added docked nav marker spacer feature.
  - Intentionally did not include spacer removal feature for the "AI remaining" and "Enemy Destroying the Core" nav markers cause it's too complicated. When these nav markers are on screen, the "Level" nav marker on the left of the screen will shift more to the left.
- Decreased passive personal point gain: Every 35.1 s → 40.0 s (0.0285 → 0.025).

### 0.11.1

- Updated warzone-sandbox to 0.22.8.
- Changed boss elimination message in the killfeed from "Enemy/Your Team Eliminated A Boss" → "Player Eliminated the Boss" where "Player" is the player who killed the boss. The player name has the team's color so it's also gets across which team killed the boss.
- Added extra UI messaging for notifying about destroying the enemy core or defending your core when they're exposed.

### 0.12.0

- Added zone team assignment, tempDisabledSpawns, spawn interruption, and station team assignment logic to mode code from on-level.
- Added station object list creation logic to mode code from on-level.

### 0.12.1

- Adjusted AI:
  - [15] Brute Minor
    - Direct Damage Resistance: 4.30 → **2.50**

- Adjusted zoneRefresh event nav marker temporary position from Z:-10000 to Z:10000 so players are less likely to see the nav marker flash on their screen as it's above their view instead of under.
- Adjusted AI encounter Nav Marker distance visibility from 170 → 250 m.
- Made the "Select Loadout" Nav Marker on item stations be only visible to the players on the team that own the zone or Home Base.
- Added 0.80 point gain for all players after the Home Base AI has been cleared.
- Added extra announcer audio after Home Base has been cleared.
- Added forceful kill of Home Base AI after 30 s from Gameplay Start to ensure the game progression doesn't halt.

### 0.12.2

- Adjusted weapon despawn time of the AI loot drops from 120 s to 40 s to reduce chances of reaching dropped item limits.
- Removed extra 1.0 point gain for all players after a level increase.
- Increased Level 9 total point threshold from 1000 → 1100.
- Added informative docked Nav Marker to players 4 s after death messaging to use the Custom Input to open the menu as some people aren't noticing the Prompt Widget on the left.

### 0.12.3

- Decreased Level 2 total point threshold from 50 → 25.
- Adjusted point grant from capturing zones to only happen for the players who contribute to capturing the zone for the first time.
- Increased point grant from capturing zones from 0.50 to 1.00.
- Disabled spawning on front Home Base spawns until the Home Base is captured.
- Removed Bot Backfill code from the mode.

### 0.13.0

- Updated warzone-sandbox to 0.23.1.
- Updated warzone-radial to 0.7.2.
- Fixed inaccurate Level Nav Marker decimal when approacing Level 9.
- Adjusted Hunter Equipment loot drop from [12] Allied Monitor + [1] Drop Wall → **[14] Headshot Shielding + [1] Drop Wall**

### 0.13.1

- Updated warzone-sandbox to 0.23.2

### 0.13.2

- Updated warzone-sandbox to 0.24.0
- Updated warzone-radial to 0.7.4

### 0.13.3

- Updated warzone-sandbox to 0.25.0
- Updated warzone-radial to 0.8.0
- Removed boss loot drops as they were not being utilized enough in gameplay and we are short on available mode file size budget.

### 0.13.5

- Updated warzone-sandbox to 0.25.1
- Updated warzone-radial to 0.8.1
- 0.13.4 is an inappropriate string in Halo Infinite

### 0.13.6

- Added AI Spawners to the mode scripts

### 0.13.7

- Updated warzone-sandbox to 0.25.2
- Fixed "Objective Start, Good Luck!" Audio playing during the intro cameras of maps where the gameplay doesn't start from the Home Bases.

### 0.13.8

- Updated warzone-sandbox to 0.26.0
- Updated warzone-radial to 0.8.2
- Fixed Grunt Ultra not dropping a [38] Hunters Right Hand on death.

### 0.13.9

- Updated warzone-sandbox to 0.26.1
- Updated warzone-radial to 0.8.3
- Made players start with 9 points if Warzone Ultra toggle is on.
- Adjusted damage taken multiplier for the Home Base core from 0.15 → **0.18** which means that players need to do ~83% of the previous damage to the core to fully destroy it compared to the previous health.

### 0.13.10

- Updated warzone-sandbox to 0.26.2
- Updated warzone-radial to 0.8.4

### 0.13.11

- Updated warzone-sandbox to 0.26.3
- Updated warzone-radial to 0.8.5
- Made Gravity Hammers do 0.3x damage to the core
- Added 0.50 s delay to item station team assignment after zone capture to try and fix issue where station teams sometimes don't get assigned after zone capture








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

### 0.14.2

- Fixed issue causing joinedPlayers list to combine with a list of AI units.
- Fixed Agoat rocket impulse not being applied correctly.
- Extermination Gungoose REQ 6 -> 5.

### 0.14.3

- Changed checkHeldWeapon loop from every two ticks to every three ticks to keep a full lobby at a 60 tick rate.

### 0.14.4

- Added new weapon [50] Scorpion Tail + Backdraft Cindershot.

### 0.14.5

- Added name "Fusion Off Legkolo" for [50] weapon.

### 0.14.6

- Added separate checkHeldWeapon loop for only projectile weapons that runs every tick; disconnected from the normal loop that runs every 3 ticks.

### 0.14.7

- Added Infected Beta VFX For [50] Fusion Off Legkolo
- Changed Rockethog Tier from 5 to 4.

### 0.14.8

- Made vehicle granting logic not require a unit to enter the vehicle to grant a custom weapon.

### 0.15.0

- Added support for granting Grenades (1-4).
- Added support for granting Equipment and Grenades at position.
- Added option for setting item velocity when spawned at position.
- Added weapon type for Brute Scrap Cannon (116)

### 0.15.1

- Added a condition for only running the checkHeldWeapon loop if the player's previously held weapon type has changed, instead of running it every 3 ticks continously. This should fix the performance issues.
  - Changed the checkHeldWeapon loop to be every tick now that it's much more efficient.
- Removed every3Ticks loop.

### 0.15.2

- onWeaponFired loop frequency changed from every 0.05 seconds to every tick.
- Adjusted [43] Banish Off Balaho projectile velocity from 2000 to 3000.
- Fixed trait application for weapons that needed constant checking about the player being in a state like zoomed or airborne.
- Fixed [34] Sentry Off Writh 'Kul zoomed in full camo persisting if the player switched weapon as they were zooming.

### 0.15.3

- Made ammoAdjustment script work when picking up weapons as a refill pickup.
  - Prevents weapons from having too much ammo off refill pickup.
- Granting empty vehicle at position of object made not require an Object input for the event.

### 0.16.0

- Changed how the checkHeldWeapon loop runs in order to reduce the checks majorly and improve server performance.
- Made checkHeldWeapon loop check run every 3 ticks again if the player's weapon has changed to save on more performance as the loop doesn't need to run every tick.
- Changed Core Banshee → Mid Banshee.
- Changed Core Ghost → Mid Ghost.
- Added 10 more empty slots for custom weapons.
  - Warning!: Weapon values past 50 were all shifted by +10; documentation updated.
- Added 3-second delay between vehicle spawns when using grantVehicle.

### 0.16.1

- Added Weapon: [118] Vestige Carbine.
- Added Weapon: [8] REQ 7 Carbine variant.
- Added Weapon: [45] REQ 2 Carbine variant.
- Added Vehicle [18] Falcon.

### 0.17.0

- Adjusted names of Weapons:
  - [2] Key Off Speed → Key Of Speed
  - [12] Valor Off Dinh → Valor Of Dinh
  - [15] Exterminating Hazard → Overloaded Pulse Carbine
  - [17] Shot Off Barroth → Spire Of Barroth
  - [18] Eayn Carbine → Eayn Stalker Rifle
  - [20] Attack Off Iratus → Rage Of Iratus
  - [21] Decaying World → Decaying Charge
  - [22] Myriad Arm → Blinding Payload
  - [24] Extermination Off Infection → Focus Beam
  - [28] ONI Ranger → ONI Avenger
  - [30] Doom Off Reach → Doom Of Reach
  - [33] Defender Off Sanghelios → Guardian Of Sanghelios
  - [34] Sentry Off Writh Kul → Sentry Of Writh Kul
  - [35] Cutlass Off Doomfruit → Rogue Juggernaut
  - [36] Power Off Jega Rdomnai → Demon
  - [37] Spike Off Thav 'Sebarim → Spike Of Thav 'Sebarim
  - [38] Infiltrator Off Worlds → Hunters Right Hand
  - [39] Knight Off Zeretus → Rain Of War
  - [40] Guard Off Doisac → Exterminating Frenzy
  - [41] Go At → A Go At
  - [43] Banish Off Balaho → Banish Of Balaho
  - [44] Broken Installation → Thunderstorm
  - [46] Reward Off Hyperius → Light Of Doisac
  - [47] Scorpion Shot → Scorpion Tail
  - [49] Artifact Off Tremonius → Volcanic Oasis
  - [50] Fusion Off Legkolo → Gamma Shot
- Adjusted names of Equipment:
  - [14] Headhunter Guard → Headshot Shielding
- Adjusted names of Ability Boosts:
  - [1] Heal Boost → Auto Medic
  - [3] Expert Marksman → Dexterity
  - [8] Frag Grenade Operator → Frag Grenade Specialist
  - [9] Spike Grenade Operator → Spike Grenade Specialist
  - [10] Plasma Grenade Operator → Plasma Grenade Specialist
  - [11] Dynamo Grenade Operator → Dynamo Grenade Specialist
- Added storage of 8 cloned spawn points, each assigned to each possible Team.
- Added Vehicle: [18] Falcon.
- Added Vehicle: [19] Dragon.
- Added Vehicle Weapon: [136] Wasp Weapon + Pursuit Hydra.

### 0.18.0

- Removed storage of 8 cloned spawn points, each assigned to each possible Team.
- Fixed old Powerup Equipment names in Object Variables.
- Removed declarations for weapon-, equipment, ability boost- & vehicle names and points as they're not needed in the sandbox code; retained four custom powerup names in code.
- Removed redundant declaration for legendaryEquipmentDispensers.
- Updated mode respawn time to instant.

### 0.18.1

- Added Weapon: [51] Seeking Hydra.

### 0.18.2

- Added Weapon: [52] Siege Bandit.

### 0.18.3

- Added Weapon: [53] Cure Of The Haunted.
- Reduced ammo capacity of [52] Siege Bandit: 14+56 → 14+42

### 0.19.0

- Added docked Nav Markers displaying remaining time of powerups when activated, including a custom one for Active Camouflage.
  - 24 total Nav Markers reserved for simoultaneous use by all players.
- Changed checkHeldWeapon loop from every 3 ticks to every tick.
- Changed chechHeldWeapon loop side event from every 3 ticks to every 0.10 seconds.

### 0.19.1

- Added a list of aerial vehicle grant values.

### 0.20.0

- Added weapon objects to the Mode to offload them from the on-level budget and to allow all custom weapon types to be spawned on any map.
- Changed base mode to Minigame BTB to limit the tick rate to 30.
- Organized brains in the Mode Prefab.

### 0.21.0

- Removed weapon objects from the mode due to issues with Object Reference ordering causing the weapons to not spawn like they should.
- Reduced automatic weapon despawn time from 40 → 30 s as players were spawning with no weapon on rare occasions in Warzone playtests.
- Reduced sprint speed of upgradedSprinting Ability Boost

### 0.21.1

- Increased projectile speed of [38] Hunters Right Hand from 250 → 350.

### 0.21.2

- Increased weapon damage of:
  - [1] Marksman Sidekick: 0.60 → 0.66
- Replaced weapon: [45] Tactical Carbine:
  - Weapon Type: Vestige Carbine + MA40 Longshot
  - Weapon Damage: 1.20
  - Ammo: 25+40

### 0.21.3

- Increased Motion Sensor distance while using [2] Upgraded Sensors from 32 m to 40 m.
- Updated resetVars event to split into resetVars_unit.
- Reverted automatic weapon despawn time from 30 → 40 s as it did not seem to fix the issue with player spawning with no weapon, and was leading to weapons despawning too fast for Warzone gameplay.

### 0.21.4

- Added new weapon:
  - [54] Duelist Plasma Pistol
- Adjusted weapon type of [14] Hardlight Plasma Pistol: Plasma Pistol + Arcane Sentinel Beam → Original Plasma Pistol + Arcane Sentinel Beam.
- Adjusted weapon damage of:
  - [12] Valor of Dinh: 2.90 → 2.33
  - [45] Tactical Carbine: 1.20 → 1.60

### 0.21.5

- Increased amount of reserved carrier clones from 28 → 36, and added debug to show player index during grantWeapon event for custom weapons to try and debug weapons not spawning issue.

### 0.21.6

- Adjusted ammo of weapons:
  - [13] Valkyrie: 4+12 → 4+10.
  - [68] Elite Bloodblade: 100% → 25%.
  - [46] Light Of Doisac: 4+16 → 4+8.
- Increased damage of [46] Light of Doisac: 2.60 → 2.84.
- Adjusted grenade count of Ability Boosts:
  - [9] Spike Grenade Specialist: 2 → 3.
  - [10] Plasma Grenade Specialist: 3 → 2.
  - [11] Dynamo Grenade Specialist: 3 → 2.
- Reduced amount of reserved carrier clones to 24 and removed player index debug.
- Added a list for Observer Players and included exclusions for them in scripts.
- Changed wait delay on requestWeapon, requestWeapon_pos, removeVFX and extract-enter events from 0.05 → 0.0666 s due to it being a value divisible by both 60 and 30 tick rate.

### 0.21.7

- Adjusted ammo of [68] Elite Bloodblade: 25% → 40%
- Adjusted movement speed with turret of [34] Sentry Of Writh Kul: 1.55 → 1.42

### 0.21.8

- Added new weapon: [55] Brute Carbine (tier 2).
- Overhauled [45] Tactical Carbine → [45] Kig-Yar Carbine.
- Increased damage of weapons:
  - [5] Hardlight Battle Rifle: 1.29 → 1.55
  - [9] Hardlight Commando: 1.72 → 1.75
- Buffed [4] Hardlight Avenger:
  - Reload Speed: 0.75 → 1.00
  - Ammo: 80+80 → 80+160
- Increased health vampirism factor of [11] Health Steal: 0.40 → 0.90.

### 0.21.9

- Adjusted [21] Decaying Charge:
  - Movement Speed: 1.10 → 1.00.
  - Ammo: 12+36 → 12+20.

### 0.22.0

- Adjusted vehicle configs:
  - [12] Mid Ghost: Health to 60% on spawn
  - [13] Extermination Gungoose: Damage: 1.00 → 1.50 for driver
  - [16] Phantom Wasp: Damage: 1.00 → 1.50 for driver, 5 sec health regen
  - [17] Banishing Wasp → Moonlight Wasp
  - [19] Dragon: Damage: 1.00 → 2.00 for driver, 5 sec health regen
- Added new vehicles:
  - [20] Undead Ghost (Tier 7)
  - [21] Divine Banshee (Tier 8)
  - [22] Incursion Banshee (Tier 9)
  - [23] Carrier Falcon (Tier 3)
  - [24] ONI Rockethog (Tier 6)
- Added new vehicle weapons:
  - [137] Rocket Hog Weapon + Scatterbound Heatwave
  - [138] Wasp Weapon + M41 Tracker
  - [139] Rocket Hog Weapon + Volatile Skewer
- Adjusted [5] Upgraded Walking Ability Boost:
  - Movement Speed: 1.20 → 1.10
  - Jump Height: 1.25 → 1.15
  - Sprint Speed, Top Speed Scalar: 0.90 → 1.00
- Increased damage of [55] Brute Carbine: 0.30 → 0.35
- Adjusted [15] Overloaded Pulse Carbine:
  - Weapon Damage: 1.70 → 3.00
  - VFX: VIP → Infected Beta
- Assigned shot cloned projectiles to the team of the unit that shot them.

### 0.22.1

- Adjusted [22] Incursion Banshee damage: 1.00 → 1.50.
- Removed secondary rockets fire from [17] Moonlight Wasp.

### 0.22.2

- Added custom vehicle health communication via Overshield to the driver of a vehicle that has the custom health regeneration loop.

### 0.22.3

- Replaced custom vehicle health communication to be in the Prompt Widget; alternates to show vehicle health for 3 seconds and Points/Level for 1 second.

### 0.22.4

- Added on-level weapons and grenades to the mode prefab.
- Changed setWeaponTypes event to run from "roundInit" instead of "gameInit" as the weapon types need to be re-applied each round as some of them come from object variables whose objects are deleted each round.
- Removed "Set Objective Banner For Player" from resetVars_unit event as it's causing a thread freeze.
- Added "Set Object Spawn Order", -1 to resetVars_unit event.
- Removed custom vehicle health regeneration events.
- Added excess mode object deletion.

### 0.22.5

- Added new vehicles:
  - [25] ONI Wasp (Tier 7)
  - [26] Kig-Yar Warthog (Tier 3)
- Added new weapons:
  - [140] Rocket Hog Weapon + Pinpoint Needler (vehicle weapon)

- Added vehicleShotCadence variable to change the shot delay between custom vehicle weapon shots.

### 0.22.6

- Adjusted vehicles:
  - [23] Carrier Falcon
    - Health Adjustment: 100% → **60%**
  - [26] Kig-Yar Warthog
    - Shot Cadence: 0.0666 s → **0.00 s**

### 0.22.7

- Added a hook for the docked nav arker spacer feature from Warzone 0.11.0 in the docked powerup nav marker logic.
- Adjusted custom powerup docked nav marker Docking Order to start descending from 20 instead of 128 so they appear in the middle left of the screen with the new spacers feature.

### 0.22.8

- Adjusted weapons:
  - [1] Marksman Sidekick
    - Weapon Damage: 0.66 → **0.71**
  - [10] ONI Commando
    - Weapon Damage: 0.45 → **0.40**
  - [61] Arcane Sentinel Beam:
    - Ammo: 80+80 → **80+160**

### 0.22.9

- Adjusted weapons:
  - [13] Valkyrie
    - Ammo: 4+10 → **4+4**
  - [43] Banish Of Balaho
    - Ammo: 10+0 → **14+0**
  - [45] Kig-Yar Carbine
    - Weapon Damage: 1.00 → **2.80**
  - [47] Scorpion Tail
    - Ammo: 4% (6 shots) → **6% (9 shots)**

### 0.23.0

- Added new weapons:
  - [143] Kinetic Coil (Tier 1)
  - [144] Hardlight Coil (Tier 2)
  - [145] Plasma Coil (Tier 3)
  - [146] Shock Coil (Tier 4)

- Added forceful weapon switching if a vehicle enter attempt fails when purchasing a vehicle; holding turrets and Fusion Coils prevents entering a vehicle.
- Made vehicles and weapons be spawned from the mode instead of requiring on-level objects.

### 0.23.1

- Added new weapons:
  - [56] Poisoned Pulse Carbine (Tier 3)
  - [57] Assault Rifle Delta (Tier 3)
  - [58] ONI Battle Rifle (Tier 2)

- Adjusted weapons:
  - [6] ONI Battle Rifle
    - Name: ONI Battle Rifle → **The Ace**
    - Ammo: 14+70 → **14+84**
  - [29] ONI Turret
    - Weapon Type: M247 HMG + Striker Sidekick → **M247 HMG + Impact Commando**
    - Weapon Damage: 0.30 → **0.34**
  - [30] Doom Of Reach
    - Weapon Type: M247 HMG + MA40 Longshot → **M247 HMG + Striker Sidekick**
    - Weapon Damage: 1.20 → **0.40**
  - [43] Banish Of Balaho
    - Shot Velocity: 3000 → **2000**

### 0.23.2

- Added new vehicles:
  - [27] Husky (Tier 6)
  - [28] Cougar (Tier 2)
  - [29] Recon Falcon (Tier 4)

- Added new weapons:
  - [141] Sentinel Beam + Convergence Bulldog
    - Notes: Used for detecting vehicle honk, not intended for players.

- Adjusted weapons:
  - [136] Wasp Weapon + Pursuit Hydra
    - Weapon Type: Wasp Weapon + Pursuit Hydra → **Rockethog Weapon + MA40 Longshot**

### 0.24.0

- Added new vehicles:
  - [30] Breech-Load Razorback (Tier 4)
  - [31] Impulse Rockethog (Tier 8)
  - [32] Chopper (Tier 4)
  - [33] Hyperius Chopper (Tier 6)
  - [34] Chieftain Chopper (Tier 6)
  - [35] Escharum Chopper (Tier 8)
  - [36] Kig-Yar Ghost (Tier 5)
  - [37] Spec Ops Warthog (Tier 7)

- Adjusted vehicles:
  - [17] Moonlight Wasp
    - Weapon Damage: 2.00 → **1.00**
  - [19] Dragon
    - Shot Velocity: 200 → **300**

- Added new weapons:
  - [141] Rockethog Weapon + Riven Mangler (Vehicle weapon)
  - [142] Rockethog Weapon + Striker Sidekick (Vehicle weapon)

- Adjusted weapons:
  - [13] Valkyrie
    - Ammo: 4+4 → **4+6**
  - [36] Demon
    - Movement Speed: 1.00 → **1.20**
  - [37] Spike Of Thav 'Sebarim
    - Ammo: 10+10 → **10+30** (+50)
  - [41] A Go At
    - Rocket Jump velocity increase and scalar inversion fix
  - [141] Sentinel Beam + Convergence Bulldog
    - [141] → **[146]**
    - Weapon Type: Sentinel Beam + Convergence Bulldog → **Plasma Cannon (object)**
  - [143] Kinetic Coil
    - [143] → **[147]**
  - [144] Hardlight Coil
    - [144] → **[148]**
  - [145] Plasma Coil
    - [145] → **[149]**
  - [146] Shock Coil
    - [146] → **[150]**

- Increased projectile kill credit detection radius from 20 → **25** units.
- Overhauled the vehicle honk detection script to be more controlled.
  - Partially fixed [19] Dragon projectile kill credit not working due to 0.00 damage trait, but if the player gets instantly killed by the Shock Coil instead of the custom damage that comes afterwards, kill credit is still not awarded.
  - Fixed the [28] Cougar not being able to splatter anyone. Was caused by 0.00 damage trait.
- Fixed [28] Cougar speed boost on honk not working with multiple players.
- Reduced vehicle spawn queue delay from 3 → **2 s**.
- Fixed weaponGrantActive boolean being left TRUE when granting a Fusion Coil to a player.

### 0.25.0

- Adjusted vehicles:
  - [17] Moonlight Wasp
    - Weapon Damage: 1.00 → **0.80**
  - [19] Dragon (Paralyzing Falcon)
    - Shot Cadence: 2.00 → **3.50**
  - [23] Carrier Faclon (Dragon)
    - Brought back side turrets
    - Health Adjustment: 60% → **100%**
    - Weapon Type: None → **[141] Rockethog Weapon + Riven Mangler**
    - Shot Cadence: 1.00 → **0.03**
  - [29] Recon Falcon
    - Weapon Damage: 0.70 → **1.20**
    - Weapon Type: [136] Rockethog Weapon + MA40 Longhsot → **Rockethog Weapon + BR75 Breacher**
    - Health Adjustment: 100% → **60%**
  - [36] Kig-Yar Ghost (Famished Ghost) 
    - Weapon Type: [140] Rockethog Weapon + Pinpoint Needler → **[137] Rockethog Weapon + Scatterbound Heatwave**
    - Weapon Damage: 1.00 → **0.60**
    - Shot Cadence: 0.10 → **0.30**
  - [37] Spec Ops Warthog
    - Weapon Type: [142] Rockethog Weapon + Striker Sidekick → **[132] Rockethog Weapon + Rapidfire Pulse Carbine**
    - Shot Cadence: 0.05 → **0.30**
    - Weapon Damage: 0.50 → **3.00**

- Removed weapons:
  - [142] Rockethog Weapon + Striker Sidekick

- Added weapons:
  - [59] Burst-Fire Bandit (Tier 4)
  - [60] SPNKr x (Tier 8)

- Adjusted weapons:
  - [36] Demon (The Demon)
    - Movement Speed: 1.20 → **1.25**
  - [37] Spike of Thav 'Sebarim
    - Ammo: 10+30 → **10+20**
    - Shot Velocity: 400 → **300**
    - Added feature to track the shot projectile while zoomed.
  - [38] Hunters Right Hand
    - Weapon Type: Fuel Rod SPNKr + Striker Sidekick → **Fuel Rod SPNKr + Impact Commando**
  - [1] Marksman Sidekick
    - Weapon Type: Mk50 Sidekick + Impact Commando → **Mk50 Sidekick + MA40 Longshot**
    - Weapon Damage: 0.71 → **1.50**
    - Ammo: 40+60 → **25+75**
  - [136] Rockethog Weapon + MA40 Longshot → **Rockethog Weapon + BR75 Breacher**

- Added a hidden feature for the [3] Dexterity Ability Boost that increases the tracking scalar of the [37] Spike Of Thav 'Sebarim from 0.08 to 0.20, making the shots track more accurately.

### 0.25.1

Removed weapons:
- [57] Assault Rifle Delta (Tier 3)

Added weapons:
- [57] Bassus Artifact (Tier 8)

### 0.25.2

- Adjusted weapons:
  - [57] Bassus Artifact
    - VFX: Infected Alpha (15)
  - [60] SPNKr x
    - VFX: Infected Beta (28)

### 0.26.0

- Removed vehicles
  - [30] Breech-Load Razorback (Tier 3)

- Added new Vehicles:
  - [30] Scout Razorback (Tier 3)
  - [38] Grenade Launcher Mongoose (Tier 4)

- Adjusted Vehicles:
  - [16] Phantom Wasp
    - Vehicle Weapon Damage: 1.50 → **1.70**
  - [17] Moonlight Wasp
    - Vehicle Weapon Damage: 0.80 → **1.00**
  - [25] ONI Wasp
    - Vehicle Weapon Damage: 0.35 → **0.45**
  - [27] Cougar
    - Vehicle Weapon Damage: 1.50 → **2.00**
  - [37] Spec Ops Warthog
    - Vehicle Weapon Damage: 3.00 → **2.00**
    - Weapon Type: [132] Rockethog Weapon + Rapidfire Pulse Carbine → **Warthog Weapon**

- Removed Equipment
  - [12] Allied Monitor (Tier 2)

- Added new Equipment
  - [12] Strong Arm (Tier 2)

- Adjusted Equipment
  - [13] Speed Boost
    - Added faster reload trait
  - [14] Headshot Shielding
    - VFX: Infected Beta → **VIP**

### 0.26.1

Removed vehicles:
- [38] Grenade Launcher Mongoose (Tier 4)

Adjusted vehicles:
- [16] Phantom Wasp
  - Overhaul to shoot Banished Hunter shots
- [23] Dragon
  - Weapon Type: Rockethog Weapon + Riven Mangler → **Wasp Weapon + Ravager Rebound**
  - Weapon Damage: 0.80 → **0.01**
  - Shot Cadence: 0.03 → **None**
- [29] Recon Falcon
  - Weapon Type: Rockethog Weapon + BR75 Breacher → **Rockethog Weapon + Riven Mangler**
  - Weapon Damage: 1.20 → **0.20**
  - Shot Cadence: 0.02 → **0.03**

Adjusted weapons:
- [46] Light Of Doisac
  - Weapon Type: S7 Sniper Rifle + Riven Mangler → **S7 Sniper Rifle + Stalker Rifle Ultra**
  - Weapon Damage: 2.84 → **2.40**
  - Ammo: 4+8 → **4+16**
- [64] Calcine Disruptor
  - Ammo 7+14 → **7+25**
- [132] Rockethog Weapon + Rapidfire Pulse Carbine
  - Weapon Type: Rockethog Weapon + Rapidfire Pulse Carbine → **Rockethog Weapon + Stalker Rifle Ultra**
- [133] Rockethog Weapon + Ravager Rebound
  - Weapon Type: Rockethog Weapon + Ravager Rebound → **Rockethog Weapon + Riven Mangler**
- [136] Rockethog Weapon + BR75 Breacher
  - Weapon Type: Rockethog Weapon + BR75 Breacher → **Rockethog Weapon + Ravager Rebound**
- [141] Rockethog Weapon + Riven Mangler
  - Weapon Type: Rockethog Weapon + Riven Mangler → **Wasp Weapon + Ravager Rebound**

Adjusted equipment:
- [12] Strong Arm
  - Duration: 45 → **60 s**

### 0.26.2

Adjusted vehicles:
- [11] Mid Banshee (Alpha Banshee)
  - Weapon Damage: None → **2.30**
- [22] Incursion Banshee (Mid Banshee)
  - Weapon Type: Wasp Weapon + M41 Tracker → **Rockethog Weapon + Rapidfire Pulse Carbine**
  - Weapon Damage: 1.50 → **None**

Adjusted weapons:
- [138] Wasp Weapon + M41 Tracker
  - Weapon Type: Wasp Weapon + M41 Tracker → **Rockethog Weapon + Rapidfire Pulse Carbine**

### 0.26.3

[Adjusted vehicles](https://github.com/The-Scripters-Guild/Warzone/commit/2f9657db4badabba447483e57bdb87909c8c8b5d):
- [11] Alpha Banshee
  - Weapon Damage: 2.30 → **2.50**
- [16] Phantom Wasp
  - Shot Cadence: 0.30 → **0.45 s**
- [20] Undead Ghost
  - Weapon Damage: 0.95 → **None**
  - Shot Cadence: None → **0.50 s**
- [23] Dragon
  - Shot Cadence: None → **0.40 s**
- [36] Famished Ghost
  - Weapon Damage: 0.60 → **0.50**

[Adjusted weapons](https://github.com/The-Scripters-Guild/Warzone/commit/ceadba73c428ba8c1476626c1b5d62ffb76a111a):
- [37] Spike Of Thav 'Sebarim (Orb Launcher)
  - Projectile: Spike Grenade → **Banished Hunter Shot**
  - Ammo: 10+20 → **10+30**
- [46] Light Of Doisac
  - Ammo: 4+16 → **4+20**

- Adjusted weaponDespawnTime from 40 → **30 s**









## tsg warzone-radial module

Changelog for the tsg warzone-radial module used for the radial menu logic.

### 0.1.1

- Initial build.
- warzone-sandbox 0.18.1 compatible.
- Weapon, Equipment, Ability Boost & Vehicle names and points transferred from warzone-sandbox to warzone-radial.

### 0.1.2

- warzone-sandbox 0.18.2 compatible.
- Added Purchase Weapon: [52] Siege Bandit.

### 0.1.4

- warzone-sandbox 0.18.3 compatible.
- Added Purchase Weapon: [53] Cure Of The Haunted.
- Note: 0.1.3 is an illegal string in Halo Infinite.

### 0.1.5

- Added fix for not being able to open an enabled menu item if someone else had opened the same menu and had that item disabled on their menu.
- Added fallback menu trait removal by moving the aim vector.

### 0.2.0

- warzone-sandbox 0.19.1 compatible.
- Major optimization update for item variant menus to make them use the same menu.
- Added logic for vehicle spawn locations.
- Added logic for detemining when a REQ station can be accessed.

### 0.2.1

- Renamed reqStations variable to stations

### 0.2.2

- Fixed issues with automatic respawn not working when closing the Menu while dead.

### 0.2.3

- Added debug number display on the left at the end of a round that shows the amount per weapon bought per Game State.
- Reordered nodes in closeMenu event so "Show Menu To Player (false)" happens at the end. Maybe if the menu is invalid and it was at the front, it would freeze the thread and cause issues?

### 0.2.4

- Prevented Menu from being able to automatically show up after the game has ended right after a player had died.
- Added workaround for players being granted their current weapons again after making the first item purchase in a station, even if it was not a weapon.

### 0.3.0

- Made the spawning radial show up automatically for dead players who've made a purchase in the menu in order to streamline the process and not require players to re-open the menu for spawn selection.
- "Spawning Disabled while Alive" message replaced with "Choose Spawn" when accessing the spawning menu while alive.
- Adjusted aim movement threshold to forcefully exit a radial menu from 1.00 → 20.00, which should reduce instances of players accidentally exiting the Menu by moving their cursor while on a high latency.
- Added spawn selection persistence feature where selecting a spawn while dead once and then opening the menu again to make a purchase will retain the previously selected spawn location. Dying will reset the selection back to Home Base.
- Added spawn interruption feature that stops a player from spawning at a zone if an enemy captures that zone as the player is queued to spawn at it.
- Fixed and issue preventing the spawn selection menu from refereshing when a zone was captured.
- Added feature for bots to be randomly granted two weapons past Game State 1 that have been purchased by a player so bots would hold more unique weapons.
- Respawn Penalty set to 0 for players who swap team so scripted respawn time tracking matches the ability to instantly spawn.
- Adjusted point tiers of shock weapons:
  - [107] Plasma Pistol: 3 → 2
  - [95] Disruptor: 4 → 3
  - [21] Decaying Charge: 5 → 4
  - [112] Shock Rifle: 6 → 5
  - [73] Purging Shock Rifle: 7 → 5
  - [64] Calcine Disruptor: 7 → 6

### 0.3.1

- Fixed spawn radial refresh and spawn interruption logic.

### 0.3.2

- Added display of the player's points or level on the Main Radial item descriptions.
- Fixed a disconnected Object pin in the forceSpawnRadial event which may have led to multiple issues with the spawn interruption code not working.
- Decreased equipment costs:
  - [1] Drop Wall: 2 → 1
  - [5] Shroud Screen: 2 → 1
  - [6] Threat Sensor: 2 → 1
  - [7] Thruster: 2 → 1
  - [2] Grappleshot: 3 → 2
  - [4] Repulsor: 3 → 2
  - [16] Legendary Grappleshot: 4 → 3
  - [17] Legendary Threat Sensor: 4 → 3
  - [15] Legendary Drop Wall: 5 → 3
  - [10] Quantum Translocator: 4 → 3
  - [11] Health Steal: 6 → 5
- Decreased weapon costs:
  - [106] Needler: 2 → 1

### 0.4.0

- Changed the "Grenade Specialist" item icon in the Ability Boosts Radial to a Dynamo Grenade so players would want to select it more and realize it's a nested menu with four options.
- Changed "Loadouts" message in the Main Radial to "Loadout Weapons".
- Added a failsafe for the Spawn Radial where the menu items are only enabled if you are dead along with the other conditions.
- Updated "Grenade Operator" names to "Grenade Specialist".
- Updated "Heal Boost" to "Auto Medic".
- Neutralizing a zone will now disable all spawns inside the zone to prevent enemy players from spawning inside a zone while it's being captured. The spawns will be enabled again after a capture is completed.
- Made "Level x/y" show up in the description of a Radial Menu Item if that is the factor determining the menu item being disabled instead of not having enough points.
- Separated Points and Level display into separate Menu Items in the "Your Items" radial.
- Added "Next Radial" message to the description of the Numbered page menu items in the Weapon and Vehicle radials.
- Adjusted vehicle costs:
  - [3] Gungoose: 2 → 3
  - [8] Warthog: 4 → 3
  - [15] Plasma Warthog: 6 → 5
- Overhauled loadout weapon levels:
  - **Old**
  - 1: [101] MA40 Assault Rifle, [105] Mk50 Sidekick
  - 2: [1] Marksman Sidekick
  - 3: [3] Hardlight Assault Rifle, [92] Bandit Evo
  - 4: [102] MA5K Avenger, [99] M392 Bandit
  - 5: [115] VK78 Commando, [4] Hardlight Avenger
  - 6: [91] BR75, [9] Hardlight Commando
  - 7: [5] Hardlight Battle Rifle
  - **New**
  - 1: [101] MA40 Assault Rifle, [105] Mk50 Sidekick
  - 2: [1] Marksman Sidekick
  - 3: [3] Hardlight Assault Rifle, [115] VK78 Commando
  - 4: [9] Hardlight Commando
  - 5: [102] MA5K Avenger
  - 6: [4] Hardlight Avenger, [99] M392 Bandit
  - 7: [91] BR75
  - 8: [5] Hardlight Battle Rifle
  - 9: [92] Bandit Evo

### 0.4.1

- Decreased cost of items:
  - [10] Quantum Translocator from 3 → 2.
  - [29] ONI Turret from 5 → 4.
- Fixed [20] Rage Of Iratus name in script.
- Updated weapon menu item placements so they show up in the correct order.

### 0.4.2

- Decreased cost of weapons:
  - [51] Seeking Hydra: 3 → 2.
  - [103] MLRS-2 Hydra: 4 → 3.
- Changed delay for automatically spawning after closing the menu while dead from 3 → 2 seconds.
- Changed logWeaponValue event to async, and connected the Object pin. Before it was also logging bot weapon purchases due to no Object pin connected.

### 0.5.0

- Overhauled Weapons Radial ordering and page system. Now the first page has shortcuts to the next 4 pages. This makes navigating to each page take the same amount of selections.
- Made the player's screen go black for the short duration they are not in a vehicle right after spawning and having chosen to purchase a vehicle from the menu.

### 0.5.1

- Increased cost of weapons:
  - [65] Convergence Bulldog: 5 → 6.
  - [83] Unbound Plasma Pistol: 5 → 6.

### 0.5.2

- Fixed issue with custom black screen before being granted a vehicle that was causing it to not show up.
- Increased cost of weapons:
  - [96] Energy Sword: 3 → 4.
  - [35] Rogue Juggernaut: 4 → 5.
  - [68] Elite Bloodblade: 4 → 5.
  - [67] Duelist Energy Sword: 5 → 6.
  - [36] Demon: 6 → 7.
- Decreased cost of [74] Pursuit Hydra: 6 → 5.

### 0.5.3

- Increased cost of weapons:
  - [13] Valkyrie: 8 → 9.
  - [46] Light Of Doisac: 6 → 7.
- Decreased cost of items:
  - [6] Rockethog: 4 → 3.
  - [14] Fusion Rockethog: 7 → 5.
  - [50] Gamma Shot: 9 → 8
  - [68] Elite Bloodblade: 5 → 3.
- Moved [47] Scorpion Tail and [50] Gamma Shot to the Scrap Cannon category.
- Made the Weapon Radial unlock at start as the Needler can be purchased at tier 1.

### 0.5.4

- Decreased level of the [99] M392 Bandit: 6 → 5.
- Added decimal accuracy to the "Level" display in the "Your Items" radial, so players can get a more accurate idea on the level progression.
- Implemented a way to forcefully close a radial menu while alive by holding crouch while closing a menu or selecting a menu item in any radial.
- Changed the Equipment icon from Drop Wall → Grappleshot and the Power Equipment menu icon from Overshield → Active Camo in the Main Radial.
- Made player spawn location persist after death, and only resetting to home base if the zone is captured by an enemy.
- Added description to Spawn Radial menu items displaying how many teammates and enemies are inside a controlled zone.
- Adjusted feature for disabling spawns inside a zone to now happen always if players from the opposite team of a controlled zone are inside the zone.
- Made vehciles whose driver has the "Spy" Ability Boost equipped go partially invisible. Doesn't work for the Falcon for some reason.

### 0.5.5

- Removed vehicle invisibility effect of "Spy" Ability Boost from the Scorpion and Wraith.
- Increased tier of [75] Rapidfire Pulse Carbine: 3 → 4.

### 0.5.6

- Changed power equipment radial icon from Active Camo → Overshield.
- Added feature where bots will choose a random spawn location that a player on their team has chosen so the bots spawn in similar areas, and not just Home Base.
- Increased tier of [62] BR75 Breacher: 4 → 5.

### 0.6.0

- Major fix to a common menu closing issue by making all menus player-based following a new discovery.
- Added new weapon: [55] Brute Carbine (tier 2).
- Increased tier of [106] Needler: 1 → 2.

### 0.6.1

- Decreased tier of [69] Impact Commando: 6 → 5.
- Increased tier of [21] Decaying Charge: 4 → 5.
- Re-ordered Weapons Radial to reflect recent tier changes.
- Made the Weapons Radial unlock at level 2 as the lowest purchaseable weapon is now back to tier 2.
- Added Home Base Core health display in the Spawn Radial on the Home Base option so there is some useful information there instead of nothing.
- Disabled custom bot spawn at random zone as it was causing bots to not spawn.

### 0.6.2

- Added new vehicles:
  - [20] Undead Ghost (Tier 7)
  - [21] Divine Banshee (Tier 8)
  - [22] Incursion Banshee (Tier 9)
  - [23] Carrier Falcon (Tier 3)
  - [24] ONI Rockethog (Tier 6)
- Renamed [17] Banishing Wasp → Moonlight Wasp
- Fixed Core Health display in Spawn Selection radial to be more accurate.
- Made players automatically choose their Home Base spawn location On Gameplay Start.

### 0.6.3

- Removed redundant global variable set in the equipment variant radial logic.
- Removed menu re-enabling bug workaround as it's unnecessary with the object-scoped menus.

### 0.6.4

- Added new vehicles:
  - [25] ONI Wasp (Tier 7)
  - [26] Kig-Yar Warthog (Tier 3)

- Adjusted weapons:
  - [74] Pursuit Hydra
    - Tier 5 → **4**

### 0.6.5

- Fixed the player's loadout weapons not populating the primary weapon correctly in the radial menus if the previous primary had been dropped and a weapon had been bought in its place.
- Fixed the player's loadout weapons not populating correctly in the radial menus if the player switched team while alive.

### 0.6.6

- Adjusted weapons:
  - [10] ONI Commando
    - Tier: 3 → **2**
  - [118] Vestige Carbine
    - Tier: 4 → **3**

- Fixed issue in "Points" display in the "Your Items" radial where right before changing to the next whole number, the decimal would show "0.10", when the last value should be "0.9".
- Adjusted descriptions and titles of the "Points" and "Level" display items in the "Your Items" radial be more descriptive.
- Updated radialRefresh event to be more generalized.

### 0.6.7

- Fixed bots who join the game before Gameplay Start not being able to spawn.
- Added feature for bots to choose spawns that players on their team have selected so they appear to spawn around the map more naturally rather than only in the Home Base.

### 0.6.8

- Adjusted station activation event to gather the station's Spawn Order in a different way that works with new itemStation prefabs where the object Spawn Order is set via scripting and not via object property setting.

### 0.6.9

- Moved "hasOpenedRadial" boolean from the beginning of "radial1_main" event to the logMenu event so it's set to True when opening any radial and only after the "Show Menu To Player" node has fired before logMenu, so it should more accurately determine when a menu has been opened.
- Added loop to attempt opening the menu automatically 4 s after dead or join in progress as the one attempt to open it wasn't always working.
- Fixed replacing your secondary weapon with a turret dropping it on the ground while alive. Did not account for purchasing two weapons while dead and having the secondary weapon be a turret.
- Added informative docked Nav Marker to players 4 s after death messaging to use the Custom Input to open the menu as some people aren't noticing the Prompt Widget on the left.

### 0.7.0

- Added new weapons:
  - [143] Kinetic Coil (Tier 1)
  - [144] Hardlight Coil (Tier 2)
  - [145] Plasma Coil (Tier 3)
  - [146] Shock Coil (Tier 4)
  - Note: These are located in the Equipment menu, but still replace a weapon.

- Fixed falsely populated slots in weapon radial if a radial with more populated slots was opened previously.
- Made entire menu pages disabled if the player can't access any of the items within the menu yet.

### 0.7.1

- Added new weapons:
  - [56] Poisoned Pulse Carbine (Tier 3)
  - [57] Assault Rifle Delta (Tier 3)
  - [58] ONI Battle Rifle (Tier 2)

- Adjusted weapons:
  - [6] The Ace
    - Tier: 5 → **6**
  - [111] Sentinel Beam
    - Tier: 4 → **3**

- Excluded bots from purchasing the [13] Valkyrie as its abundance was causing issues in Warzone Ultra games.

### 0.7.2

- Added new vehicles:
  - [27] Husky (Tier 6)
  - [28] Cougar (Tier 2)
  - [29] Recon Falcon (Tier 4)

- Adjusted vehicles:
  - [19] Dragon
    - Weapon Type: [136] Wasp Weapon + Pursuit Hydra → **[141] Sentinel Beam + Convergence Bulldog**
    - Tier: 9 → **8**
    - Made the vehicle shoot Shock Coils.

### 0.7.3

- Added support for a debug mode that makes spawning and vehicle purchasing possible without a Warzone map setup. Use the boolean "debug" as TRUE to enable.

### 0.7.4

- Added new vehicles:
  - [30] Breech-Load Razorback (Tier 4)
  - [31] Impulse Rockethog (Tier 8)
  - [32] Chopper (Tier 4)
  - [33] Hyperius Chopper (Tier 6)
  - [34] Chieftain Chopper (Tier 6)
  - [35] Escharum Chopper (Tier 8)
  - [36] Kig-Yar Ghost (Tier 5)
  - [37] Spec Ops Warthog (Tier 7)

- Adjusted vehicles:
  - [27] Husky
    - Name: Husky → **Cougar**
  - [28] Cougar
    - Name: Cougar → **Scout Warthog**

- Added continuous menu closing after player has died to stop a menu from staying open if it was opened right as a player had died.
- Fixed players getting stuck dead in a "Respawning Next" message.
  - Happened if a bot left the match within one second after getting killed due to their spawn value not being set yet, and then the invalid value freezing the spawn queue. Bot spawn value is now instantly set after dying.
- Adjusted blindness and movement freeze effect length from 1 → **3 s** when attempting to spawn in a vehicle while dead to somewhat account for wait times in the vehicle spawn queue.
- Moved Gungoose variants to the Mongoose category in the vehicle radial.
- Moved [28] Scout Warthog to the Razorback category in the vehicle radial.

### 0.8.0

- Adjusted vehicles:
  - [1] Banshee
    - Point Cost: 7 → **6**
  - [9] Wasp
    - Point Cost: 7 → **6**
  - [11] Mid Banshee
    - Point Cost: 6 → **5**
  - [16] Phantom Wasp
    - Point Cost: 8 → **7**
  - [19] Dragon
    - Name: Dragon → **Paralyzing Falcon**
  - [23] Carrier Faclon
    - Name: Carrier Faclon → **Dragon**
    - Point Cost: 3 → **9**
  - [25] ONI Wasp
    - Point Cost: 7 → **6**
  - [30] Breech-Load Razorback
    - Point Cost: 4 → **3**
  - [36] Kig-Yar Ghost
    - Name: Kig-Yar Ghost → **Famished Ghost**

- Removed weapons:
  - [142] Rockethog Weapon + Striker Sidekick

- Added weapons:
  - [59] Burst-Fire Bandit (Tier 4)
  - [60] SPNKr x (Tier 8)

- Adjusted weapons:
  - [1] Marksman Sidekick
    - Level: 2 → **4**
  - [3] Hardlight Assault Rifle
    - Level: 3 → **2**
  - [24] Focus Beam
    - Point Cost: 5 → **4**
  - [64] Calcine Disruptor
    - Point Cost: 6 → **5**
  - [36] Demon
    - Name: Demon → The Demon
  - [92] Bandit Evo
    - Level: 9 → **8**
  - [112] Shock Rifle
    - Point Cost: 5 → **4**

### 0.8.1

- Removed weapons:
  - [57] Assault Rifle Delta (Tier 3)

- Added weapons:
  - [57] Bassus Artifact (Tier 8)

- Fixed players getting stuck dead in a "Respawning Next" message.
  - Happened if a bot left the match within 7 seconds of joining the match due to their spawn value not being set yet, and then the invalid value freezing the spawn queue. Joined bot is now checked for validity 7 seconds after joining before placing in spawn queue or not.

### 0.8.2

- Removed vehicles
  - [30] Breech-Load Razorback (Tier 3)

- Added new Vehicles:
  - [30] Scout Razorback (Tier 3)
  - [38] Grenade Launcher Mongoose (Tier 4)

- Adjusted Vehicles:
  - [1] Banshee
    - Tier: 6 → **7**
  - [10] Wraith
    - Tier: 8 → **7**
  - [11] Mid Banshee
    - Tier: 5 → **6**
  - [16] Phantom Wasp
    - Tier: 7 → **8**
  - [25] ONI Wasp
    - Tier: 6 → **7**

- Removed Equipment
  - [12] Allied Monitor (Tier 2)

- Added new Equipment
  - [12] Strong Arm (Tier 2)

- Made all Fusion Coils unlock at level 1

### 0.8.3

Removed vehicles:
- [38] Grenade Launcher Mongoose (Tier 4)

Adjusted weapons:
- [13] Valkyrie
  - Tier: 9 → **8**
- [79] S7 Flexfire Sniper
  - Tier: 6 → **5**
- [110] S7 Sniper Rifle
  - Tier: 6 → **5**

### 0.8.4

Adjusted vehicles:
- [11] Mid Banshee
  - Tier: 6 → **9**
  - Name: Mid Banshee → **Alpha Banshee**
- [22] Incursion Banshee
  - Tier: 9 → **6**
  - Name: Incursion Banshee → **Mid Banshee**

### 0.8.5
[Adjusted vehicles](https://github.com/The-Scripters-Guild/Warzone/commit/2f9657db4badabba447483e57bdb87909c8c8b5d):
- [36] Famished Ghost
  - Tier 5 → **6**

[Adjusted weapons](https://github.com/The-Scripters-Guild/Warzone/commit/ceadba73c428ba8c1476626c1b5d62ffb76a111a):
- [92] Bandit Evo
  - Level: 8 → **7**
- [37] Spike Of Thav 'Sebarim
  - Name: Spike Of Thav 'Sebarim → **Orb Launcher**

[Adjusted equipment](https://github.com/The-Scripters-Guild/Warzone/commit/9d8b56af338a992068c51069ce9c176a8f6a5b66):
- [4] Repulsor
  - Point Cost: 2 → **1**
- [11] Health Steal
  - Point Cost: 5 → **4**
- [15] Legendary Drop Wall
  - Point Cost: 3 → **2**
- [17] Legendary Threat Sensor
  - Point Cost: 3 → **2**
- [18] Legendary Thruster
  - Point Cost: 3 → **2**

- Made vehicle weapons be operable right after spawning in the vehicle from the death screen
