# Ability Boost Configurations

The configurations that make up each of the ability boosts.

<!--
## [#] Armor Mod Name
- Trait Set: #
  - Weapon Damage: #.##
  - Reload Speed
    - Empty Reload Scalar: #.##
    - Tactical Reload Scalar: #.##
  - Weapon Switch Speed: #.##
  - Movement Speed: #.##
  - Movement Speed With Turret: #.##
  - Jump Height: #.##
  - Clamber Speed: #.##
  - Sprint Speed
    - Top Speed Scalar: #.##
    - Time To Top Speed Scalar: #.##
  - Slide Speed
    - Slide Speed Scalar: #.##
    - Slide Duration Scalar: #.##
  - Melee Damage: #.##
  - Melee Impulse: #.##
  - Melee Recovery Speed: #.##
  - Bonus Health: #.##
  - Bonus Shield: #.##
  - Health Recharge
    - Recharge Delay Scalar: #.##
    - Recharge Rate Scalar: #.##
  - Shield Recharge
    - Recharge Delay Scalar: #.##
    - Recharge Rate Scalar: #.##
  - Vampirism
    - Shield Scalar: #.##
    - Health Scalar: #.##
  - Damage Resistance
    - Direct Damage Scalar: #.##
    - Grenade Damage Scalar: #.##
    - Explosive Damage Scalar: #.##
  - Headshot Protection: TRUE/FALSE
  - Grenade Damage: #.##
  - Grenade Detonation Radius: #.##
  - Grenade Impulse: #.##
  - VFX - Active Camouflage
    - Intensity Scalar: #.##
    - Interpolation Scalar: #.##
  - VFX - Overshield: TRUE/FALSE
  - Motion Tracker Visible
    - Motion Tracker Enabled: TRUE/FALSE
    - Enabled While Zooming: TRUE/FALSE
  - Motion Tracker Range
    - Inner Ring Scalar: #.##
    - Extended Range Scalar: #.##
    - Vehicle Range Scalar: #.##
- Level: #
- Notes: -
-->

## [1] Auto Medic
- Trait Set: autoMedic
  - Health Recharge
    - Recharge Delay Scalar: -0.30 (5.0 s -> 3.5 s to begin recharging = 30.0% faster)
    - Recharge Rate Scalar: 0.42 (1.1333 s -> 0.798098591549 s to charge fully = 29.5% faster)
  - Shield Recharge
    - Recharge Delay Scalar: -0.30 (5.0 s -> 3.5 s to begin recharging = 30.0% faster)
    - Recharge Rate Scalar: 0.42 (2.0 s -> 1.40845070423 s to charge fully = 29.5% faster)
- Level: 4
- Notes: Explanation on how to adjust the scalars: https://discord.com/channels/220766496635224065/1275401201973854238/1275437779370639420

## [2] Upgraded Sensor
- Trait Set: upgradedSensor
  - Motion Tracker Visible
    - Motion Tracker Enabled: TRUE
    - Enabled While Zooming: TRUE
  - Motion Tracker Range
    - Inner Ring Scalar: 1.666
    - Extended Range Scalar: 1.10
    - Vehicle Range Scalar: 1.00
- Level: 5
- Notes: Inner Ring is a general extension of the range and Extended Range is how far enemies will be shown on the outside ring of the radar when they're not within the range of the Inner Ring.

## [3] Dexterity
- Trait Set: expertMarksman
  - Reload Speed
    - Empty Reload Scalar: 1.17
    - Tactical Reload Scalar: 1.17
  - Weapon Switch Speed: 1.17
  - Clamber Speed: 1.17
  - Melee Recovery Speed: 1.40
- Level: 4
- Notes: Changes the projectile tracking scalar of the [37] Spike Of Thav 'Sebarim from 0.08 to 0.20, making the shots track more accurately.

## [4] Grenadier
- Trait Set: grenadier
  - Damage Resistance
    - Direct Damage Scalar: 1.00
    - Grenade Damage Scalar: 0.91
    - Explosive Damage Scalar: 1.00
  - Grenade Damage: 1.10
  - Grenade Detonation Radius: 1.52
- Level: 3
- Notes: -

## [5] Upgraded Walking
- Trait Set: upgradedWalking
  - Movement Speed: 1.10
  - Jump Height: 1.15
  - Slide Speed
    - Slide Speed Scalar: 0.85
    - Slide Duration Scalar: 1.00
- Level: 4
- Notes: -

## [6] Upgraded Sprinting
- Trait Set: upgradedSprinting
  - Sprint Speed
    - Top Speed Scalar: 1.15
    - Time To Top Speed Scalar: 0.90
  - Slide Speed
    - Slide Speed Scalar: 1.10
    - Slide Duration Scalar: 1.00
- Level: 4
- Notes: -

## [7] Spy
- Trait: VFX - Active Camouflage
  - Intensity Scalar: 0.50
  - Interpolation Scalar: 1.00
- Level: 5
- Notes: Removes outline and name from player; 50% passive camo that takes a second to reactivate if the player starts running or fires their weapon. Driving a vehicle with the Ability Boost active causes the vehicle to go invisible; excluded vehicles: Falcon, Wraith, Scorpion.

## [8] Frag Grenade Specialist
- Level: 5
- Notes: Sets the player's Frag Grenade count to 4 and removes all other Grenades.

## [9] Spike Grenade Specialist
- Level: 3
- Notes: Sets the player's Frag Grenade count to 2, Spike Grenade count to 3 and removes all other Grenades.

## [10] Plasma Grenade Specialist
- Level: 4
- Notes: Sets the player's Frag Grenade count to 2, Plasma Grenade count to 2 and removes all other Grenades.

## [11] Dynamo Grenade Specialist
- Level: 6
- Notes: Sets the player's Frag Grenade count to 2, Dynamo Grenade count to 2 and removes all other Grenades.
