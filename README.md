# Advanced Trade Skill Window 2 — WotLK 3.3.5a port

An enhanced professions window for World of Warcraft **3.3.5a** (Wrath of the Lich King),
ported for the **Ebonhold** server. It replaces the default tradeskill window with a
better one: recipe queue, shopping list, advanced search, custom recipe categories,
reagent tracking across bags/bank/alts, and more.

> This is a **community port**, not the original work. All credit for the addon goes to
> its authors (see below). This repository only adapts their Vanilla (1.12) addon to run
> on the 3.3.5a client.

## Credits — original authors

This addon is **Advanced Trade Skill Window 2** by:

- **Alexander Shelokhnev** (*Dreamios* / *Shellyoung*) — author of the ATSW2 rewrite (2022).
  Original repository: <https://github.com/Shellyoung/AdvancedTradeSkillWindow2>
- **Rene Schneider** (*Slarti*) — author of the original Advanced Trade Skill Window (2006).
- **laytya** — earlier contributor (2017).

The original project targets WoW **Vanilla 1.12** and carries **no license** (all rights
reserved by its authors). This 3.3.5a port is shared for the Ebonhold community out of
appreciation for their work. If an original author would prefer this not be hosted here,
please open an issue and it will be removed.

## What this port changes

Only compatibility fixes for the 3.3.5a client — no feature changes. Notably:

- TOC interface `11200 → 30300`.
- Vanilla events `SPELLCAST_*` → `UNIT_SPELLCAST_*` (cast progress / queue).
- Enchanting routed through the TradeSkill API (the old Craft API is absent on 3.3.5 cores).
- Lua 5.0 `arg` vararg tables → `select('#', ...)`.
- Button font/colour methods routed to the button FontString (Buttons aren't FontInstances in 3.3.5).
- `UIDropDownMenu` / `FauxScrollFrame` argument-order fixes, `string.gfind → gmatch`,
  `GetPoint(0) → GetPoint(1)`, `ChatFrameEditBox → ChatFrame1EditBox`, and the
  `OptionFrameBoxTemplate` re-provided.

## Installation

**Via the Ebonhold launcher** (recommended): Catalogue → install "Advanced Trade Skill Window 2".

**Manual**: download the latest release `.zip`, extract the `AdvancedTradeSkillWindow2`
folder into `World of Warcraft\Interface\AddOns`, then `/reload` in game.

## Usage

Open any profession — the window replaces the Blizzard one automatically.
Options: `/atsw config`.
