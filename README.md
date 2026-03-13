# Speech to Text App (my_app)

Flutter-based speech-to-text demo app with basic recording, recognition, and transcript display. Built for Android/iOS, and optionally desktop/web if plugin support is available.

## Features

- Real-time speech recognition (microphone input -> text)
- Start/stop listening controls
- Display recognized text in app UI
- Copy transcript to clipboard
- Error reporting and permission handling
- Save transcript locally (optional) / clear session

## Dependencies

- `speech_to_text` (or similar plugin in `pubspec.yaml`)
- `flutter_localizations` (if using localized UI)
- `provider` / `riverpod` (optional state management)

## Getting Started

1. Install Flutter SDK: `https://flutter.dev/docs/get-started/install`
2. Clone repository:
   - `git clone <repo-url>`
   - `cd my_app`
3. Get dependencies:
   - `flutter pub get`
4. Run on a device/emulator:
   - `flutter run`
5. Build release:
   - Android: `flutter build apk --release`
   - iOS: `flutter build ios --release`

## Platform requirements

### Android

- `android/app/src/main/AndroidManifest.xml` includes:
  - `RECORD_AUDIO` permission
- Ensure `minSdkVersion` in `android/app/build.gradle` matches plugin requirements

### iOS

- `ios/Runner/Info.plist` includes:
  - `NSMicrophoneUsageDescription`
  - `NSSpeechRecognitionUsageDescription`

### Desktop / Web

- Check plugin support before enabling; speech recognition offering may vary

## Usage

1. Open the app
2. Grant microphone permission
3. Tap `Start` to begin listening
4. Tap `Stop` to end recognition
5. Optional: copy or clear text

## Project Layout

- `lib/main.dart` - app entry and main widget
- `lib/screens/` - screen widgets (if app structured in folders)
- `lib/state/` - state management providers/controllers
- `lib/services/` - speech-to-text service abstractions
- `test/` - widget/unit tests

## Tests

- Run `flutter test`
- Add coverage for:
  - permission flows
  - start/stop actions
  - recognized text state updates

## Troubleshooting

- `flutter doctor` should be clean
- Re-run `flutter pub get` after dependency updates
- For Android microphone permission runtime issues, ensure permission is granted in OS settings
- For iOS speech recognition, enable proper entitlements (if needed)

## Contributing

1. Fork repo
2. Create branch `feature/<name>`
3. Code + tests
4. Run `flutter test && flutter analyze`
5. Open PR with description

## Notes

- Keep app key/secret management out of source
- Follow platform-specific store/privacy guide for microphone/speech usage
- Document any plugin changes in `pubspec.lock`
