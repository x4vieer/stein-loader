# Stein Loader

**Minecraft 1.8.9 on Java 25 and LWJGL 3.** The game keeps its 1.8.9 rules and its look; what changed underneath
is the engine it runs on. Nothing from Mojang is redistributed here: the installer patches the `1.8.9.jar` that is
already on your machine, on your machine.

## Download

**[Stein Loader — latest installer](https://github.com/x4vieer/stein-loader/releases/latest)** — one file that
carries its own Java 25, the engine and the loader. It is a `.jar`: double-click it (or `java -jar
SteinLoader-Installer.jar`) with Java 17 or newer. No Java at all? Take `SteinLoader-Installer-windows.zip` from
the same release, unzip it and run the `.exe` inside.

Play Minecraft 1.8.9 once in the launcher first, run the installer, then pick the profile **Stein Loader 1.8.9**.
Already installed? The button says Update and keeps your earlier choices.

## Mods

Each mod has its own repository and its own releases, so a download link always points at that mod's latest
version. They are installed by hand: drop the `.steinmod` into the `mods` folder of your `.minecraft` — the
installer never adds or removes mods. They are turned on and off in the Stein Loader menu and set up in the Panel
(Insert).

| mod | what it does | download |
| --- | --- | --- |
| [HUD](https://github.com/x4vieer/stein-hud) | customizable HUD, minimap and the Tab list | [HUD.steinmod](https://github.com/x4vieer/stein-hud/releases/latest/download/HUD.steinmod) |
| [Connect](https://github.com/x4vieer/stein-connect) | accounts, reconnect and SOCKS5 proxy | [Connect.steinmod](https://github.com/x4vieer/stein-connect/releases/latest/download/Connect.steinmod) |
| [Combat](https://github.com/x4vieer/stein-combat) | clans, allies, nearest enemy, hide allies | [Combat.steinmod](https://github.com/x4vieer/stein-combat/releases/latest/download/Combat.steinmod) |
| [Mouse](https://github.com/x4vieer/stein-mouse) | inventory gestures: shift-drag and scroll | [Mouse.steinmod](https://github.com/x4vieer/stein-mouse/releases/latest/download/Mouse.steinmod) |

## stein.json

Public data that the **Stein Loader** reads on startup, in `stein.json`. Editing it here applies to everyone the
next time they start the game — no new Loader release and no new installer.

- **`discord`** — the invite to the Stein Labs Discord. It is what the button on the main menu and the one on the
  About tab of the Stein Loader menu open. Only `https://discord.gg/...` or `https://discord.com/invite/...` is
  accepted: the Loader refuses any other address.
- **`servers`** — servers added to the multiplayer list of everyone running the Loader, under a "Recommended
  servers" divider. **Nothing is ever deleted**: servers the player already had stay where they are, and one that
  is already in the list (same address) is only moved to the top and renamed to the name given here.
- **`latest`** — the installer version that is published and where to get it. The game compares it with the
  version installed on that machine and, when this one is newer, shows a balloon on the main menu.
- **`news`** — a small balloon on the main menu: `id` (shown once per id), `title` and `text` (one string, or one
  entry per game language, with `en_US` as the fallback) and an optional `url`.

Releases here are published by CI, and `latest` and `news` are written by it. The mods live in their own
repositories, listed above; this one carries the installer and `stein.json`.
