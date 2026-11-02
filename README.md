# Steady

A gentle daily tracker for physio, Pilates and light cardio. Built from FitTrack (same plain HTML/JS installable app),
reworked for physio recovery: the physio exercises themselves stay in Embodia, and Steady records that they
got done, keeps a streak and tracks how things feel over time.

What's in it:

- **Daily physio** card with an *Open Embodia* link and a *Mark as done* log. Streak counts consecutive days.
- **Pilates** 2–3 times a week (Mon/Wed/Fri suggested): logs a class, reformer or mat session.
- **Light cardio** on the other days: a guided easy walk (5 min warm-up, 20 min conversational pace, 5 min cool-down)
  with a timer, or log a bike, swim, water walk or elliptical session. Low impact only, no running or jumping.
- **Check-in** (comfort, 1–5) offered after sessions and on the Today screen, charted on Progress so it can
  be shown to the PT.
- Weekly goals for physio days, Pilates and cardio (Settings), progress charts, optional body weight, history.

No build step and no backend: data lives in the phone's browser storage. Use **Settings → Export backup** to save a copy.
Steady is a tracker, not medical advice; the app says to follow the PT's plan.

## Run it locally

```bash
python3 -m http.server 8767
```

Then open <http://localhost:8767>.

## Put it on her phone

Host the folder on GitHub Pages (same steps as `Sample Keys/SETUP.md` section 3), open the address on her phone, then:

- **iPhone (Safari):** Share → Add to Home Screen
- **Android (Chrome):** ⋮ → Install app

## Things to know

- The Embodia link in `index.html` (`EMBODIA` constant) points at `https://app.embodia.com`. Change it if her
  login lives elsewhere.
- Storage key is `steady-v1` and the cache is `steady-v1`, so it never collides with FitTrack or Sample Keys on the
  same `github.io` address.
- The weekly plan is the `SCHEDULE` array; session text lives in `SESSIONS`.

## Files

| File | What it is |
| --- | --- |
| `index.html` | The whole app: Today, history, progress, settings, walk timer, check-ins |
| `sw.js` | Offline support |
| `manifest.webmanifest`, `icons/` | Lets phones install it as an app |
