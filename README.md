# Starling Desktop

Native desktop client for **[Starling](https://forgejo.hearthhome.lol/Saltfault/Starling)** — a federated, peer-to-peer communications platform with no company in the middle.

> **Status: 📋 Planned — not yet started.**
> The terminal client, **[Starling-TUI](https://forgejo.hearthhome.lol/Saltfault/Starling-TUI)**, is the working client today. This repo is a placeholder for the eventual windowed app.
> It's a graphical app — when ready, you'll download and install it normally. There's no `starling install` command for it.

---

## What this will be

A proper native application — not a browser tab wearing a costume — that gives you Starling's text, voice, and video with a mouse-and-window UI. The goal is to stay lean: use noticeably less memory and CPU than the mainstream chat apps it replaces.

It will speak the exact same murmuration as every other client. A flock you join from Desktop is the same flock your friend is in from the TUI.

## How it's built (planned)

Starling Desktop is a **thin UI over a shared core**. The frontend is **SolidJS**, wrapped in a **Tauri** shell whose Rust backend is the [`starling-server`](https://forgejo.hearthhome.lol/Saltfault/Starling-Server) library — so all the hard parts (the iroh endpoint, gossip, encryption, and the voice/video pipelines) are shared with every other client. This repo contains the SolidJS UI and the Tauri glue that pumps `Command`/`AppEvent` messages between the UI and that core.

| Piece | Stack |
|-------|-------|
| Frontend | SolidJS |
| App shell | Tauri |
| Protocol / networking | [`starling-server`](https://forgejo.hearthhome.lol/Saltfault/Starling-Server) library (Tauri's Rust backend) |
| Target platforms | Windows, macOS, Linux |

## Following along

- Design and roadmap live in the main **[Starling](https://forgejo.hearthhome.lol/Saltfault/Starling)** repo.
- The protocol this will implement is documented in **[Starling-Server](https://forgejo.hearthhome.lol/Saltfault/Starling-Server)**.
- Want it sooner? The most useful help right now is exercising the protocol through the TUI and filing what breaks.

## License

Apache 2.0
