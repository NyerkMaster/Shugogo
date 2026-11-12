# Shugogo

A fan-made radar overlay for **Aion 2**. Shugogo isn't made by, endorsed by or affiliated with NCSOFT, or with MetaBot.GG, questlog.gg, Shugo.GG or any other site whose data it uses.

## What it shows

- **Hidden Cubes** near you, with a sound and a direction the moment one appears
- **The world map** with your position (read from the game's minimap), players by faction and monsters
- **Pet souls** you still need: which monsters nearby drop them, and the Black Cloud Merchant's pet offers
- **Upcoming events** (rifts, sieges, Abyss bosses, the Shugo Festival) with optional spoken reminders
- **A Gains Tracker**: Kinah, Abyss Points and rank points per hour, and a chart of what you earned in each 5 minutes, starting by itself at each login
- **Your currencies** at the right of the status row: Odyle Energy, and your Nightmare and Ascension Trial attempts and Shugo Festival and Dimensional Invasion keys as the game counts them
- **Combat:** a DPS meter (everyone's damage, skills and targets; honest about field bosses) and a log of your kills, deaths and assists, with each player's name a link to their Shugo.GG page
- **A Raid Tracker** (beta) for Abyssal Forge: Ludra: every pull's damage over time, the boss's HP, who died, when and to what, your progress across the nights and the people you've raided with
- **Only what you want on screen**: click Radar, Event Timers, Combat, Gains Tracker or Pets in the bar to show each one under it, in any mix

## The Combat window

**Combat** in the bar shows your K/D/A and the top five of the fight; its **Detailed** button opens the window. **Damage** is a DPS meter: from the first damage of the fight to its end it shows your damage and, on ordinary monsters, in dungeons and in PvP in view, everyone else's (you, your party, or everyone: your choice), with each player's class icon, skills and targets, a boss's HP and a kill estimate, your best on each boss, and the last 30 fights to step through. It has two looks, **Vibrant** (the default: each player a bar in their class's colour) and **Plain** (the rows as text), chosen in the Combat section or the window. On a field boss the server sends only your own damage, so the meter says so and shows only yours, as a share of the boss's HP. **K/D/A** logs every player you kill, who killed you (and the Abyss Rank Points it cost) and your assists, counted the way the game counts them: an ally's kill of a player your own hits did at least 10 % of their HP to in the 30 seconds before. Click a name to open that player's page on Shugo.GG in your browser; **Hide other players' names** is there for screenshots and streams. The Combat section keeps score: your K / D / A beside its name, the fight line and the top five rows (a party), yours among them; three or four when the window wouldn't fit your screen otherwise. Other players' names stay on your PC, in the window and in `user_data/kda.jsonl`; they never go into a log.

## The Raid Tracker (beta)

It's new and may have mistakes (a cause of death, a missed death, someone's damage): check anything important
in game.

**Raids** in the Combat section, or **Raids ↗** in the Combat window, opens it. In Abyssal Forge: Ludra (Normal and
Hard), and in any instance boss fight with 6 or more players, it records every pull: everyone's damage second by second,
the boss's HP, and who died, when and to what (the game's own death message). A pull under 10 seconds that isn't a kill
doesn't count.

- **Raid**: one pull at a time. Duration, Party DPS, Damage taken and Deaths; the **Damage** and **Damage taken** charts
  with a ☠ at each death and the boss's HP; the players' table; **Deaths** (what you, your party or everyone die to,
  and a death's last 10 seconds); **Timeline** (a lane per player).
- **History**: the boss's HP left at the end of every pull across the nights (a wipe's: where the boss was when it
  reset), and your bests on each boss.
- **People**: everyone you've raided with: how often they died, how often first, and their damage against the same
  class on the same boss. Numbers, not verdicts: the game doesn't say why someone died.

A boss's skills show as a number ("skill 1803110") until you name them (right-click). The raid history stays on your PC,
in `user_data/raids/`, never in a log; **Hide other players' names** hides names here too, and **Forget**, **Don't
track**, **Clear raid history…** and **Reset everything…** delete it.

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
- **A click on a player's name** in the Combat window or the Raid Tracker opens their [Shugo.GG](https://shugo.gg) page in your browser, only then: Shugogo itself never contacts Shugo.GG.
- **Nothing about you or your PC is ever sent:** no account, no sign-in, no telemetry, no usage statistics, no crash reports. (Like any website, the sites it downloads from see your IP address.) Your settings, logs, recordings and raid history stay in `user_data/` on your PC.

