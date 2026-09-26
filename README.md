# WFMarketWatcher

A Windows app that watches [warframe.market](https://warframe.market) for sell orders at or below your price and alerts you in the app (sound and Windows notification) and in Discord, with a ready-to-paste whisper message.

- Price limits in plat or as a % under the average price
- Rank and variant filters, lists, pause
- Price charts, purchase log and profit share cards
- Discord webhook or bot with Bought / Gone / Whisper buttons

## Download

Get the latest version from **[Releases](../../releases/latest)**:

1. Download `WFMarketWatcher-<version>.exe` and `images.zip`.
2. Put the exe in its own folder and unzip `images` next to it.
3. Start the exe and set up Discord in ⚙ Settings (optional).

Windows SmartScreen may warn about an unknown app the first time. Click *More info → Run anyway*.

Requires Windows 10 or 11 with the Microsoft Edge WebView2 runtime (always there on Windows 11).

## Updates

The app checks this repository for new releases and shows **Update available** in the top bar. **Update now** downloads the new version next to the old one, checks it against its published SHA-256 checksum and starts it. Older versions stay in the folder, so you can always go back by starting an older exe.

## Your data

Your settings (including your Discord webhook or bot token), purchases and history are stored in files next to the exe and never leave your PC. **Don't share your `config.json`.**
