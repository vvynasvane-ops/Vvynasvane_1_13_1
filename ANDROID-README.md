# Vvynas Vane for Android 1.13.0 — offline media player

**Install:** copy `VvynasVane-1.13.0.apk` to the phone → open it → allow "install from this source" when asked.
Works on Android 5.0 (API 21) and newer, including Android 14/15, phones, tablets and Chromebooks. ~4 MB. No internet needed — the app blocks all network requests.

## What it does
- Same app as the desktop version (library, playlists, Future Hub, EQ, lyrics, DJ mode, video player, Recap, "My Video" background).
- **Your whole phone, one tap**: on first start Android asks "Allow Vvynas Vane to access music and audio / photos and videos?". Say Allow and the app reads the phone's own media index — every song and video appears at once, with titles, artists, albums, durations and cover art already known. Nothing is scanned or decoded up front, so even tens of thousands of songs don't slow or heat the phone.
- **Or one folder**: "Change folder" offers *This phone* or *Choose a folder…* (internal storage or SD card); folder mode also finds lyrics (.lrc) and subtitles (.srt) next to your files, which Android doesn't expose through the media index.
- Files are streamed in place with range requests — never copied — so a 4 GB movie starts and seeks instantly. If you decline the permission you get the folder picker instead (or Settings).
- **Background playback**: a foreground service keeps music playing with the screen off, with lock-screen / notification controls (prev, play-pause, next, seek bar, artwork), headset and Bluetooth buttons, pause on unplug, and audio-focus handling (calls, other players).
- **Default player**: appears in "Open with" for every audio and video file, and can be set as the default; also registered as a Music app.
- **Open from other apps**: tap a song or video in Files / WhatsApp / Downloads → plays in Vvynas Vane.
- Fullscreen video with auto-landscape, screen kept awake while video plays, back button minimises (music keeps playing).
- Start screen says it is an Android offline media player; splash screen on launch.
- Survives: screen rotation, font/display-size changes, the web engine crashing (it is rebuilt), a missing/old WebView (clear message + Play Store button).

## Formats
Android's own hardware decoders: MP3, AAC/M4A, FLAC, OGG/Opus, WAV, AMR, MIDI; video H.264, HEVC (where the phone supports it), VP8/VP9, AV1 (newer phones), in MP4, MKV, WebM, 3GP, MOV. AVI/FLV/WMV/AC3/DTS need the desktop version (it bundles FFmpeg).

## Rebuilding
`./build.sh` (needs: JDK, aapt, dalvik-exchange, apksigner, android-23 android.jar). Web assets are in `www/`.
