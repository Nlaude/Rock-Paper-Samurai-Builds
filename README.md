# Rock Paper Samurai — Builds

Windows builds of Rock Paper Samurai, and the launcher that keeps them up to date.

## Play

1. Download [RockPaperSamuraiLauncher.exe](https://github.com/Nlaude/Rock-Paper-Samurai-Builds/raw/main/RockPaperSamuraiLauncher.exe).
2. Put it in a folder of its own, for example `Documents\Rock Paper Samurai`. It installs the game into a `Game` folder beside itself.
3. Run it. It downloads the game (about 100 MB the first time), then shows a **Play** button.

Always start the game through the launcher. Each time it starts it checks for a new build and downloads only the files that changed, so you and your opponent stay on the same version (online play only pairs identical builds).

Windows may show a "Windows protected your PC" warning because the launcher is unsigned; choose **More info > Run anyway**. Windows 10 or 11, 64-bit.

## How to play

Two samurai, one choice each round. Both lock in a move in secret, then both strike at once.

| Move | Beats | Loses to |
|---|---|---|
| Iron Stance (Rock) | Blade Rush | Shadow Step |
| Shadow Step (Paper) | Iron Stance | Blade Rush |
| Blade Rush (Scissors) | Shadow Step | Iron Stance |

A draw replays the round. Pick Best of 1, 3, 5 or 7 on the title screen.

| | Iron Stance | Shadow Step | Blade Rush |
|---|---|---|---|
| Player 1 | Q | W | E |
| Player 2 | U | I | O |
| Gamepad (pad 1 = P1, pad 2 = P2) | X | Y | B |

You can also click the move buttons on screen.

## Playing online

One player picks **Online Duel > Host a duel**. The other enters the host's IP address and clicks **Join**.

- The game uses **UDP port 7777**. The host should allow it through Windows Firewall when asked.
- Players on the same network, or on the same Tailscale network, can join straight away.
- Over the internet without Tailscale, the host forwards UDP 7777 on their router and shares their public IP address.
- After a duel, both players press **Play Again** for a rematch.

Steam matchmaking and invites are planned; until then it's direct IP.

## What is in this repo

| Item | Purpose |
|---|---|
| `RockPaperSamuraiLauncher.exe` | The launcher |
| `Game/` | The current build |
| `manifest.json` | Version, plus a SHA-256 checksum and size for every file; the launcher compares against it |

Builds are published from the game's source repository with `Tools/publish-build.ps1`.
