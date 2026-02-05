# Repository Analysis Notes

## What this repository appears to be
- This is a **live Paper Minecraft server directory** (not a source-only plugin repo): it contains active world data (`world`, `world_nether`, `world_the_end`), server runtime logs, plugin jars/configs, and downloaded Java libraries.
- The root `README.md` documents Season 1 gameplay policies and custom event flows.

## Core server stack
- Minecraft/Paper target version appears to be **1.21.11**.
- Bedrock bridging is enabled via **Geyser + Floodgate**.
- Extensive plugin ecosystem is present (`Skript`, `TAB`, `LuckPerms`, `GrimAC`, `Essentials`, `PlaceholderAPI`, voice chat, etc.).

## Custom gameplay logic (Skript-driven)
The most custom behavior is implemented in Skript files under `plugins/Skript/scripts/`:

1. **End unlock + teleport sequence** (`endlockdown.sk`)
   - Locks End access until a fixed date.
   - Shows pre-unlock countdown bossbar.
   - Broadcasts unlock and force-teleports players to the End once the trigger time is reached.

2. **Dragon fight controller** (`ENDFIGHTEVENT.sk`)
   - Tracks active dragon fight state.
   - Blocks PvP while dragon is alive.
   - Clears glitch/event state after dragon death.

3. **Combat logging system** (`combatlog.sk`)
   - Starts a 15-second combat timer when players attack each other.
   - Shows per-player combat bossbars.
   - Kills and broadcasts if a player logs out mid-combat.

4. **Border progression logic** (`borderchecker.sk`)
   - Expands world border to 25,000 after dragon death.
   - Keeps/reset border at 10,000 before progression.

5. **TAB placeholders bridge** (`TAB_placeholders.sk`)
   - Exposes Skript variables (glitch state, combat state, time) to TAB scoreboards.

## Configuration observations
- `server.properties` is set to `online-mode=false`, with RCON enabled.
- `server.properties` also has `enforce-whitelist=true`, but `white-list=false` appears contradictory and worth validating in runtime behavior.
- TAB config contains a conditional “glitch” scoreboard tied to Skript placeholder `%skript_tab_glitch_active%`.
- Paper world/global configs are mostly default-style with selective toggles.

## Security/ops notes
- Sensitive credentials are stored directly in plain text in repo-tracked files (`server.properties`, `rcon-cli.yaml`, `rcon-cli.env`).
- Because this is effectively a production-like runtime directory with logs/world/player files, a `.gitignore` strategy and secrets segregation would materially reduce accidental exposure.
