The SMP — Server Information
General Info

Minecraft Version: 1.21.11

Backups: Weekly

Server Launch Date: February 5, 2026

End Portals Unlock: February 19, 2026

Ender Dragon Fight: Begins after the End unlock sequence completes

World & Border
Starting World Border

10,000 × 10,000 blocks

Border Expansion

The world border expands through specific progression achievements

Ender Dragon death is a major expansion trigger

Additional achievements may be added in the future to further affect border size

Season Resets

Season resets can occur, but are not guaranteed at a fixed date.

A reset may happen if:

Server activity drops too low

A majority of active players vote that a reset is necessary

Resets are player-driven or activity-driven, not automatic.

End Dimension & Dragon Event Flow

The End is fully scripted and operates as a server-wide event.

Before Unlock

The End dimension is locked until Feb 19, 2026 at 15:30 (server time)

Bossbar pre_teleport displays a live countdown

Attempting to:

Right-click End portal frames

Enter the End
is blocked with a message

Unlock Sequence
Announcement

A server-wide broadcast announces the End opening

5-Minute Pre-Fight Lock

The End remains locked and protected

The Ender Dragon is still preventing entry

Stronghold Phase

Players are teleported to the stronghold

PvP is disabled

A world border surrounds the stronghold

A 10-minute timer is displayed

Messages explain that the dragon is still protecting the End

Forced Entry

After the 10-minute timer:

Players are surrounded by the border

Everyone is forced into the End portal

Dragon Fight Begins

Players are teleported to the End

PvP remains disabled

A lore-based “glitch event” activates due to:

The world border

The dragon’s control over the End

Glitch effects appear in:

TAB

Scoreboards

Bossbars

Post-Dragon

Once the Ender Dragon is defeated:

Glitch effects are removed

End portals unlock fully

PvP remains disabled for an additional 15 minutes

The world border expands as part of progression

Combat System (Anti-Combat Log)

PvP combat is tracked using:

{-combat::%player%}

Combat Behavior

When players fight:

A bossbar appears showing a 15-second countdown

Both attacker and victim receive a bossbar

Bossbars:

Update every second

Disappear after 15 seconds

Bossbar IDs use dynamic UUIDs:

combat_%uuid%

Combat Logging

Logging out during combat:

Instantly kills the player

Broadcasts a combat-log message to the server

Integration

Fully integrated with TAB scoreboards and placeholders

Only player-caused damage triggers combat
(mobs, fall damage, etc. do not)

TAB Plugin Configuration
Animations (animations.yml)

Custom animated elements used across TAB, scoreboards, and bossbars:

glitch_vibrant / glitch_line – Glitch-style visual effects

ram_bar – Memory usage display

ip_glow – Animated server IP

health_safe / health_warning / health_danger – Color-based health display

day_colors / night_colors – Time-based color cycling

⚠️ These animations depend on Skript placeholders being loaded correctly.

TAB Config (config.yml)

Custom tablist headers and footers

Multiple conditional scoreboards

glitch-sb scoreboard only displays when:

{event.glitch.active} = true


Anti-override enabled to prevent other plugins from replacing values

Bossbars can use animated colors via:

animation:bar_colors

Gameplay Rules & Restrictions
Ender Chests & Shulker Boxes

Uncraftable / unobtainable before the Ender Dragon fight

Maces & Netherite Spears

Uncraftable / unobtainable before the Ender Dragon fight

Other spear types are allowed

Other Items

No global item bans

Voice Chat

Required to play

Uses Simple Voice Chat

Install:

https://modrinth.com/plugin/simple-voice-chat

Commands

/tpa – Request teleport to another player

/home / /sethome – Teleport to saved locations

/resetallprogression – Admin command to reset:

Event variables

Bossbars

World border

/testglitch – Toggle glitch mode (testing only)

Combat Logging Summary

PvP starts a 15-second combat timer

Timer is shown via a bossbar

Logging out during combat results in death

Only player-caused damage triggers the system
