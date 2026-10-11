# Misty Mirror

POC: a fogged live camera mirror. The camera is requested on load, and "Hello you" is written on the mist as if by a finger. Wipe the mirror with a finger to reveal a crisp view; each area stays clear for 7s, then fades back to fog over 5s.

Open `index.html` over HTTPS or `localhost` (camera access requires a secure context), e.g. `python3 -m http.server` and visit `http://localhost:8000`. Tunables (`HOLD_MS`, `FADE_MS`, `FOG_BLUR` and the `DEFAULTS` block) are at the top of the script.

Brush width follows finger contact size where the device reports it (clamped by `BRUSH_MIN`/`BRUSH_MAX`, scaled by `REF_CONTACT`). Add `?tune` to the URL for a panel with sliders for the brush sizes, edge softness, bar fade, sound volume and greeting line width (default 4.5), plus a Replay button for the greeting. Add `?debug` to see only the reported contact size.

## Credits

- Sound: "Squeak finger on glass" by freesound_community, from [Pixabay](https://pixabay.com/sound-effects/search/finger-on-glass/) (file 73186). `audio/squeaks.mp3` is 47 short squeaks cut from that recording and levelled. Pixabay's content licence applies; check its current terms before any wider use.

## Sound

The wipe sound (default volume 50; "Sound volume" slider in `?tune`, 0 = off) plays one randomly chosen squeak at a time while the finger is moving over the glass, louder when faster, and fades out when it stops.
