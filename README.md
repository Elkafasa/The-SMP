The SMP – SERVER INFO

Minecraft Version: 1.21.11
Backups: Weekly
Server Launch Date: Feb 5, 2026
End Portals Unlock: Feb 19, 2026
Ender Dragon Fight: Begins immediately after End portals unlock

World & Border

Starting Border: 10,000 × 10,000 blocks

Border Expansion: Increases with certain achievements, including the Ender Dragon’s death

Future Achievements: More may be added to influence border size

Reset Mechanics:

Season resets can happen but are not guaranteed at a fixed date.

Resets occur if server activity is too low or if the majority of the server votes for a reset.

End Dimension & Dragon Fight

End dimension is locked until UnlockDate (Feb 19, 2026, 15:30 server time)

Bossbar "pre_teleport" shows countdown to unlock

Right-clicking End portal frames or entering the End before unlock is cancelled with a message

When unlock occurs:

Broadcast announces the End opening

A 5 minute timer begins before the dragon fight starts the end is still locked/protected by the ender dragon at this time

After that players are teleported to the stronghold (pvp is turned off)

The border surrounds the stronghold and a 10 minute timer is shown, a message reveals that the ender dragon is still protecting people from entering the end

After The 10 minute timer everyone is surrounded by the border and is forced into the end portal

Players are teleported to the End

The end fight begins yet pvp is still disabled by some sort of glitch caused by the border fighting the ender dragon's lock on the borders

Glitch event activates, adding visual effects to the scoreboard and TAB

Once the ender dragon is defeated the glitch is gone the end portals are unlocked but pvp is still disable for 15 minutes

Combat System

Tracks PvP combat with dynamic variable {-combat::%player%}

Bossbar appears for both attacker and victim showing countdown in seconds

Every 1 second, bossbar updates progress; removed after 15 seconds

Logging out during combat kills the player and broadcasts a message

Bossbar IDs: combat_%uuid%

Fully integrated with TAB scoreboard placeholders

TAB Plugin Configurations

Animations (animations.yml):

glitch_vibrant & glitch_line: flashy “glitchy” effects

ram_bar: memory usage (%progressbar_percentage_memory-used%)

ip_glow: server IP highlight

health_safe, health_warning, health_danger: color-coded health display

day_colors / night_colors: dynamic color changes based on in-game time

Note: animations depend on Skript placeholders being loaded

Config (config.yml):

Sets tablist header/footer, scoreboards, and bossbar defaults

glitch-sb scoreboard displays only when {event.glitch.active} is true

Anti-override prevents other plugins from overwriting custom scoreboard values

Bossbar colors can use animation:bar_colors placeholders

Rules & Gameplay Mechanics

Ender Chests & Shulker Boxes: Uncraftable/obtainable before Ender Dragon fight

Maces & Netherite Spears: Uncraftable/unobtainable before Ender Dragon fight

Other items: No bans or restrictions

Voice Chat: Required; works with Simple Voice Chat

Commands

/tpa – Request teleport to another player

/home & /sethome – Teleport to saved locations

/resetallprogression – Admin command to reset all event variables and borders to default

/testglitch – Toggle glitch mode for testing

Combat Logging

Hitting or being hit by another player starts 15-second PvP timer

Bossbar shows countdown during combat

Leaving the server during combat kills the player

Non-player damage (e.g., mobs, fall damage) does not trigger combat timer
