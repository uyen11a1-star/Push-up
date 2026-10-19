# PushUp Quest — Android starter project

A free-first Android app starter: cute fantasy UI, workout session, on-device pose detection, rep counter, XP and local progress.

## Open and build
1. Download and unzip this project.
2. Install Android Studio on a computer (Android Studio is the easiest route for building APKs).
3. Choose **Open** and select the `PushUpQuest` folder.
4. Let Gradle sync. Use JDK 17 if Android Studio asks.
5. Connect an Android phone with USB debugging enabled, or use an emulator. Camera rep counting needs a real camera for meaningful testing.
6. Press Run. To build an APK: **Build > Build APK(s)**. Android Studio shows the APK location when finished.

This starter does not include the Gradle wrapper JAR. Opening in Android Studio and letting it sync is the simplest route.

## How the counter works
- ML Kit Pose Detection runs on-device; no API key or cloud server is required.
- Best camera placement: phone stable, landscape/side view, full upper body visible, good lighting.
- The prototype estimates reps from the shoulder-elbow-wrist angle. It counts after a high-angle (top) -> low-angle (bottom) -> high-angle cycle.
- This is a prototype, not a certified fitness or medical tool. Pose estimation can miss reps depending on camera angle, clothing, lighting and body visibility. Test slowly and adjust thresholds if needed.
- Camera permission is requested at runtime. No camera frames are uploaded by this code.

## Project layout
- `app/src/main/java/com/nyra/pushupquest/MainActivity.kt` — UI and session logic
- `app/src/main/java/com/nyra/pushupquest/PushUpCamera.kt` — CameraX + ML Kit pose detector
- `app/src/main/AndroidManifest.xml` — camera permission and app setup

## Next upgrades
1. Improve rep classification with shoulder/hip alignment and confidence checks.
2. Add workout history/calendar and a character progression system.
3. Add sound/haptics, accessibility options and a setup tutorial.
4. Test on several phones and tune the rep thresholds before release.
