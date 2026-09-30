# Changelog

## [1.1.0] - 2026-09-30

### Added
- **Friends.** Sign in with Microsoft and open **Friends** in the sidebar. Add friends by their Xbox gamertag, accept or decline requests, and see live who's online, idle, busy or playing, and which pack. The sidebar shows unread messages and new requests. Signing in connects you to PackSync's online service with your gamertag and picture; if it can't be reached, signing in and playing work as before.
- **Chat window with tabs.** Chats open in their own window, one tab per friend, like a browser. Double-click a friend or press **Message**; close tabs with ✕, middle-click or Ctrl+W; switch with Ctrl+Tab. A dot marks tabs with new messages, and a message from a friend whose chat isn't on screen pops up at the bottom right with **Open chat**.
- **Your status.** Pick **Online**, **Idle**, **Busy** or **Invisible** on the Friends page. Online turns Idle by itself after 15 minutes away from PackSync, but never while you're playing: friends then see "Playing {pack}". Busy hides message pop-ups. Invisible looks offline to friends, and you still get their messages.
- **Send to friend…** drops a pack into a friend's chat as a card with an **Install** button: one click creates the pack on their PC and installs everything. The card works for 2 hours.
- **Share pack…** makes a link anyone can import a pack from for the next 2 hours (for example `https://packsync.ecsgameservers.com/p/Ab3xY9kQ2m`), with a one-click **Copy link**. Packs up to 50 MB fit in a link. Opened in a browser, a link shows the pack and how to import it; an expired link says so.
- **Export modpack…** saves a pack as a `.packsync` file others can import. Mods, resource packs and shaders are listed as downloads from Modrinth or CurseForge (each with its SHA-1, and marked client-only, server-only or both). Files that aren't downloadable anywhere can be put in the file itself, and the summary tells you which. Format: [docs/PACKSYNC_FORMAT.md](docs/PACKSYNC_FORMAT.md).
- **Share, export or send any pack:** your own, CurseForge packs and linked packs, from each pack's page or by right-clicking it in the sidebar. For a linked folder whose Minecraft version can't be read, the form asks for it.
- **Choose what goes in.** The export form lists every file and folder of the pack with tick boxes, like CurseForge's and Modrinth's exporters. Mods, resource packs, shaders, configs and scripts are ticked; worlds, options, the server list and other folders are yours to add. Logs, passwords and caches are never included. Your choices are remembered per pack, and the summary shows how much actually goes in the file or link.
- **Import `.packsync` files and share links:** **+ → Import a modpack** (and **Update from a link**) take `.packsync` files and share links, besides CurseForge `.zip` exports. The pack's name, Minecraft and loader version, icon and author come along; every file is checked by its SHA-1; server-only mods are skipped. If a file can't be downloaded, the rest still installs and PackSync lists what's missing under **Can't be downloaded**.
- **Worlds, your call.** A pack can carry worlds its author ticked. When installing it, PackSync asks which worlds to add (none ticked at first). A world with the same name as one of yours is added as a copy ("My World (2)"), so your worlds are never replaced, and **Undo** removes the copy.
- **Servers.** Run your packs as dedicated servers from PackSync:
  - **New server from a pack** leaves out the mods only players need (Sodium, Iris, minimaps, …), keeps anything another mod needs, and downloads the right server software and Java.
  - Each server has **Start** and **Stop**, a live console with a command box, its settings (port, message, max players, difficulty, whitelist, PvP, online mode, view distance, …) with checks for invalid values, and memory and Java options.
  - **Stop** saves the world the way typing `stop` does; a server is only forced to stop if you ask. Closing PackSync stops running servers properly first. Servers only start once you agree to the Minecraft EULA.

### Changed
- **CurseForge mods download by themselves in every build.** PackSync's CurseForge lookup service is built into the app, so mods that aren't on your PC download in the background with no setup. The CurseForge API key stays on the service and is never in the app. **Settings → CurseForge → API proxy** can still point a PC at a different one.
- **Fewer clicks for CurseForge mods.** When a CurseForge mod can't be downloaded directly (its author only allows downloads on CurseForge's website), PackSync uses Modrinth's copy of the exact same file (same SHA-1) when there is one. This works when checking a pack against a link, importing, and in **Install mods**. Exported and shared packs list such mods as Modrinth downloads in the first place.

### Fixed
- Importing a pack no longer forgets where its Modrinth mods came from, so they keep their names, updates and version picker on the Mods tab.

