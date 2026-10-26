# Shugogo

A fan-made radar overlay for **Aion 2**. Shugogo isn't made by, endorsed by or affiliated with NCSOFT, or with MetaBot.GG, questlog.gg, Shugo.GG or any other site whose data it uses.

## What it shows

- **Hidden Cubes** near you, with a sound and a direction the moment one appears
- **The world map** with your position (read from the game's minimap), players by faction and monsters
- **Pet souls** you still need: which monsters nearby drop them, and the Black Cloud Merchant's pet offers
- **Upcoming events** (rifts, sieges, Abyss bosses, the Shugo Festival) with optional spoken reminders
- **A farming tracker**: Kinah, Abyss Points and rank points per hour
- Collapse the map when you only want the timers

## Install

1. Install **[Npcap](https://npcap.com/#download)** (free) with its default options. Shugogo needs it to see the game's network traffic.
2. Download **`Shugogo-Setup-<version>.exe`** from **[Releases](../../releases/latest)** and run it. No administrator rights needed.
3. Windows may say "Windows protected your PC" because the installer isn't code-signed: click **More info → Run anyway**.

No installer wanted? **`Shugogo-<version>-windows.zip`** holds the same program: unzip it somewhere permanent and run `Shugogo.exe`.

Shugogo updates itself: once a day it checks this page for a new version and asks before installing anything
(⚙ Settings → General).

**The files on a release:** `Shugogo-Setup-<version>.exe` (install this), `Shugogo-<version>-windows.zip` (the same
program without an installer), `latest.json` (what the built-in updater reads) and, for a small update,
`Shugogo-<version>-code.zip` (the updater's download, nothing to run by itself). GitHub adds **Source code (zip)** and
**Source code (tar.gz)** to every release by itself: those only hold this page, not Shugogo's code.

## What Shugogo does and doesn't do

- **It only listens.** It reads a copy of the game's network traffic through [Npcap](https://npcap.com) (as Wireshark and the DPS meters do), only this PC's own traffic, and only the game's connections are decoded.
- **It reads the minimap from your screen** (a few times a second, only that small part of the screen) to know where you are.
- **It never touches the game:** not its files, not its memory, not its process. It sends nothing to the game or its servers and injects nothing.
- **All it downloads:** the map pictures, once per region (from MetaBot.GG, kept in `user_data/maps/`); one small file a day from GitHub to see whether there's a new version (`latest.json`, a few KB; untick **Check for updates once a day** to stop it); and an update, only when you click **Install**. Updates are signed and checked before they're used.
- **Nothing about you or your PC is ever sent:** no account, no sign-in, no telemetry, no usage statistics, no crash reports. (Like any website, the sites it downloads from see your IP address.) Your settings, logs and recordings stay in `user_data/` on your PC.

## Risk

Reading the game's traffic is against NCSOFT's terms of service. **Using Shugogo could get your account banned. Use it
at your own risk.**

## Licence

Shugogo is free to use, but it isn't open source (© 2026 NyerkMaster). You may install it, use it and share copies of
the official, unmodified downloads, free of charge. Modifying it, reverse engineering, decompiling or disassembling it
(except where the law allows that regardless), selling it and repackaging it aren't allowed. The full terms are in
`LICENSE.txt`, which Setup shows before it installs and puts beside `Shugogo.exe`. The third-party parts inside Shugogo
(Python, Tcl/Tk, numpy, Pillow, PyInstaller's starter and run-time files) and its installer and uninstaller (made with
Inno Setup) keep their own licences, in the `licenses` folder beside it, with the credits of the data Shugogo uses: the
pet data's, with the MIT notices of the two projects it uses (`Pet data.txt`), the NPC names' (`NPC names.txt`:
questlog.gg and MetaBot.GG), the event schedule's (`Event schedule.txt`: Shugo.GG, questlog.gg and MetaBot.GG) and the
map data's (`Map data.txt`: MetaBot.GG's public maps). Shugogo comes with no warranty.

## Credits

Shugogo's game data comes from public Aion 2 sites, used with their permission; the files in the `licenses` folder
link every page used. Game data © NCSOFT.

- **Map data and map pictures:** [MetaBot.GG's maps](https://metabot.gg/en/aion-2/map): [Altgard](https://metabot.gg/en/aion-2/map/altgard),
  [Morheim](https://metabot.gg/en/aion-2/map/morheim), [Verteron](https://metabot.gg/en/aion-2/map/verteron), [Eltnen](https://metabot.gg/en/aion-2/map/eltnen),
  [Chaotic Lower Reshanta](https://metabot.gg/en/aion-2/map/chaotic-lower-reshanta),
  [Chaotic Middle Reshanta](https://metabot.gg/en/aion-2/map/chaotic-middle-reshanta) and
  [Chaotic Upper Reshanta](https://metabot.gg/en/aion-2/map/chaotic-upper-reshanta).
- **NPC names:** [questlog.gg's NPC database](https://questlog.gg/aion-2/en/db/npcs) and
  [map](https://questlog.gg/aion-2/en/map), and MetaBot.GG's field-boss and NPC pages.
- **Event schedule:** [Shugo.GG's timers](https://shugo.gg/timers),
  [questlog.gg's boss schedule](https://questlog.gg/aion-2/en/boss-schedule) and [MetaBot.GG's timers](https://metabot.gg/en/aion-2/events).
- **Pet data:** [questlog.gg](https://questlog.gg/aion-2), [MetaBot.GG](https://metabot.gg/en/aion-2/mounts),
  [aion2.app](https://aion2.app/db/pets), [aion2.th.gl](https://aion2.th.gl/db/pets) and [Shugo.GG](https://shugo.gg),
  and the MIT-licensed [Tomtoxi44/aion2-pet-meter](https://github.com/Tomtoxi44/aion2-pet-meter) and
  [MartinLVila/aion2-pet-overlay](https://github.com/MartinLVila/aion2-pet-overlay).
- **The installer** is made with [Inno Setup](https://jrsoftware.org/isinfo.php).
