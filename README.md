# KENZEN Cockpit for Android (Perchance Edition)

KENZEN Cockpit is a touch-first mobile prompt engineering studio engineered specifically for Perchance.org AI image generators (including Mack's Place, The Imaginarium, Qinegen, and AI Real Revolution). It adapts the deep 41-category matrix taxonomy of Tomohito Fujikawa's desktop helper into a responsive, one-handed Android application.

## Core Features
- Complete 41-category Matrix covering anatomy, style anchors, camera optics, wardrobe, and composition.
- Natural Language Flux Prose Synthesizer (converts tags into coherent descriptive sentences).
- Multi-slot layout generator for Mack's Place (Main, Style, Subject, Fashion, Scene, Pose, Aesthetic, Negative).
- Touch Inspector: tap for comma separation, long-press for prepositional space joining, weight modulation, and alternation blocks.
- Offline persistence via local storage and Service Worker.
- Direct-launch dispatchers for Perchance generators with pre-encoded prompt URLs.

## Project Structure
```text
├── .github/workflows/build-apk.yml   # GitHub Actions automated build pipeline
├── android/                          # Native Android Gradle project
│   ├── app/                          # Main Android application module
│   ├── build.gradle                  # Top-level build configuration
│   ├── gradle/wrapper/               # Gradle wrapper binaries & properties
│   └── gradlew                       # Gradle execution script
├── capacitor.config.json             # Capacitor runtime configuration
├── package.json                      # Build scripts and dependencies
└── www/                              # Web application assets
    ├── index.html                    # Single-file Cockpit studio
    ├── manifest.json                 # Web App Manifest
    └── sw.js                         # Offline cache service worker
```

## Compilation Instructions

### Option 1: Automated Cloud Build (GitHub Actions)
1. Push this repository to GitHub.
2. Navigate to the **Actions** tab.
3. Select **Build Android APK** and click **Run workflow** (or simply push to `main`).
4. Once completed, download the installable `KENZEN-Cockpit-Perchance.apk` from the **Artifacts** section.

### Option 2: Local Command Line (macOS / Linux / WSL)
Prerequisites: JDK 17, Android SDK Platform 34, Node.js 20+.
```bash
npm install
npx cap sync android
cd android
chmod +x gradlew
./gradlew assembleDebug
```
The compiled package will be located at:
`android/app/build/outputs/apk/debug/app-debug.apk`

### Option 3: Android Studio
1. Run `npm install` and `npx cap sync android`.
2. Open the `android/` directory in Android Studio.
3. Select **Build > Build Bundle(s) / APK(s) > Build APK(s)**.
