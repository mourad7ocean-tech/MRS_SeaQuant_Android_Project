MRS SeaQuant - Android build
============================
Easiest way (no installs on your PC):
 1. Create a free account on github.com and a new PRIVATE repository.
 2. Upload everything in this folder (including the hidden ".github" folder
    and the "icons" folder that holds the app icon).
 3. Open the repository > Actions tab > "Build Android APK" > Run workflow.
 4. After ~5 minutes open the finished run and download the artifact
    "MRS-SeaQuant-apk-build<number>" (a zip containing MRS-SeaQuant-build<number>.apk).
 5. Copy the .apk to the phone and install it
    (allow "Install unknown apps" when asked). The app is named "MRS SeaQuant".

Build on your own PC instead (needs Node.js 20+, JDK 17, Android SDK):
    npm install
    npx cap add android
    (copy everything inside the icons/ folder into android/app/src/main/res/)
    npx cap sync android
    cd android && gradlew assembleDebug
    APK: android/app/build/outputs/apk/debug/app-debug.apk

To update the app later: replace www/index.html with the new HTML file and rebuild.

IMPORTANT: uninstall any older version of the app from the phone before installing
the new APK, otherwise Android may keep showing the old icon.
When you tap the APK, the install window must show the SeaQuant logo. If it shows a blue "X",
you are installing an old APK: delete it and use the newest build from the Actions tab.
