# Brokenithm-Android 32-Axis Fork

Based on [tindy2013/Brokenithm-Android](https://github.com/tindy2013/Brokenithm-Android)

## Changes from Original

This fork adds **32-axis support** and updates the build environment for modern development.

### Key Changes

#### 32-Axis Support
- Increased slider buttons from 16 to 32
- LED display now shows all 32 buttons
- Touch input mapped to 32 distinct areas across the screen
- Compatible with existing Brokenithm-Android-Server (already supports 32 axes)

#### Build Environment Updates
- **Android Gradle Plugin**: 4.2.2 → 8.1.0
- **Kotlin**: 1.5.21 → 1.9.0
- **Gradle**: 6.7.1 → 8.5
- **compileSdk/targetSdk**: 30 → 34
- **Repository migration**: jcenter → mavenCentral + jitpack.io

#### Android 12+ Compatibility
- Added `PendingIntent.FLAG_IMMUTABLE` for NFC foreground dispatch
- Added `android:exported` attributes for activities
- Compatible with Android 12+ security requirements

#### Layout Changes
- Replaced `ExpandableLayout` (jcenter dependency) with `LinearLayout`
- Control panel expand/collapse functionality preserved using visibility toggles
- Added `clickable="false"` to TextViews to prevent touch interference

### LED Display

The LED display uses a 32-axis layout with proper button-to-gap ratio:
- 32 buttons displayed across the screen
- Visual appearance maintains original 16-axis ratio for familiarity
- LED data received from server in correct order (right-to-left in original code)

### Installation

1. Build the APK: `./gradlew assembleDebug`
2. Install `app/build/outputs/apk/debug/app-debug.apk` on your Android device
3. Connect to Brokenithm-Android-Server

### Server Compatibility

Works with existing [Brokenithm-Android-Server](https://github.com/tindy2013/Brokenithm-Android-Server) - no server changes required.

### Credits

- Original project: [tindy2013/Brokenithm-Android](https://github.com/tindy2013/Brokenithm-Android)
- LED display reference: [SinaKh0/Brokenithm-Slide-Android](https://github.com/SinaKh0/Brokenithm-Slide-Android)

### License

Same as original project.
