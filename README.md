# Random Dance Play

A little web app for random play dance (RPD): it shuffles clips of K-pop dance
sections, hides the song name for a few seconds so you can guess, then reveals it
and moves to the next one. Fun for solo or group play, and it casts to a TV by
casting the browser tab.

No accounts, no backend, no build step, nothing downloaded. Playback runs through
the official YouTube IFrame Player API and your library lives in the browser. This
is a weekend-project kind of thing, built because it sounded fun, not a startup.

**Live demo:** _(coming once it's deployed)_

## What It Does

- Browse a built-in catalog of K-pop songs (TWICE, ILLIT, LE SSERAFIM, NewJeans,
  aespa, IVE, and more) and one-tap add. Each song comes with a clip already set,
  so you can play right away with nothing to type.
- Or paste any YouTube link for songs that aren't in the catalog.
- Load a whole playlist in one tap (Bias picks, Add everything, Surprise six).
- Play a session: each clip plays with the name hidden, reveals after a guess
  window, counts down, then auto-advances to the next random clip.
- Everything saves in your browser. Export and import JSON to back up or move it
  between devices.

## Run It Locally

Serve over http(s) so the player behaves. From this folder:

```
python3 -m http.server 8000
```

Then open `http://localhost:8000`. It works on any static host too. Opening the
file directly with `file://` can make the player flaky, so prefer a local server.

## How To Play

1. Add songs from the catalog, or paste links in the second panel.
2. Optional: tap Set Clip to scrub to the exact dance section you want.
3. Tap Play Session, then Start once to unlock audio.

During a session: Replay, Pause (freezes every timer), Skip, End. Keyboard: space
pauses, right arrow or N skips, R replays, Esc ends.

## Settings

- **Guess window** (default 5s): how long the name stays hidden.
- **Next-in countdown** (default 3s): the reset pause between clips.
- **Reveal mode**: after the guess window, immediate, or hidden.
- **Include un-clipped songs** and a **fallback clip length** for songs without a set clip.

## Notes

- Removed, private, or region-blocked videos are skipped mid-session and flagged
  in the library, so one dead link doesn't break the game.
- Reloading mid-session drops the session state; your library and clips persist.
- The home page can show cute photocards if you drop portrait images into the
  `photos/` folder (`nayeon.jpg`, `momo.jpg`, `sana.jpg`, `chaewon.jpg`,
  `wonhee.jpg`, `iroha.jpg`). Those stay on your machine and are never committed.

Made by Crystal Cheng, just because it sounded fun to build.
