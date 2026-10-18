# Melon — Flutter cross-platform starter

A dark-cinematic starter app for Android and iOS, with the Melon green visual identity.

## Included in this starter
- Home dashboard, Explore, Learn, Connect, Saved and profile screens
- Local content search
- Save/unsave sample content
- Pick a photo or video from the device, or take a photo
- Demo chat screens with temporary in-memory messages
- Dark theme with neon-green accents

## Important limitations
This is a working **starter project**, not yet a production social platform. User accounts, cloud photo/video hosting, real-time messaging, push notifications, moderation, and cross-device saved content require a backend and security/privacy work. The current profile is a local demo profile; sample posts are placeholder content.

## Requirements
- Flutter SDK (stable channel)
- Android Studio with Android SDK for Android builds
- For iOS builds: macOS with Xcode installed (Apple requires Xcode for signing and App Store distribution)

Install Flutter: https://docs.flutter.dev/get-started/install

## Run on Android
1. Extract this project.
2. Open a terminal in the `melon` folder.
3. Run:
   ```bash
   flutter doctor
   flutter pub get
   flutter run
   ```
4. Connect your Android phone with USB debugging enabled, or start an emulator.

## Build an Android APK
```bash
flutter pub get
flutter build apk --release
```
APK output:
`build/app/outputs/flutter-apk/app-release.apk`

To build a Play Store app bundle:
```bash
flutter build appbundle --release
```
Output:
`build/app/outputs/bundle/release/app-release.aab`

## Run/build for iPhone
You need a Mac with Xcode. On the Mac:
```bash
flutter doctor
flutter pub get
cd ios
pod install
cd ..
flutter run
```
For a release build:
```bash
flutter build ipa --release
```
Apple Developer signing and App Store Connect setup are required for distribution. You cannot build a signed iOS app on a standard Windows or Android phone alone.

## Photo/video picker platform setup
`image_picker` is used for local device media selection. Flutter's Android plugin setup normally configures Android automatically. For iOS, review the generated `ios/Runner/Info.plist` and add the relevant permission descriptions if needed:
- `NSPhotoLibraryUsageDescription`
- `NSCameraUsageDescription`
- `NSMicrophoneUsageDescription` (if recording video with audio)

Example descriptions:
- `Melon lets you choose media to add to your local feed.`
- `Melon uses the camera when you choose to take a photo.`

## Suggested next production steps
1. Pick a backend: Firebase or Supabase.
2. Add secure sign-up/login, account recovery and profile storage.
3. Upload media to private-by-default cloud storage with size/type limits.
4. Implement real-time chat, reporting/blocking, moderation and privacy controls.
5. Add push notifications and test on physical Android/iOS devices.
6. Add app icon, screenshots, privacy policy and store metadata.
7. Run accessibility, security and performance checks before release.
