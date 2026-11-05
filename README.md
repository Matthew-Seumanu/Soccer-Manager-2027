# Pitchside Career: Android app

This project turns the Pitchside Career game into an installable Android app (APK).
GitHub builds the APK for you in the cloud. You don't need Android Studio.

## What's inside
- `www/` holds the game (index.html), with three.js, lz-string and the fonts stored locally, so it works offline
- `android/` is the Android app shell: landscape only, full screen, its own icon and splash screen
- `.github/workflows/build-apk.yml` is the cloud build that makes the APK

## Get the APK
1. Create a new **public** repository on GitHub (for example `pitchside-app`).
2. Upload everything in this folder to it, keeping the folders as they are. Include the hidden `.github` folder.
3. Open the repo's **Actions** tab. The "Build APK" run starts on its own (about 5 to 8 minutes).
4. When it shows a green tick, open the repo's **Releases** on your phone and download `PitchsideCareer-1.0.X.apk`.
5. Open the APK and allow "Install unknown apps" for your browser or Files app if Android asks.

## Updating the game later
Replace `www/index.html` with the new version of the game and commit. A new APK appears in Releases.
It installs over the old app and keeps your saved careers, because every build uses the same signing key (`android/app/pitchside.keystore`).
Don't delete or change that key, or Android will refuse the update until you uninstall (which wipes your saves).
