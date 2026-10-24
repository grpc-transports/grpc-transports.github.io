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
- [vsock](https://github.com/grpc-transports/vsock) — gRPC over a host/guest vsock.
- [websocket](https://github.com/grpc-transports/websocket) — gRPC over a WebSocket.
- [webrtc](https://github.com/grpc-transports/webrtc) — gRPC over a WebRTC data channel.
- [control](https://github.com/grpc-transports/control) — the admin plane: a 0600 unix socket, or TCP with mandatory mTLS.

## The design is not here

It comes from the shared Hugo module
[`go-fleettools/landingkit`](https://github.com/go-fleettools/landingkit),
pinned in `go.mod` (Renovate bumps it); `kit.go` keeps `go mod tidy` from
deleting that requirement. `[params.brand]` in `hugo.toml` is read from the logo by
`landingkit brand`. A file under `layouts/partials/` with the name of one of the
kit's would silently override it.
