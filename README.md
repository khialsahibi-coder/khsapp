# SAHIBI VISION AI STUDIO — Complete Source Pack v2

This is a Flutter Android source project. It is not a prebuilt APK; the APK must be compiled on your Windows/Flutter setup.

## Included in this pack

### AI video creation (online)
- AI Create screen with prompt entry.
- Copies the prompt and opens fal.ai's FLUX 3 free video Sandbox.
- fal advertises five free 720p FLUX 3 Draft text-to-video generations per rolling 24 hours in the web Sandbox.
- The free Sandbox allowance requires a fal account and a card on file to activate.
- Free Sandbox allowance is NOT a free unlimited API. Full-quality 1080p enhancement and API generations are paid.
- Workflow: generate/download in fal browser, then import the downloaded MP4 into this app.
- This pack does not secretly submit paid API jobs or store your fal secret.

### Local editor
- Import multiple video files.
- Preview selected clip.
- Trim start/end of a single clip.
- Concatenate multiple untrimmed clips.
- Add a background audio file and set its volume.
- Import SRT and burn subtitles into output.
- Render MP4 at 720p or 1080p using FFmpegKit.
- Share the rendered MP4.

### Studio features
- English, Dari and Pashto script templates.
- Phone text-to-speech preview (depends on installed Android voice packs).
- Microphone recording and playback.
- SRT draft from script (estimated timing, NOT speech recognition).
- About Us developer/contact details and navy/gold/teal brand palette.

## Important known limitations in v2
- The free fal Sandbox is opened in a browser; the app does not directly call a free fal API because fal's advertised free allowance is for its web Sandbox. User must download the clip and import it.
- Online AI video generation needs internet and a fal account. Five free daily drafts are subject to provider policy and availability; no unlimited free video generation is promised.
- AI-generated speech recognition / automatic word-level subtitle synchronization is not implemented. SRT can be imported and burned into video; script-to-SRT draft timing is approximate.
- Current editor supports trim of one clip OR concatenation of multiple untrimmed clips. It supports one optional music track and SRT burn-in. It is not yet a full multi-track NLE: transitions, animated titles, overlays and frame-accurate multi-clip trimming are not included.
- Your own voice can be recorded and replayed, then selected with 'Use my voice in video export' to mix it into the exported video.
- 1080p export depends on the input, phone codec support, available storage and device memory. Large projects may fail or take time.
- FFmpegKit full package includes GPL codecs. Review its license if you distribute this app to others. For personal testing, build locally.

## Build on Windows 10
1. Extract this ZIP.
2. Open the extracted `SAHIBI_VISION_AI_STUDIO_COMPLETE` folder in VS Code.
3. In Terminal run:
   ```powershell
   flutter doctor
   flutter pub get
   ```
4. If there is no `android` folder yet:
   ```powershell
   flutter create . --platforms=android
   ```
   Keep the provided `lib/main.dart` and `pubspec.yaml`.
5. Connect your Xiaomi 11T Pro with USB debugging enabled and run:
   ```powershell
   flutter run
   ```
6. Build an APK:
   ```powershell
   flutter build apk --release
   ```
   Output: `build\app\outputs\flutter-apk\app-release.apk`

## Android setup
- Set Android `minSdk` to 24 or higher for `ffmpeg_kit_flutter_new`.
- Microphone permission must be present in `android/app/src/main/AndroidManifest.xml` inside `<manifest>`:
  ```xml
  <uses-permission android:name="android.permission.RECORD_AUDIO" />
  ```
- If required by your Android version / file picker, keep the Android system document picker permissions/configuration from plugin defaults.
- App uses app-private documents folder for recordings and exports. Share exported files from the app's Share button.

## First test
1. `flutter pub get`
2. `flutter run`
3. Open Voice and record a 5-second sample.
4. Open AI Create, write a prompt, open fal and generate a short sample.
5. Download the MP4, return to app, import it in Editor.
6. Trim a short 5-second segment and export at 720p first.
7. After 720p works, test 1080p.

## Provider references
- Free FLUX 3 Draft Sandbox: https://fal.ai/flux-video-free
- fal API pricing is separate from the Sandbox daily free allowance: https://fal.ai/docs/documentation/model-apis/pricing
