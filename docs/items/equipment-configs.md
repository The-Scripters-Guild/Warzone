# Equipment Configurations

The configurations that make up each of the equipment, including custom powerups.

<!--
## [#] Equipment Name
- Equipment Type: Custom Equipment #
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
    - Extended Ranger Scalar: #.##
    - Vehicle Range Scalar: #.##
- Charge Count: #
- Duration: ## s
- VFX: Infected Alpha, Infected Beta, VIP, None
- REQ Tier: #
- Game State: #
- Notes: -
-->

## [1] Drop Wall
- Equipment Type: Drop Wall
- Charge Count: 3
- REQ Tier: 2
- Game State: 1
- Notes: -

## [2] Grappleshot
- Equipment Type: Grappleshot
- Charge Count: 4
- REQ Tier: 3
- Game State: 1
- Notes: -

## [3] Repair Field
- Equipment Type: Repair Field
- Charge Count: 1
- REQ Tier: 3
- Game State: 1
- Notes: -

## [4] Repulsor
- Equipment Type: Repulsor
- Charge Count: 4
- REQ Tier: 3
- Game State: 1
- Notes: -

## [5] Shroud Screen
- Equipment Type: Shroud Screen
- Charge Count: 2
- REQ Tier: 2
- Game State: 1
- Notes: -

## [6] Threat Sensor
- Equipment Type: Threat Sensor
- Charge Count: 3
- REQ Tier: 2
- Game State: 1
- Notes: -

## [7] Thruster
- Equipment Type: Thruster
- Charge Count: 3
- REQ Tier: 2
- Game State: 1
- Notes: -

## [8] Active Camouflage
- Equipment Type: Active Camouflage
- Charge Count: 1
- Duration: 30 s
- REQ Tier: 4
- Game State: 3
- Notes: -

## [9] Overshield
- Equipment Type: Overshield
- Charge Count: 1
- Duration: 50 s
- REQ Tier: 3
- Game State: 2
- Notes: -

## [10] Quantum Translocator
- Equipment Type: Quantum Translocator
- Charge Count: 1
- Duration: 30 s
- REQ Tier: 4
- Game State: 3
- Notes: -

## [11] Health Steal
- Equipment Type: Custom Equipment A
- Trait Set: healthSteal
  - Vampirism
    - Shield Scalar: 0.00
    - Health Scalar: 0.40
- Charge Count: 1
- Duration: 60 s
- VFX: Infected Alpha
- REQ Tier: 6
- Game State: 5
- Notes: Vampirism only comes from dealing damage to enemy health, not shield.

## [12] Allied Monitor
- Equipment Type: Custom Equipment B
- Trait Set: alliedMonitor
  - Third Person Gameplay: TRUE
- Charge Count: 1
- Duration: 45 s
- VFX: VIP
- REQ Tier: 2
- Game State: 1
- Notes: Puts the player's view in third person, allowing for a wider angle of the battlefield.

## [13] Speed Boost
- Equipment Type: Custom Equipment C
- Trait Sets: speedboost1 & speedboost2 & speedboost3 & speedboost4
  - Movement Speed: 1.16
  - Sprint Speed
    - Top Speed Scalar: 1.13
    - Time To Top Speed Scalar: 1.00
  - Slide Speed
    - Slide Speed Scalar: 0.93
    - Slide Duration Scalar: 1.00
- Charge Count: 1
- Duration: 45 s
- VFX: None
- REQ Tier: 2
- Game State: 1
- Notes: Has four identical traits that can be stacked for a total of four Speed Boosts. Stacking multiple traits multiplies their scalars.

## [14] Headhunter Guard
- Equipment Type: Custom Equipment D
- Trait Set: headhunterGuard
  - Headshot Protection: TRUE
- Charge Count: 1
- Duration: 60 s
- VFX: Infected Beta
- REQ Tier: 3
- Game State: 2
- Notes: Makes headshots to unshielded players act like bodyshots. Weapons that can kill an unshielded player in one hit to the head will now require more shots to the head to kill.

## [15] Legendary Drop Wall
- Equipment Type: 
- Charge Count: 1
- REQ Tier: 5
- Game State: 1
- Notes: Granted via object reference; has invalid Equipment Type that doesn't work in script. Object reference must be gathered initially via player mark. Equipment spawner object be index 1 with label "Dodgeball Overtime Zone".

## [16] Legendary Grappleshot
- Equipment Type: 
- Charge Count: 4
- REQ Tier: 4
- Game State: 1
- Notes: Granted via object reference; has invalid Equipment Type that doesn't work in script. Object reference must be gathered initially via player mark. Equipment spawner object be index 2 with label "Dodgeball Overtime Zone".

## [17] Legendary Threat Sensor
- Equipment Type: 
- Charge Count: 2
- REQ Tier: 4
- Game State: 1
- Notes: Granted via object reference; has invalid Equipment Type that doesn't work in script. Object reference must be gathered initially via player mark. Equipment spawner object be index 3 with label "Dodgeball Overtime Zone".

## [18] Legendary Thruster
- Equipment Type: 
- Charge Count: 3
- REQ Tier: 3
- Game State: 1
- Notes: Granted via object reference; has invalid Equipment Type that doesn't work in script. Object reference must be gathered initially via player mark. Equipment spawner object be index 4 with label "Dodgeball Overtime Zone".
