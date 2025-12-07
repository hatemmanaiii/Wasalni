# Building APK for Wasalni App

## Prerequisites

1. **Android Studio** - Download and install from [https://developer.android.com/studio](https://developer.android.com/studio)
2. **Java Development Kit (JDK)** - Android Studio includes this, or install JDK 11 or later
3. **Android SDK** - Installed through Android Studio

## Steps to Build APK

### Option 1: Using Android Studio (Recommended)

1. **Open Android Studio**
   - Launch Android Studio
   - Select "Open an Existing Project"
   - Navigate to: `wasalniservice-main/android`
   - Click "OK"

2. **Wait for Gradle Sync**
   - Android Studio will automatically sync the project
   - This may take a few minutes the first time

3. **Build the APK**
   - Go to: `Build` → `Build Bundle(s) / APK(s)` → `Build APK(s)`
   - Wait for the build to complete
   - When done, click "locate" in the notification
   - The APK will be in: `android/app/build/outputs/apk/debug/app-debug.apk`

### Option 2: Using Command Line

1. **Navigate to Android directory**
   ```powershell
   cd wasalniservice-main\android
   ```

2. **Build the APK**
   ```powershell
   .\gradlew assembleDebug
   ```

3. **Find the APK**
   - Location: `android/app/build/outputs/apk/debug/app-debug.apk`

## Important Notes

- **Debug APK**: The APK built using the above methods is a **debug APK** suitable for testing
- **Release APK**: For production, you need to:
  1. Generate a signing key
  2. Configure signing in `android/app/build.gradle`
  3. Build using `assembleRelease` or through Android Studio

## After Making Changes to Your Web App

If you make changes to your React app:

1. **Rebuild the web app:**
   ```powershell
   npm run build
   ```

2. **Sync with Capacitor:**
   ```powershell
   npx cap sync
   ```

3. **Rebuild the APK** using one of the methods above

## Quick Commands

```powershell
# Build web app and sync
npm run build && npx cap sync

# Open Android Studio
npx cap open android

# Or use the combined command
npm run android:build
```

## Troubleshooting

- **Gradle sync fails**: Make sure you have a stable internet connection and Android Studio is updated
- **Build errors**: Check that Android SDK is properly installed in Android Studio
- **APK not installing**: Make sure "Install from unknown sources" is enabled on your Android device

