# HP Scan to Paperless – Home Assistant add-on

Scan on an HP All-in-One printer (**Scan → Computer → Paperless**) and the document lands in
[Paperless-ngx](https://docs.paperless-ngx.com/). Runs as a Home Assistant add-on, e.g. on the
Raspberry Pi that is always on anyway. Built on
[node-hp-scan-to](https://github.com/manuc66/node-hp-scan-to).

Useful for older HP printers whose cloud services (HP ePrint / Web Services) were shut down and
which only support the outdated SMB1 for *Scan to Network Folder*. Tested target: HP OfficeJet
Pro 7730.

## Install

1. Home Assistant → **Settings → Add-ons → Add-on Store** → ⋮ (top right) → **Repositories**.
2. Add `https://github.com/dosje/hp-scan-paperless` → **Add** → close.
3. Reload the page; under **HP Scan to Paperless** open the add-on → **Install**
   (Home Assistant builds it on your device, a few minutes on a Raspberry Pi).
4. Tab **Configuration**: printer IP, Paperless address, API token → **Save** → **Start**.

Requires Home Assistant OS or Supervised (the menu *Settings → Add-ons*). Details, options and
troubleshooting: [hp-scan-paperless/DOCS.md](hp-scan-paperless/DOCS.md) (also shown in Home
Assistant under the add-on's *Documentation* tab).

## Updates

A new version here (version number in `hp-scan-paperless/config.yaml`) shows up in Home
Assistant as **Update** on the add-on.

## Structure

| Path | Purpose |
|---|---|
| `repository.yaml` | marks this as a Home Assistant add-on repository |
| `hp-scan-paperless/config.yaml` | add-on definition and options |
| `hp-scan-paperless/Dockerfile` | `manuc66/node-hp-scan-to` image plus the start script |
| `hp-scan-paperless/run.sh` | turns the add-on options into the tool's settings |
| `hp-scan-paperless/DOCS.md`, `translations/` | documentation and option texts in Home Assistant |

## License

[MIT](LICENSE) for this add-on (configuration and start script). The add-on builds on the
[node-hp-scan-to](https://github.com/manuc66/node-hp-scan-to) Docker image by Emmanuel Counasse,
which is also MIT-licensed. HP and OfficeJet are trademarks of HP Inc.; this project is not
affiliated with HP.
