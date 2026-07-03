# platysonique-killswitch

**Public** revocation list for Platysonique desktop apps (`pbmsweet`, `bbc`).

> **This repo must stay public.** Apps fetch `killswitch.json` over HTTPS without authentication. If you make this repo private, remote revoke stops working (apps fail open when offline).

Full operator guide: [pombomb-obs `security/README.md`](https://github.com/platysonique/pombomb-obs/blob/main/security/README.md) (private repo — clone locally).

## Quick: revoke one machine

```bash
python3 /usr/share/platysonique/killswitch.py --show-id
```

Add the hash to `revokedMachineIds` in `killswitch.json`, commit, push.

## Quick: revoke all machines

Set `"globalRevoke": true` in `killswitch.json` and push.

## Live URL

`https://raw.githubusercontent.com/platysonique/platysonique-killswitch/main/killswitch.json`

## On revoke

Apps wipe local credentials (OBS WebSocket, BabbleCast, browser saved passwords, sudo keyring, `gh`) then exit.

Manual wipe: `platysonique-killswitch-wipe`

## Private device labels (optional)

See **platysonique-device-registry** on GitHub — your notebook of hash → machine name. Apps never read it.
