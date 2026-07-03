# platysonique-killswitch

Public revocation list for Platysonique desktop apps (`pbmsweet`, `bbc`).

## Revoke one machine

```bash
python3 /usr/share/platysonique/killswitch.py --show-id
```

Add the printed SHA-256 hash to `revokedMachineIds` in `killswitch.json`, commit, and push.

## Revoke all machines

Set `"globalRevoke": true` in `killswitch.json` and push.

Apps fetch:

`https://raw.githubusercontent.com/platysonique/platysonique-killswitch/main/killswitch.json`

When revoked, apps wipe local credentials (OBS WebSocket password, BabbleCast passwords, browser storage, sudo keyring entry, etc.) before exiting.

Optional private device labels: `platysonique-device-registry` (GitHub private).
