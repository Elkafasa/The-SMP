# Latest Startup Log Diagnosis (logs/latest.log)

## Primary breakages

1. **EssentialsDiscord fails to authenticate and disables itself**
   - Log shows: `The provided token is invalid!`
   - This prevents EssentialsDiscord from staying online.

2. **EssentialsDiscordLink crashes with NullPointerException**
   - It tries to call Discord API while EssentialsDiscord is already disabled.
   - Root cause is cascading from the invalid Discord token above.

3. **Skript scripts are not compiling (multiple syntax errors)**
   - Several scripts fail to parse (`ENDFIGHTEVENT.sk`, `endlockdown.sk`, `combatlog.sk`, `TAB_placeholders.sk`, `borderchecker.sk`).
   - Because these scripts fail at load time, event systems described in README are likely not active.

4. **TAB placeholder warnings indicate unresolved placeholders**
   - `%skript_tab_time%` is returned as literal text instead of a number.
   - `%animation:bar_colors%` returns `AQUA`, but TAB bossbar color enum only allows `[PINK, BLUE, RED, GREEN, YELLOW, PURPLE, WHITE]`.

5. **MCXboxBroadcast session creation fails (TLS trust/cert chain issue)**
   - Error includes `SSLHandshakeException` and `PKIX path building failed`.
   - Indicates Java truststore / certificate chain issue when connecting to remote endpoint.

6. **MCOptimizer throws NPE on shutdown task**
   - `this.webServer is null` in `LagPredictionManager` task.
   - This is likely plugin bug or race condition during plugin disable.

## Important warnings (non-fatal but significant)

- Server running in offline mode (`online-mode=false`) and warns it is insecure.
- Simple Voice Chat warns encryption is not secure in offline mode.
- ProtocolLib says Minecraft 1.21.11 is not officially tested.
- Essentials reports unsupported server version.

## README cross-check

README states:
- End event flow is fully scripted.
- Combat system is bossbar-driven and tracked in Skript variables.
- TAB animations and placeholders depend on Skript placeholders.

Current logs show those systems are partially broken because related Skript files fail to parse.

## Recommended fix order

1. Fix Discord token in EssentialsDiscord config, then restart.
2. Temporarily disable EssentialsDiscordLink until EssentialsDiscord is healthy.
3. Resolve Skript syntax compatibility for installed Skript/addon versions:
   - `on dragon spawn`, `after 10 seconds`, bossbar syntaxes, placeholder request syntax, world border syntaxes.
4. Fix TAB bossbar color animation by removing unsupported values (e.g., replace `AQUA`).
5. Define/load missing `%skript_tab_time%` placeholder (or remove numeric condition depending on it).
6. For MCXboxBroadcast PKIX errors, update Java CA trust bundle / system certs and verify outbound TLS chain.
7. Update/replace MCOptimizer if NPE persists after clean restart.
