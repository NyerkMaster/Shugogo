# Shugogo

A fan-made radar overlay for **Aion 2**. Shugogo is not made by or affiliated with NCSOFT or Shugo.GG.

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

Shugogo updates itself: once a day it checks this page for a new version and asks before installing anything
(⚙ Settings → General).

## How it works, and privacy

Shugogo only **listens** to the game's network traffic (through Npcap) and reads the game's minimap from your screen.
It never touches the game's files or memory and never sends anything to the game or its servers. The only thing it
downloads is the map pictures (once) and one small file from this page a day to look for updates; nothing about you or
your PC is sent, and you can switch the update check off.

## Risk

Reading the game's traffic is against NCSOFT's terms of service. **Using Shugogo could get your account banned. Use it
at your own risk.**

## Licence

GPL-3.0. Every release includes its full source code (`Shugogo-<version>.zip`).
