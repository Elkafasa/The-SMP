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

Players are teleported to the End

Dragon fight begins

Glitch event activates, adding visual/server-lore effects to indicate the fight has started

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

Ender Chests & Shulker Boxes: Uncraftable/obtainable only after Ender Dragon fight

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
