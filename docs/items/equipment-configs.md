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
- VFX: Infected Alpha, Infected Alpha - Screen, Infected Beta, Infected Beta - Screen, VIP, None
- REQ Tier: #
- Game State: #
- Notes: -
-->

## [E1] Drop Wall
- Equipment Type: Drop Wall
- Charge Count: 3
- REQ Tier: 2
- Game State: 1
- Notes: -

## [E2] Grappleshot
- Equipment Type: Grappleshot
- Charge Count: 4
- REQ Tier: 4
- Game State: 1
- Notes: -

## [E3] Repair Field
- Equipment Type: Repair Field
- Charge Count: 1
- REQ Tier: 3
- Game State: 1
- Notes: -

## [E4] Repulsor
- Equipment Type: Repulsor
- Charge Count: 4
- REQ Tier: 3
- Game State: 1
- Notes: -

## [E5] Shroud Screen
- Equipment Type: Shroud Screen
- Charge Count: 2
- REQ Tier: 2
- Game State: 1
- Notes: -

## [E6] Threat Sensor
- Equipment Type: Threat Sensor
- Charge Count: 3
- REQ Tier: 2
- Game State: 1
- Notes: -

## [E7] Thruster
- Equipment Type: Thruster
- Charge Count: 3
- REQ Tier: 2
- Game State: 1
- Notes: -

## [E8] Active Camouflage
- Equipment Type: Active Camouflage
- Charge Count: 1
- Duration: 30 s
- REQ Tier: 4
- Game State: 3
- Notes: -

## [E9] Overshield
- Equipment Type: Overshield
- Charge Count: 1
- Duration: 50 s
- REQ Tier: 3
- Game State: 2
- Notes: -

## [E10] Quantum Translocator
- Equipment Type: Quantum Translocator
- Charge Count: 1
- Duration: 30 s
- REQ Tier: 4
- Game State: 3
- Notes: -

## [E11] Health Steal
- Equipment Type: Custom Equipment A
- Trait Set: healthSteal
  - Vampirism
    - Shield Scalar: 0.00
    - Health Scalar: 0.40
- Charge Count: 1
- Duration: 60 s
- VFX: Infected Alpha, Infected Alpha - Screen
- REQ Tier: 6
- Game State: 5
- Notes: Vampirism only comes from dealing damage to enemy health, not shield.

## [E12] Power Arm
- Equipment Type: Custom Equipment B
- Trait Set: powerArm
  - Melee Impulse: 2.00
  - Melee Recovery Speed: 1.80
- Charge Count: 1
- Duration: 45 s
- VFX: Infected Beta, Infected Beta - Screen
- REQ Tier: 2
- Game State: 1
- Notes: Can melee faster with any weapon and can melee inert objects further upon impact.

## [E13] Speed Boost
- Equipment Type: Custom Equipment C
- Trait Set 1: upgradedWalkingPU
  - Movement Speed: 1.10
  - Jump Height: 1.10
  - Sprint Speed
    - Top Speed Scalar: 0.95
    - Time To Top Speed Scalar: 1.00
  - Slide Speed
    - Slide Speed Scalar: 0.93
    - Slide Duration Scalar: 1.00
  - Slide Speed
    - Slide Speed Scalar: 0.99
    - Slide Duration Scalar: 1.00
- Trait Set 2: upgradedSprintingPU
  - Sprint Speed
    - Top Speed Scalar: 1.13
    - Time To Top Speed Scalar: 0.90
  - Slide Speed
    - Slide Speed Scalar: 1.10
    - Slide Duration Scalar: 1.00
- Charge Count: 1
- Duration: 45 s
- VFX: None
- REQ Tier: 2
- Game State: 1
- Notes: Combines the upgradedWalking and upgradedSprinting ability boosts for the best of both. Trait sets are identical, but separate declarations so they can be individually turned on and off without intereference.

## [E14] Headhunter Guard
- Equipment Type: Custom Equipment D
- Trait Set: headhunterGuard
  - Headshot Protection: TRUE
- Charge Count: 1
- Duration: 60 s
- VFX: VIP
- REQ Tier: 3
- Game State: 2
- Notes: Makes headshots to unshielded players act like bodyshots. Weapons that can kill an unshielded player in one hit to the head will now require more shots to the head to kill.

## [E99] Legendary Drop Wall
- Equipment Type: 
- Charge Count: 1
- REQ Tier: 5
- Game State: 1
- Notes: Granted via object reference; has invalid Equipment Type that doesn't work in script. Object reference must be gathered initially via player mark. Equipment spawner object be index 1 with label "Dodgeball Overtime Zone".

## [E99] Legendary Grappleshot
- Equipment Type: 
- Charge Count: 4
- REQ Tier: 5
- Game State: 1
- Notes: Granted via object reference; has invalid Equipment Type that doesn't work in script. Object reference must be gathered initially via player mark. Equipment spawner object be index 2 with label "Dodgeball Overtime Zone".

## [E99] Legendary Threat Sensor
- Equipment Type: 
- Charge Count: 2
- REQ Tier: 4
- Game State: 1
- Notes: Granted via object reference; has invalid Equipment Type that doesn't work in script. Object reference must be gathered initially via player mark. Equipment spawner object be index 3 with label "Dodgeball Overtime Zone".

## [E99] Legendary Thruster
- Equipment Type: 
- Charge Count: 3
- REQ Tier: 3
- Game State: 1
- Notes: Granted via object reference; has invalid Equipment Type that doesn't work in script. Object reference must be gathered initially via player mark. Equipment spawner object be index 4 with label "Dodgeball Overtime Zone".
