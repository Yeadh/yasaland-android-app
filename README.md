# YASA LAND - PLAY & LEARN (Android app)

Kids' 3D game: find hidden letters, animals and vegetables in an open field.
Web app lives in `www/` (index.html + three.min.js, works offline). Wrapped as an Android app with Capacitor.

## Get the APK (no Android Studio needed)
1. Create a free GitHub account and a new repository.
2. Upload everything in this folder to it (drag & drop in the browser works; keep the `.github` folder).
3. Open the repo -> Actions -> "Build Android APK" -> Run workflow (it also runs on every push).
4. When it turns green, open the run -> Artifacts -> download `YasaLand-debug-apk` -> unzip -> `app-debug.apk`.
5. Copy the APK to an Android phone and install it (allow "install unknown apps").

## Build locally instead
Needs Node 20, JDK 17 and Android Studio.
    npm install --legacy-peer-deps
    npx cap sync android
    npx cap open android      # then Build > Build APK(s)

## Change the game later
Edit `www/index.html`, then run `npx cap sync android` and rebuild.

## Play Store notes
- Change `appId` in capacitor.config.json (com.yasaland.playlearn) to your own before publishing.
- Play needs a signed release (AAB) with your own keystore, a privacy policy, and the Families/Kids policy answers.
- `playstore-icon-512.png` is the 512x512 store icon.

## Also a PWA
`www/` can be hosted on any HTTPS site; browsers can then "Install app" (manifest + service worker included).
