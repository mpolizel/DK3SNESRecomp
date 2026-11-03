# Changelog

## 0.1.4 — 2026-11-03

### Fixed
- Preventive fix for a black screen after saving. Donkey Kong Country could
  stay on a black screen (sound still playing) after saving at Candy's. This
  game runs on the same engine and gets the same fix, so saving at
  Wrinkly's Save Cave cannot freeze for that reason.

## 0.1.3 — 2026-11-02

### New
- **Settings during play:** Ctrl+L (or Select+L3 on a controller) reopens the
  launcher. Shader, window scale, volume and controls apply when you press
  Resume, without restarting the game.
- **Audio interpolation:** press **I** to cycle Gaussian (the console's own,
  default), Cubic (crisper highs) and Sinc. It changes only what you hear;
  the game, its echo and save states are unaffected. The choice is kept.
- New upscaler shaders: **ScaleFX**, **NNEDI3 (neural)** and **NNEDI3
  (neural, high)**.
- A fresh install starts with the **CRT Lottes** shader. An install that
  already has a shader chosen keeps it.
- **Updates never cost you a save.** From the next update on, the updater
  copies your in-game saves and save states to `save-backups\<date>_before_<version>\` before
  installing, leaves save files out of the copy and puts the backup back if
  they changed anyway. Save states from earlier versions keep working, and
  every release is now checked for that before it is published.

### Fixed
- HDMA raster effects (per-line color, layer and scroll changes) started one
  line late; they now start on the line the game asks for.
- Choosing **None** as the shader during play no longer leaves a black
  screen.
- Multi-pass shaders that read the original game frame from a later pass
  (ScaleFX) no longer draw black.

## 0.1.2 — 2026-11-01

### New
- **Check for updates on start** (on the launcher's main screen, next to
  *Skip launcher on boot*; on by default). When a newer release is out the
  game offers to install it: it downloads the new setup pack, copies it over
  the install without deleting anything, keeps your ROM selection and reopens
  the setup window; press **Generate & rebuild**. In-game saves, save states
  and settings are kept; save states from an older version may not load in a
  newer one.
- A fresh install starts with the **CRT Geom (curved)** shader. Any renderer
  or shader you pick in the launcher is saved and kept.

### Fixed
- Renderer: sprites now use the sprite table that was current on each line,
  HDMA effects enabled during vblank start on the first line, and writes made
  at the start of vblank are no longer applied one frame late (screens could
  show the previous screen's layout for a frame on a mode change).

Updating from 0.1.1 or older: unpack this release's zip over your install
folder once (those versions have no updater), start
`DonkeyKongCountry3SNESRecomp.exe` and press **Generate & rebuild**. Later
versions update themselves.

## 0.1.1 — 2026-10-30

### Fixed
- NMI handlers that abandon their frame may now outlast it, so long uploads
  done with NMI off are no longer cut short.

## 0.1.0 — 2026-10-30

First release: a setup pack that recompiles the game from your own ROM. Boots
through the Nintendo logo and copyright into the opening world-map scene.
Scanline, CRT and upscaler shader presets; console-free Windows build.
