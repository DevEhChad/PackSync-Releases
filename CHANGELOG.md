# Changelog

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
