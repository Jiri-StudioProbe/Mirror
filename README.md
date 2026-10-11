# Misty Mirror

POC: a fogged live camera mirror. Wipe it with a finger to reveal a crisp view; each area stays clear for 10s, then fades back to fog over 5s.

Open `index.html` over HTTPS or `localhost` (camera access requires a secure context), e.g. `python3 -m http.server` and visit `http://localhost:8000`. Tunables (`HOLD_MS`, `FADE_MS`, `BRUSH_RADIUS`, `FOG_BLUR`) are at the top of the script.

Brush width follows finger contact size where the device reports it (clamped by `BRUSH_MIN`/`BRUSH_MAX`, scaled by `REF_CONTACT`). Add `?debug` to the URL to see the reported contact size.

## Sound

The wipe sound (default volume 50; "Sound volume" slider in `?tune`, 0 = off) plays short finger-on-glass squeaks (`audio/squeaks.mp3`) while the finger is moving over the glass. They were cut from "squeak-finger-on-glass" by freesound_community (file 73186, downloaded from a free sound library); check that library's licence before any wider use.
