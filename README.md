<div align="center">

# PackSync

**A Minecraft launcher that keeps your modpacks healthy.**

Create your own packs, add mods, resource packs, shaders and datapacks from Modrinth and CurseForge, and play.
PackSync also finds the packs you've installed with CurseForge, checks every file and repairs anything broken.

[**Download for Windows**](https://github.com/DevEhChad/PackSync-Releases/releases/latest) ·
[Website](https://packsync.ecsgameservers.com) ·
[What's new](CHANGELOG.md)

</div>

---

This repository holds the **downloads and update files** for PackSync. Installed copies of the app check its
[Releases](https://github.com/DevEhChad/PackSync-Releases/releases) for new versions and update themselves.

## Features

- **Your own packs.** Create a pack for any Minecraft version, vanilla or with Fabric, Quilt, Forge or NeoForge, or import one from a `.zip` or link with a CurseForge manifest. Each pack has **Mods, Resource packs, Shaders and Datapacks** tabs: see what's installed, turn things on or off, update them, or press **Add** to search Modrinth and CurseForge. Only versions that fit the pack are offered, and required dependencies come along automatically.
- **Press Play.** Sign in with your Microsoft account (or look around as a guest first) and start any pack straight from PackSync. It checks the pack first and repairs it if needed. Fabric, Quilt, Forge and NeoForge packs all work; PackSync installs the loader the first time if CurseForge hasn't yet.
- **Your CurseForge modpacks, automatically.** Everything installed in the CurseForge app shows up in PackSync's sidebar with its artwork, version and status. The list updates live while CurseForge installs, updates or removes packs.
- **Checked against CurseForge's own records.** A quick check runs by itself; **Check all files** verifies every mod, resource pack and shader pack by checksum.
- **One-click repair.** Missing or damaged files are downloaded again and verified. Mods you added yourself are never touched, and mods whose authors only allow downloads on CurseForge take one click in a CurseForge window inside PackSync (or your browser).
- **Knows when there's an update.** When a newer pack version is out, PackSync tells you and opens CurseForge to install it.
- **Update from a link.** Got a modified version of a pack from a friend or a server, as a Dropbox, Google Drive or `.zip` link (for example one exported from CurseForge)? Paste it on the pack's page or add it as a linked pack. PackSync shows exactly what will change (mods to add or update, configs and scripts) with checkboxes, then installs what you picked. Mods already on your PC are copied over; mods that can only be downloaded on CurseForge take one click each. Your own settings (options, keybinds, server list) are never overwritten.
- **Safe by default.** Changed your mind? **Undo changes** puts a pack back exactly as it was before PackSync touched it. PackSync also backs up your `mods` folder before changing anything, waits if Minecraft is running, checks files aren't in use, and never touches your worlds.
- **Updates itself.** New versions of PackSync install in the background.

## Install

1. Download **`PackSync-win-Setup.exe`** from the [latest release](https://github.com/DevEhChad/PackSync-Releases/releases/latest) and run it.
   Prefer no installer? Download **`PackSync-win-Portable.zip`**, extract it anywhere and run `PackSync.exe`.
2. Sign in with the Microsoft account you play Minecraft with, or continue as a guest (you can sign in later from the account button at the top right).
3. Your CurseForge modpacks are already listed on the left. To make your own, press **+** next to **My packs**.
4. Pick a pack and press **Play**. If something needs fixing, PackSync repairs it before the game starts.

> Windows may show a SmartScreen warning because the installer isn't code-signed yet. Choose
> **More info → Run anyway**.

The other files in each release (`.nupkg`, `releases.win.json`, `RELEASES`) are used by the app to update itself;
you don't need to download them.

### Requirements

- Windows 10 or 11 (64-bit)
- A Minecraft: Java Edition account to play
- Optional: the [CurseForge app](https://www.curseforge.com/download/app), if you want your CurseForge modpacks listed too

## FAQ

**Does PackSync change my CurseForge packs?**
Only when you ask it to: **Repair** puts back exactly the files CurseForge installed, and adding, removing or updating content or updating from a link changes just what you picked (and can be undone). The CurseForge app won't list content added by PackSync. New official pack versions are always installed by CurseForge itself, so its records stay correct. To experiment freely, use **Copy to My packs** first.

**Where are my settings?**
In `%LOCALAPPDATA%\PackSync`, together with the shared game files. Uninstalling PackSync removes them; your packs and Minecraft instances are never touched.

**Where are my own packs?**
In `Documents\PackSync\Instances`, one folder per pack. Change it in **Settings → My packs**.

**My modpacks folder isn't in the usual place.**
Open **Settings → CurseForge → Instances folder** and pick it. PackSync remembers it.

---

<sub>This README and [CHANGELOG.md](CHANGELOG.md) are updated automatically with each release.
PackSync is not affiliated with Mojang, Microsoft or CurseForge. Minecraft is a trademark of Mojang Synergies AB.</sub>
