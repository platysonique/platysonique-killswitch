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
