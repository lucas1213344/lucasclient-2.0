# Lucas Client (Fabric, Minecraft 1.21.11)

An original client mod: HUD elements, Spotify HUD, and floating lyrics
with an adjustable distance from your point of view.

## Build
Requires JDK 21 and an internet connection (Gradle downloads Minecraft, Fabric and mappings).

    ./gradlew build          # Windows: gradlew.bat build
                             # jar ends up in build/libs/lucas-client-1.1.0.jar (not the -sources one)

No local setup? Push this folder to a GitHub repo: the included workflow (.github/workflows/build.yml)
builds the jar and attaches it to the run under Actions -> Artifacts.

Drop the jar into your Modrinth profile's `mods` folder. The profile must be Fabric, Minecraft 1.21.11, with
Fabric API installed. If Gradle can't resolve a version, edit `gradle.properties` (https://fabricmc.net/develop/).

## Spotify setup (one time)
1. Go to https://developer.spotify.com/dashboard and create an app.
2. Add this Redirect URI exactly: `http://127.0.0.1:8888/callback`
3. Copy the app's Client ID, then in game run:
   - `/lucas spotify clientid <your_client_id>`
   - `/lucas spotify login`  (opens your browser; approve once)
Spotify Premium is not required for reading what's playing.

## Controls
- Right Shift: menu (toggle modules, sliders, "Edit HUD Layout")
- C (hold): zoom
- All keys can be rebound in Controls -> Lucas Client

## Features
HUD: FPS, Ping, CPS, Coordinates, Clock, Keystrokes (with CPS), Armor + durability %,
Spotify HUD (album art, title, artist, progress bar).
3D Lyrics (synced via LRCLIB): Distance, Scale, Opacity, Vertical Offset, Smooth Follow
+ Follow Speed, Keep Apparent Size, Previous/Next line.
Extras: smooth Zoom, Fullbright (client-side night vision), Theme accent colour, draggable HUD editor.

## Added modules
Free Look (hold Left Alt), Freecam (F6), Atmosphere, Hand Glow, CS Knife (viewmodel), Sus Chunks.
Logo: drop your logo at `src/main/resources/assets/lucasclient/textures/gui/logo.png` and it appears in the menu.
Build: `./gradlew build` -> `build/libs/lucas-client-1.1.0.jar`