## [1.0.1] - 2026-09-30

### Added
- **Mods that don't work together are caught.** PackSync reads each mod's own requirements, as Minecraft does when it starts. The Mods tab lists every problem in plain words: a missing required mod, the wrong version of one (for example "Reese's Sodium Options 2.2.4 needs Sodium 0.8.13, but 0.6.13 is installed"), mods that say they're incompatible, a mod installed twice, or a mod for another Minecraft or loader version. Each problem has buttons that fix it: **Find a … that fits** tries versions until one works with everything else, and **Install …** adds a missing mod. PackSync also checks before **Play**.
- **Choose any version.** **Version…** on every installed mod, and **Other versions…** in the Install window, list every version for the pack's Minecraft version and loader, for when the game asks for an older or newer one.

### Fixed
- **The right version is installed.** Mods often need one exact version of another mod. Installing a mod now picks the newest version that works with the mods already in the pack (and says so when that isn't the newest), instead of always the newest. Versions a mod's author pins on Modrinth are installed as pinned, and PackSync asks first before installing a mod its author marks as incompatible with one you have.

## [1.0.0] - 2026-09-30

### Fixed
- PackSync no longer closes when the **+** menu next to *My packs* opens. Unexpected errors are now logged (details in `logs\errors.log`) instead of closing the app.
- Search results only offer what really fits the pack: its exact Minecraft version and, for mods, its loader (Quilt packs also get Fabric mods). Before, a mod with Fabric builds for an older version showed up for a newer Fabric pack and then failed to install.
- Memory stays low while browsing mods: icons are kept at icon size, and only the most recent ones stay in memory.
- A few more safety checks: only `https` downloads, file names from mod sites can't point outside the right folder, and two changes to the same pack can't run at once.
- **Play starts the game again.** CurseForge writes its loader version files with empty (`null`) fields, which made the launcher skip every library, so Fabric packs stopped with "Could not find or load main class". PackSync now uses cleaned copies in its own folder and never edits CurseForge's files.
- **Checking a pack link exported from CurseForge works.** It used to fail with "Unresolved project/file IDs" unless a lookup service was configured. Mods already installed in any CurseForge instance on this PC are now recognized and copied from there, even ones whose authors don't allow downloads by other apps.
- The **API proxy** set in Settings is now actually used, straight away.

### Added
- **PackSync is now a full Minecraft launcher.**
  - **My packs:** create your own packs (vanilla, Fabric, Quilt, Forge or NeoForge, any Minecraft version), or import one from a `.zip` or link with a CurseForge manifest, or copy a CurseForge pack. Your packs live in `Documents\PackSync\Instances`, which you can change in Settings.
  - **Mods, Resource packs, Shaders and Datapacks** tabs on every pack. They list what's installed with names and icons, and let you enable, disable, remove or update each item, or **Update all**.
  - **Install mods** (resource packs, shaders, datapacks) opens its own window: search **Modrinth** or **CurseForge**, sort, and page through results with page numbers and a *per page* choice. Each result shows the exact version that fits the pack; installed ones are marked. Required dependencies are installed automatically, and adding shaders offers Iris or Oculus.
  - The installed list has a filter, shows disabled items dimmed, and keeps updates one click away.
  - **Pack settings:** name, Minecraft and loader version, memory and Java arguments.
- **Sign in or continue as guest.** On first launch PackSync asks you to sign in with your Minecraft account; you can continue as a guest instead. The account button at the top right signs you in and out any time. Guests can create, edit and update packs; **Play** asks them to sign in first.
- **Launch logs:** each game start is written to `%LOCALAPPDATA%\PackSync\logs\launch-latest.log`, with the access token hidden. If the game closes early, PackSync shows its last lines and a button to open the log. PackSync's own log is kept for 7 days.
- **Play** is here: PackSync's Microsoft sign-in was approved. Press Play on any CurseForge pack, sign in once with the Microsoft account you play Minecraft with, and the game starts. The pack is checked (and repaired if needed) first.
- **Forge and NeoForge** packs can be played even if CurseForge never launched them: PackSync runs the official installer the first time.
- **Install CurseForge-only mods inside PackSync** (Settings → CurseForge, with a one-time agreement). Mods whose authors only allow downloads on curseforge.com open on their CurseForge download page in a window inside PackSync. The download starts by itself; PackSync checks the file, puts it in the pack's mods folder and opens the next one. A wrong version is refused.
- **Update from a link** on every CurseForge pack page, and **Check for changes** on linked packs. They show what will change (Update, Add, Needs one click, Configs & scripts, Not in this pack) with checkboxes, then **Install selected** does exactly that. Updated mods replace their old version, which is removed only once the new one is installed. Mods not in the pack are kept unless you tick them.
- **Undo changes:** after PackSync installs, repairs or updates a pack, one button (with a confirmation) puts it back exactly as it was before PackSync touched it. Added files are removed and replaced or removed files are restored. **Keep changes** forgets the saved copy.
- **Guided installs** for mods that can't be downloaded by other apps. PackSync opens each mod's CurseForge download page in turn; the download starts by itself, and PackSync installs the file and opens the next. Files it learns this way are recognized next time.
- Jars included in a pack ZIP's `overrides/mods/` are used directly.
- A ready-to-deploy **CurseForge lookup proxy** ([proxy/README.md](proxy/README.md)), so mods that aren't on the PC download automatically. The API key stays on the server, never in the app.
- **Configs and scripts in linked packs:** PackSync now keeps `config/`, `defaultconfigs/`, `kubejs/` and `scripts/` in sync too. It uses the pack ZIP's `overrides` folder or the new `overrides` list in `master_manifest.json`, and compares every file by SHA-1. See [docs/MANIFEST.md](docs/MANIFEST.md).
- **What will change:** the pack page lists every file a sync would add or replace, with outdated mods shown separately from changed configs and scripts.
- Scripts that were removed from a pack are reported as extra, so they don't keep running. The *Extra mods* setting can disable or remove them.

### Changed
- The "Open CurseForge instead" fallback next to Play is gone; Play always launches from PackSync.
- The CurseForge lookup proxy also allows CurseForge search and file lists (`GET /v1/mods/search`, `GET /v1/mods/{id}/files`), and limits each player to 300 requests a minute so nobody can use up the key. Redeploy `proxy/worker.js` to use them.
- Status badges now separate **mods missing / outdated** from **configs changed** and **scripts changed**.
- Backups also include the configs and scripts that a sync is about to replace.

### Security
- Your own settings are never overwritten, even if a pack includes them. Options and keybinds (`options.txt`) and the server list (`servers.dat`) from a pack are only used if you don't have your own yet. Worlds, screenshots and logs are never touched.

## [0.1.1] - 2026-09-28

### Changed
- The [PackSync-Releases](https://github.com/DevEhChad/PackSync-Releases) download page now has a proper README and this changelog, kept up to date with every release.

### Fixed
- Symbols such as the → arrow now show correctly in the "What's new" release notes of builds packaged on Windows PowerShell 5.1.

## [0.1.0] - 2026-09-27

First release of **PackSync**.

### Added
- **Library of your CurseForge modpacks:** everything installed in the CurseForge app appears automatically in the sidebar, most recently played first, with its artwork, version, loader and status. The list updates live when CurseForge installs, updates or removes a pack, or when mod files change.
- **Checks against CurseForge's own records:** a quick check runs automatically, and **Check all files** verifies every file's SHA-1.
- **Repair** puts back missing or changed files without touching mods you added yourself. Mods whose authors disallow other apps are fetched through your browser.
- **Update available** notice when CurseForge knows a newer pack version, with a button that opens CurseForge to update. The page refreshes by itself afterwards.
- **Open CurseForge** button on every pack to jump straight into the CurseForge app and play.
- **Linked packs:** add any number of packs from a Dropbox, Google Drive or direct `.zip` link and keep a folder in sync with it. Supports standard CurseForge `manifest.json` and extended `master_manifest.json` packs.
- Optional per-pack **manifest link** to compare a CurseForge pack against.
- **Settings** page (everything saves automatically) and a **welcome page** that explains what to do when no modpacks are found.
- **Extra mods** setting for linked packs: Keep (default), Disable (`*.jar` → `*.jar.disabled`) or Remove (asks every time).
- **Safety:** warns if Minecraft is running, checks files aren't in use before changing them, and zips `mods/` to `backups/backup-{timestamp}.zip` first (the 5 newest are kept).
- Downloads run several at a time, retry on network hiccups, and are verified before replacing anything.
- Automatic app updates from GitHub Releases.
- Uninstall removes the app and its settings without touching your instances.

### Coming later
- **Play from PackSync:** one-click launch with Microsoft sign-in. It's built but switched off until the app is approved by Microsoft for Minecraft sign-in.
