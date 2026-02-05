# Startup Validation Report (current run)

## Command used

```bash
(sleep 120; echo stop) | java -jar server.jar nogui
```

## Result: target files are still broken

The fresh `logs/latest.log` from this run shows the same targeted Skript parsing failures.

### Broken Skript files

- `plugins/Skript/scripts/ENDFIGHTEVENT.sk`
  - `Can't understand this structure: on dragon spawn`
  - `Can't understand this structure: after 10 seconds`
- `plugins/Skript/scripts/TAB_placeholders.sk`
  - `Can't understand this structure: on skript placeholder request "player_health"`
- `plugins/Skript/scripts/endlockdown.sk`
  - structure/flow errors and unsupported `bossbar ... exists` checks
- `plugins/Skript/scripts/borderchecker.sk`
  - world border syntax lines still error in this runtime
- `plugins/Skript/scripts/combatlog.sk`
  - unsupported bossbar create/set/remove syntax and time-difference expression errors

## TAB status

- The prior dynamic runtime warnings about `%skript_tab_time%` and bossbar color `AQUA` were **not present** in this fresh run.
- TAB still reports config-schema warnings (missing/default sections, unknown key warnings), but these are separate from the old `%skript_tab_time%` / `AQUA` issues.

## Bottom line

- **Yes, files are still broken** for the Skript set above.
- The server reaches `Done (...)`, but those scripts fail to load correctly, so their gameplay logic is not active.
