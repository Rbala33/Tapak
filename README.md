# Tapak Karya Order Manager – Android project

## Easiest: build the APK on GitHub (no Android Studio)
1. Create a free GitHub account and a new private repository.
2. Upload ALL files from this folder (keep the `.github` folder).
3. Open the repo > Actions > "Build debug APK" > Run workflow (it also runs on every upload).
4. When it finishes (about 5 min), open the run and download the artifact `tapak-karya-debug-apk`. Unzip it to get `app-debug.apk`.
5. Upload `app-debug.apk` in Firebase Console > Test Lab > Run a test > Robo test.

## Alternative: build on your computer
Needs Node 20+, Java 21 and Android Studio.
    npm install
    npm run prep
    npx cap add android
    (add <uses-permission android:name="android.permission.CAMERA" /> before </manifest> in android/app/src/main/AndroidManifest.xml)
    npx cap sync android
    cd android && ./gradlew assembleDebug
APK: android/app/build/outputs/apk/debug/app-debug.apk

## Notes
- Debug APK is for testing only. A release build for the Play Store needs your own signing key.
- Backup, Excel and PDF files open the Android share sheet (save to Files, Drive, WhatsApp...).
- Data is stored inside the app. Uninstalling the app deletes it, so use "Save backup file".
- Browser-style notifications do not work in the app; reminders show inside the app.
