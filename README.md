# FlashyChord

FlashyChord is a mobile-friendly chord trainer packaged as an Android WebView app.

## Run locally

### Android debug build

```bash
cd /workspaces/FlashyChord
./gradlew assembleDebug --no-daemon -x lintVitalAnalyzeRelease -x lintAnalyzeRelease -x lint
```

This produces the APK at:

- app/build/outputs/apk/debug/app-debug.apk

### Android release build

```bash
cd /workspaces/FlashyChord
./gradlew bundleRelease --no-daemon -x lintVitalAnalyzeRelease -x lintAnalyzeRelease -x lint
```

This produces the Android App Bundle at:

- app/build/outputs/bundle/release/app-release.aab

## Upload to Google Play

1. Open Google Play Console.
2. Create or select the app.
3. Go to Release > Testing or Production.
4. Upload the AAB file from the release output folder.
5. Fill in the app details, screenshots, privacy policy, and content rating.
6. Submit for review.

## Signing

The app uses a local keystore for release signing. The credentials are stored in:

- keystore.properties
- release-keystore.jks

Keep these files private and do not commit them to a public repository. The project ignores them in Git.

## Notes

- The app loads the HTML game from app/src/main/assets/index.html.
- The Android wrapper keeps the app alive across orientation changes using WebView state restoration.
- The manifest includes orientation handling to support portrait and landscape layouts.
