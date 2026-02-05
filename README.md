The SMP — Server Information
General Info

Minecraft Version: 1.21.11

Backups: Weekly

Server Launch Date: February 5, 2026

End Portals Unlock: February 19, 2026

Ender Dragon Fight: Begins after the End portals unlock sequence completes

World & Border

Starting World Border: 10,000 × 10,000 blocks

Border Expansion:

Expands through specific achievements, including the Ender Dragon’s death

More achievements may be added later to influence border size

Season Resets

Season resets can happen, but are not guaranteed at a specific date

A reset may occur if:

Server activity drops too low

A majority of the server agrees via a vote that a reset is necessary

End Dimension & Dragon Event Flow

The End is heavily scripted and event-driven.

Before Unlock

The End dimension is locked until Feb 19, 2026 at 15:30 (server time)

Bossbar pre_teleport displays a live countdown

Right-clicking End portal frames or attempting to enter the End is blocked with a message

Unlock Sequence

When the unlock time is reached:

Announcement Broadcast

The End opening is announced server-wide

5-Minute Pre-Fight Lock

The End remains locked and protected

The Ender Dragon is still preventing access

Stronghold Phase

Players are teleported to the stronghold

PvP is disabled

A border surrounds the stronghold

A 10-minute timer appears

Messages explain that the dragon is still protecting the End

Forced Entry

After the 10-minute timer:

Players are surrounded by the border

Everyone is forced into the End portal

Dragon Fight Begins

Players are teleported to the End

PvP remains disabled due to a lore-based “glitch” caused by:

The world border

The dragon’s control over the End

Glitch event activates, affecting TAB and scoreboard visuals

Post-Dragon

Once the Ender Dragon is defeated:

Glitch effects are removed

End portals unlock fully

PvP remains disabled for 15 additional minutes

Combat System (Anti-Combat Log)

PvP combat is tracked using:
{-combat::%player%}

When players fight:

A bossbar appears showing a countdown in seconds

Both attacker and victim receive a bossbar

Bossbars update every second and disappear after 15 seconds

Bossbar IDs use dynamic UUIDs:
combat_%uuid%

Logging out during combat:

Instantly kills the player

Broadcasts a combat-log message to the server

Integrated with TAB scoreboards and placeholders

Non-player damage (mobs, fall damage, etc.) does not trigger combat

TAB Plugin Configuration
Animations (animations.yml)

Custom animated elements used across TAB, scoreboards, and bossbars:

glitch_vibrant / glitch_line – Glitch-style visual effects

ram_bar – Memory usage display

ip_glow – Animated server IP

health_safe / warning / danger – Color-based health display

day_colors / night_colors – Time-based color cycling

⚠️ These animations depend on Skript placeholders being loaded correctly.

TAB Config (config.yml)

Custom tablist headers and footers

Multiple scoreboards with conditions

glitch-sb scoreboard displays only when {event.glitch.active} is true

Anti-override enabled to prevent other plugins from replacing values

Bossbars can use animated colors via animation:bar_colors

Gameplay Rules & Restrictions

Ender Chests & Shulker Boxes

Uncraftable / unobtainable before the Ender Dragon fight

Maces & Netherite Spears

Uncraftable / unobtainable before the Ender Dragon fight

Other spear types are allowed

Other Items

No global item bans

Voice Chat

Required to join

Uses Simple Voice Chat

Install here:
https://modrinth.com/plugin/simple-voice-chat

Commands

/tpa – Request teleport to another player

/home / /sethome – Teleport to saved locations

/resetallprogression – Admin command to reset all event variables and borders

/testglitch – Toggle glitch mode (testing only)

Combat Logging Summary

PvP starts a 15-second combat timer

Timer is displayed via a bossbar

Logging out during combat results in death

Only player-caused damage triggers the system
