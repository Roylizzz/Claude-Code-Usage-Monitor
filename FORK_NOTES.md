# Roylizzz fork changes

This fork keeps the upstream MIT attribution and focuses on a compact, local-first
Windows taskbar monitor.

## Privacy and quota guarantees

- Claude usage is read only from the OAuth usage endpoint.
- The Claude poller does **not** call the Messages API and does not send a prompt
  merely to obtain rate-limit headers.
- If the read-only usage endpoint is unavailable, the poll fails and the app keeps
  its normal stale/last-good behavior instead of spending model quota.
- No new telemetry or backend service is introduced by this fork.
- Provider credentials remain used only for the provider usage/account requests
  already required by the monitor.

## Taskbar design

The default theme is **Roy Compact Cards**.

Each enabled provider occupies one 148 px card. Disabled providers take no space.
For Claude and Codex, a card shows the short and long usage windows as two compact
continuous bars with percentages. Providers can be enabled together, so Claude +
Codex uses about 302 px including the gap.

The original built-in themes remain available from Theme Studio.
