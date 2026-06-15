# grpc-transports.github.io

Sources for **grpc-transports.github.io** — the grpc-transports landing page.
Built by [Hugo](https://gohugo.io), with the same single inline-CSS template
shape as the sibling family pages (light/dark CSS vars, centered hero logo,
honest repository cards).

## Layout

```text
.
├── hugo.toml                       Site config + repo card params
├── content/
│   └── _index.md                   Homepage marker (empty)
├── layouts/
│   └── index.html                  Homepage body (grpc-transports specific)
├── static/
│   ├── favicon.svg                 Brand mark (favicon)
│   └── img/logo.svg                Brand mark (88px hero logo)
└── public/                         Hugo build output (gitignored — built by CI)
```

## Build locally

```sh
hugo server -D                            # live reload at http://localhost:1313/
GOWORK=off hugo --minify                  # production build → ./public/
```

## Deploy

`.github/workflows/hugo.yml` builds + deploys on every push to `main`.
Configure GitHub Pages on the repo with **Source = "GitHub Actions"**
(not "Deploy from a branch").

## Repositories

- [wireguard](https://github.com/grpc-transports/wireguard) — gRPC over a WireGuard overlay.
- [ssh](https://github.com/grpc-transports/ssh) — gRPC over an SSH tunnel.
