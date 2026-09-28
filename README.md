<div align="center">

# PackSync

**Keep your Minecraft modpacks healthy, automatically.**

PackSync finds the modpacks you've installed with CurseForge, checks every file, repairs anything that's
missing or broken, and tells you when a new version is out, all in a couple of clicks.

[**Download for Windows**](https://github.com/DevEhChad/PackSync-Releases/releases/latest) ·
[What's new](CHANGELOG.md)

</div>

---

## Features

- **Your CurseForge modpacks, automatically.** Everything installed in the CurseForge app shows up in PackSync's sidebar with its artwork, version and status. The list updates live while CurseForge installs, updates or removes packs.
- **Checked against CurseForge's own records.** A quick check runs by itself; **Check all files** verifies every mod, resource pack and shader pack by checksum.
- **One-click repair.** Missing or damaged files are downloaded again and verified. Mods you added yourself are never touched, and mods whose authors don't allow other apps are fetched through your browser instead.
- **Knows when there's an update.** When a newer pack version is out, PackSync tells you and opens CurseForge to install it.
- **Linked packs.** Got a modpack from a friend or a server as a Dropbox, Google Drive or `.zip` link? Add it, pick a folder, and press **Sync now** to keep it up to date.
- **Safe by default.** PackSync backs up your `mods` folder before changing anything, waits if Minecraft is running, checks files aren't in use, and never touches your worlds.
- **Updates itself.** New versions of PackSync install in the background.

> **Coming soon:** a **Play** button that launches your modpack straight from PackSync. It's built and waiting for
> Microsoft's approval for Minecraft sign-in.

## Getting started

1. Download **`PackSync-win-Setup.exe`** from the [latest release](https://github.com/DevEhChad/PackSync-Releases/releases/latest) and run it.
2. PackSync opens with your CurseForge modpacks already listed on the left. Pick one to see its status.
3. If something needs fixing, press **Repair**. To play, press **Open CurseForge** and start the pack there.

> Windows may show a SmartScreen warning because the installer isn't code-signed yet. Choose
> **More info → Run anyway**.

### Requirements

- Windows 10 or 11 (64-bit)
- The [CurseForge app](https://www.curseforge.com/download/app) for CurseForge modpacks (linked packs work without it)

## FAQ

**Does PackSync change my CurseForge packs?**
Only when you press **Repair**, and then only to put back exactly the files CurseForge installed. New pack versions are always installed by CurseForge itself, so its records stay correct.

**Where are my settings?**
In `%LOCALAPPDATA%\PackSync`. Uninstalling PackSync removes them; your Minecraft instances are never touched.

**My modpacks folder isn't in the usual place.**
Open **Settings → CurseForge → Instances folder** and pick it. PackSync remembers it.

## Building from source

Requires the [.NET 10 SDK](https://dotnet.microsoft.com/download).

```bash
dotnet restore
dotnet build -c Release
dotnet test
dotnet run --project src/PackSync.Desktop
```

| Document | What it covers |
| --- | --- |
| [docs/GITHUB_SETUP.md](docs/GITHUB_SETUP.md) | Step by step: private source repo, public releases repo, first release, seeing updates |
| [docs/RELEASING.md](docs/RELEASING.md) | Building and publishing releases (GitHub Actions → public releases repo) |
| [release-repo/README.md](release-repo/README.md) | Front page of the public releases repo (copied there with `CHANGELOG.md` on each release) |
| [website/README.md](website/README.md) | The download site at packsync.ecsgameservers.com |
| [docs/MICROSOFT_SIGNIN.md](docs/MICROSOFT_SIGNIN.md) | Enabling the Play button (Azure app ID + Minecraft approval) |
| [CHANGELOG.md](CHANGELOG.md) | Release history |

Built with .NET 10 and [Avalonia](https://avaloniaui.net/); self-updates with [Velopack](https://velopack.io/).
Local configuration goes in a git-ignored `appsettings.json` next to the executable (see
`src/PackSync.Desktop/appsettings.example.json`). No API keys or tokens are ever stored in the app.

---

<sub>PackSync is not affiliated with Mojang, Microsoft or CurseForge. Minecraft is a trademark of Mojang Synergies AB.</sub>
