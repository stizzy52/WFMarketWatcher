**⚠️ Disclaimer: This software was made for me and my friends. It has not been checked for compliance with the Terms of Service of Warframe or warframe.market. Every user uses it at their own risk and bears the risk of any punishment, including suspensions and bans.**

# WFMarketWatcher

A Windows app that watches [warframe.market](https://warframe.market) for sell orders at or below your price and alerts you in the app (sound and Windows notification) and in Discord, with a ready-to-paste whisper message.

- Price limits in plat or as a % under the average price
- Rank and variant filters, lists, pause
- Price charts, purchase log and profit share cards
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

## Updates

The app checks this repository for new releases and shows **Update x.y.z** in the top bar. **Update now** downloads the new version and checks it against its published SHA-256 checksum. If it matches, it replaces `WFMarketWatcher.exe` and restarts; if not, nothing changes. Your settings and data stay, and shortcuts keep working.

Every version stays available here under [Releases](../../releases), in case you ever want an older one.

## Your data

Your settings (including your Discord webhook or bot token), purchases and history are stored in files next to the exe and never leave your PC. **Don't share your `config.json` or your backups.** Watchlist codes contain only items and limits, so those are safe to share.

---

**⚠️ Disclaimer: This software was made for me and my friends. It has not been checked for compliance with the Terms of Service of Warframe or warframe.market. Every user uses it at their own risk and bears the risk of any punishment, including suspensions and bans.**
