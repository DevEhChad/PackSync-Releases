<div align="center">

# PackSync

**Keep your Minecraft modpacks healthy, automatically.**

PackSync finds the modpacks you've installed with CurseForge, checks every file, repairs anything that's
missing or broken, and tells you when a new version is out, all in a couple of clicks.

[**Download for Windows**](https://github.com/DevEhChad/PackSync-Releases/releases/latest) ·
[Website](https://packsync.ecsgameservers.com) ·
[What's new](CHANGELOG.md)

</div>

---

This repository holds the **downloads and update files** for PackSync. Installed copies of the app check its
[Releases](https://github.com/DevEhChad/PackSync-Releases/releases) for new versions and update themselves.

## Features

- **Your CurseForge modpacks, automatically.** Everything installed in the CurseForge app shows up in PackSync's sidebar with its artwork, version and status. The list updates live while CurseForge installs, updates or removes packs.
- **Checked against CurseForge's own records.** A quick check runs by itself; **Check all files** verifies every mod, resource pack and shader pack by checksum.
- **One-click repair.** Missing or damaged files are downloaded again and verified. Mods you added yourself are never touched, and mods whose authors don't allow other apps are fetched through your browser instead.
- **Knows when there's an update.** When a newer pack version is out, PackSync tells you and opens CurseForge to install it.
- **Linked packs.** Got a modpack from a friend or a server as a Dropbox, Google Drive or `.zip` link? Add it, pick a folder, and press **Sync now** to keep it up to date.
- **Safe by default.** PackSync backs up your `mods` folder before changing anything, waits if Minecraft is running, checks files aren't in use, and never touches your worlds.
- **Updates itself.** New versions of PackSync install in the background.

> **Coming soon:** a **Play** button that launches your modpack straight from PackSync.

## Install

1. Download **`PackSync-win-Setup.exe`** from the [latest release](https://github.com/DevEhChad/PackSync-Releases/releases/latest) and run it.
   Prefer no installer? Download **`PackSync-win-Portable.zip`**, extract it anywhere and run `PackSync.exe`.
2. PackSync opens with your CurseForge modpacks already listed on the left. Pick one to see its status.
3. If something needs fixing, press **Repair**. To play, press **Open CurseForge** and start the pack there.

> Windows may show a SmartScreen warning because the installer isn't code-signed yet. Choose
> **More info → Run anyway**.

The other files in each release (`.nupkg`, `releases.win.json`, `RELEASES`) are used by the app to update itself;
you don't need to download them.

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

---

<sub>This README and [CHANGELOG.md](CHANGELOG.md) are updated automatically with each release.
PackSync is not affiliated with Mojang, Microsoft or CurseForge. Minecraft is a trademark of Mojang Synergies AB.</sub>
