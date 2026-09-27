**⚠️ Disclaimer: This software was made for me and my friends. It has not been checked for compliance with the Terms of Service of Warframe or warframe.market. Every user uses it at their own risk and bears the risk of any punishment, including suspensions and bans.**

**The relic reward overlay doesn't work in exclusive fullscreen.** Play Warframe in *Borderless Fullscreen* or *Windowed*. In exclusive fullscreen the game draws straight to the monitor and bypasses the Windows desktop, so no window can be shown on top of it and screenshots often come out black. Overlays like Steam's or Discord's get around this by injecting code into the game; WFMarketWatcher deliberately doesn't.

# WFMarketWatcher

A Windows app that watches [warframe.market](https://warframe.market) for sell orders at or below your price and alerts you in the app (sound and Windows notification) and in Discord, with a ready-to-paste whisper message.

- Price limits in plat or as a % under the average price
- Rank and variant filters, lists, pause
- Price charts, purchase log and profit share cards
- Relic reward prices shown above the reward cards, in a layout you can edit (optional, read-only)
- Opportunities: flips (buyers paying more than sellers ask) and sets vs parts
- Share watchlists with a code; back up and restore your data; export purchases as CSV
- Discord webhook or bot with Bought / Gone / Whisper buttons

## Download

Get the latest version from **[Releases](../../releases/latest)**:

1. Download `WFMarketWatcher-<version>.exe` and `images.zip`.
2. Put the exe in its own folder and unzip `images` next to it.
3. Start the exe. On its first start it moves itself to `WFMarketWatcher.exe` and restarts once. Set up Discord in ⚙ Settings if you want alerts there.

Windows SmartScreen may warn about an unknown app the first time. Click *More info → Run anyway*.

Requires Windows 10 or 11 with the Microsoft Edge WebView2 runtime (always there on Windows 11).

## Relic reward prices (optional, off by default)

When the relic reward screen opens, the app shows a box just above each reward card with its price. Turn it on in ⚙ Settings → **Relic rewards**; set your Warframe **HUD scale** there (Options → Interface → HUD Scale) and play in *Borderless* or *Windowed*.

**What it watches for.** It reads Warframe's log file, `%LOCALAPPDATA%\Warframe\EE.log`, opened read-only, and waits for these two lines:
- `ProjectionRewardChoice.lua: Got rewards`: the reward cards are shown, so the prices appear.
- `ProjectionRewardChoice.lua: Relic reward screen shut down`: the screen closed, so the prices disappear.

Optionally a hotkey (e.g. `ctrl+F9`) triggers it by hand instead.

**What it reads, and how it's used:**
1. A screenshot of **only the reward-card row**, taken with Windows' normal screen capture.
2. Windows' built-in text recognition reads the item names **on your PC**. It works with any Warframe UI theme colour.
3. The names are matched to warframe.market items, and **only those item names** are used to look up prices (at most 2 requests per second).
4. The screenshot is discarded right away, unless you turn on **Keep all screenshots**, which saves each one as a PNG in a folder you choose. Nothing is ever uploaded.

**What it never does:** read or change the game's memory, inject anything into the game, modify game files, or send the game any keys or clicks. You still pick your reward yourself.

The boxes can show the item name, the cheapest in-game price, the average price (1D / 1W / 1M / 3M), ducats and how many sold, each switchable, plus a **BEST** highlight by plat or ducats. Their colours, size and position are set in ⚙ Settings → **Overlay**, with **Preview on screen**. **Edit layout…** opens an editor over the game with sample boxes: drag each box where you want it and drag its edges or corners to resize it (the text follows the size). Boxes snap to each other, the reward cards, the screen centre and a grid sized for your resolution; **Snapping** and **Grid** can be switched off in the editor's top bar, and holding Alt places a box freely. **Apply** saves the layout in `config.json`; **Use the default layout** goes back. The overlay window is click-through and never takes focus from the game.

## Trade detection (optional, off by default)

The app can notice your finished in-game trades and update itself. Turn it on in ⚙ Settings → **Trades**.

**What it watches for.** It reads the same log file, `%LOCALAPPDATA%\Warframe\EE.log`, opened read-only, and waits for:
- `Are you sure you want to accept this trade? You are offering: …`: the trade confirmation, with what you give (e.g. `Platinum x 5`), the player's name (`and will receive from <name> the following:`) and what you get.
- `The trade was successful!`: the trade went through. A trade that's cancelled or fails changes nothing.

**What it does with it:**
- **You pay plat for items from a found deal's seller:** the deal is marked **Bought** at the plat you actually paid, the purchase is logged, and the Discord alert is updated.
- **You pay plat for items that aren't a found deal:** they're logged as purchases (can be switched off).
- **You trade an item you bought away for plat:** its **Sold for** is filled in.
- With several items in one trade, the plat is split between them. Item-for-item trades are only noted in the activity log.

It needs the game in English (the log texts are in the game's language) and runs on the PC that plays the game. **What it never does:** read or change the game's memory, inject anything, modify game files, or send the game keys or clicks.

## Updates

The app checks this repository for new releases and shows **Update x.y.z** in the top bar. **Update now** downloads the new version and checks it against its published SHA-256 checksum. If it matches, it replaces `WFMarketWatcher.exe` and restarts; if not, nothing changes. Your settings and data stay, and shortcuts keep working.

Every version stays available here under [Releases](../../releases), in case you ever want an older one.

## Your data

Your settings (including your Discord webhook or bot token), purchases and history are stored in files next to the exe and never leave your PC. **Don't share your `config.json` or your backups.** Watchlist codes contain only items and limits, so those are safe to share.

---

**⚠️ Disclaimer: This software was made for me and my friends. It has not been checked for compliance with the Terms of Service of Warframe or warframe.market. Every user uses it at their own risk and bears the risk of any punishment, including suspensions and bans.**