## Risk

Reading the game's traffic is against NCSOFT's terms of service. **Using Shugogo could get your account banned. Use it
at your own risk.**

## Licence

Shugogo is free to use, but it isn't open source (© 2026 NyerkMaster). You may install it, use it and share copies of
the official, unmodified downloads, free of charge. Modifying it, reverse engineering, decompiling or disassembling it
(except where the law allows that regardless), selling it and repackaging it aren't allowed. The full terms are in
`LICENSE.txt`, which Setup shows before it installs and puts beside `Shugogo.exe`. The third-party parts inside
Shugogo (Python, Tcl/Tk, numpy, Pillow, PyInstaller's starter and run-time files) and its installer and uninstaller
(made with Inno Setup) keep their own licences, in the `licenses` folder beside it, with the credits of the data
Shugogo uses: the pet data's, with the MIT notices of the two projects it uses (`Pet data.txt`), the NPC names'
(`NPC names.txt`: questlog.gg and MetaBot.GG), the skill names' (`Skill names.txt`: MetaBot.GG and questlog.gg), the
event schedule's (`Event schedule.txt`: Shugo.GG, questlog.gg and MetaBot.GG), the map data's (`Map data.txt`:
MetaBot.GG's public maps) and the currency icons' (`Game icons.txt`: NCSOFT's art, four by way of MetaBot.GG, one from the game's window). Shugogo comes
with no warranty.

## Credits

Shugogo's game data comes from public Aion 2 sites, used with their permission; the files in the `licenses` folder
link every page used. Game data and art © NCSOFT.

- **Map data and map pictures:** [MetaBot.GG's maps](https://metabot.gg/en/aion-2/map): [Altgard](https://metabot.gg/en/aion-2/map/altgard),
  [Morheim](https://metabot.gg/en/aion-2/map/morheim), [Verteron](https://metabot.gg/en/aion-2/map/verteron), [Eltnen](https://metabot.gg/en/aion-2/map/eltnen),
  [Chaotic Lower Reshanta](https://metabot.gg/en/aion-2/map/chaotic-lower-reshanta),
  [Chaotic Middle Reshanta](https://metabot.gg/en/aion-2/map/chaotic-middle-reshanta) and
  [Chaotic Upper Reshanta](https://metabot.gg/en/aion-2/map/chaotic-upper-reshanta).
- **NPC names:** [questlog.gg's NPC database](https://questlog.gg/aion-2/en/db/npcs) and
  [map](https://questlog.gg/aion-2/en/map), and MetaBot.GG's field-boss and NPC pages.
- **Skill names:** [MetaBot.GG's Aion 2 skills](https://metabot.gg/en/aion-2/skills) and [questlog.gg's skill database](https://questlog.gg/aion-2/en/db/skills).
- **Currency icons:** the game's own art, from MetaBot.GG's item pages (the Ascension Trial ticket turned violet):
  [Odyle Energy](https://metabot.gg/en/aion-2/items/odyle-energy-bound),
  [Nightmare Dungeon Challenge Ticket](https://metabot.gg/en/aion-2/items/nightmare-dungeon-challenge-ticket-bound),
  [Ascension Trial Challenge Ticket](https://metabot.gg/en/aion-2/items/ascension-trial-challenge-ticket-bound),
  [Shugo Festival Reward Key](https://metabot.gg/en/aion-2/items/shugo-festival-reward-key-bound); the Dimensional Invasion key, which has no page, is cut
  from the game's own window (and turned silver).
  Nothing is downloaded for them.
- **Event schedule:** [Shugo.GG's timers](https://shugo.gg/timers),
  [questlog.gg's boss schedule](https://questlog.gg/aion-2/en/boss-schedule) and [MetaBot.GG's timers](https://metabot.gg/en/aion-2/events).
- **Pet data:** [questlog.gg](https://questlog.gg/aion-2), [MetaBot.GG](https://metabot.gg/en/aion-2/mounts),
  [aion2.app](https://aion2.app/db/pets), [aion2.th.gl](https://aion2.th.gl/db/pets) and [Shugo.GG](https://shugo.gg),
  and the MIT-licensed [Tomtoxi44/aion2-pet-meter](https://github.com/Tomtoxi44/aion2-pet-meter) and
  [MartinLVila/aion2-pet-overlay](https://github.com/MartinLVila/aion2-pet-overlay).
- **The installer** is made with [Inno Setup](https://jrsoftware.org/isinfo.php).
