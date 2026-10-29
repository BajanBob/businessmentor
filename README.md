# My BUSINESS Mentor

Speak or type your business idea; get a concept, 20 hard questions with scrutiny and true stories read aloud, and local registration steps.

One shared app in `www/` is wrapped for every platform:

| Platform | Shell | You get |
|---|---|---|
| Windows 10/11 | Electron | installer `.exe` (x64 + ARM64) and portable `.exe` |
| macOS (Intel + Apple Silicon) | Electron | universal `.dmg` and `.zip` |
| Linux | Electron | `.AppImage` and `.deb` |
| Raspberry Pi (64-bit and 32-bit) | Electron | arm64 / armv7l `.AppImage` and `.deb` |
| Android | Capacitor | `.apk` |
| iPhone / iPad | Capacitor | simulator build and unsigned `.ipa` |
| Web | GitHub Pages | https://YOUR-NAME.github.io/REPO/ |

## Build everything (no setup on your computer)

1. Put this folder in a GitHub repository (include the hidden `.github` folder).
2. **Actions → Build My BUSINESS Mentor → Run workflow.** About 15 minutes later, download each platform from the run's **Artifacts**.
3. Push a tag such as `v1.0.0` to also attach every installer to a GitHub Release.
4. For the website: **Settings → Pages → Source: GitHub Actions**. The **Publish website** workflow then updates it on every push to main.

## Build on your own computer (Node.js 20+)

```bash
npm install
npm start             # run the desktop app
npm run dist:win      # or dist:mac, dist:linux, dist:pi
npm run android:add && npm run android:apk
```

## Installing

- **Windows:** unsigned, so SmartScreen warns. Choose **More info → Run anyway**.
- **macOS:** right-click the app → **Open** the first time. If it says the app is damaged: `xattr -cr "/Applications/My BUSINESS Mentor.app"`.
- **Raspberry Pi:** `sudo apt install ./My-BUSINESS-Mentor-1.0.0-linux-arm64.deb`. Add `--no-gpu` if the window stays blank.
- **Android:** open the `.apk` and allow "install unknown apps".
- **iPhone:** Apple requires signing. Open the project in Xcode with your Apple ID, or re-sign the `.ipa` with AltStore or Sideloadly.

## Claude review in the installed app

Claude can only check code inside the Claude version of Coder for Babies. In the installed app, step 6 runs the built-in quick check. If it finds no errors, tap **Approve without Claude** twice to unlock releases.
