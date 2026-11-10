# Loop Director

Web app for iPad (landscape) to run songs live at church: each song is a list of sections (Intro, Verse, Pre-Chorus, Chorus, Bridge…) with bars, meter and tempo. The live screen has a pad per section, a timeline with the current section and bar, a continuous click, **Loop**, jumps that always land on the next downbeat (or at the end of the section), voice cues one bar before each change, and setlists.

- Published at https://dxvxd27.github.io/loop-director/
- One `index.html`, no build step. `sounds.js` holds the click sounds (CLICK_RIM / CLICK_RIMUP from Pulso Libre).
- Data is saved on the device and synced with Supabase (project "EasyPlan", table `loopdirector_docs`, RLS per user) when signed in with the EasyPlan account.
- Voice cues are **not** in the repo: import them in Ajustes → «Importar avisos…» (they are recognized by file name: `INTRO`, `VERSE`, `VERSE 2`, `PRE CHORUS`, `CHORUS 2`, `END`, `ONE`…`FOUR`…). They are stored in your account.
- When you change any file, bump `VERSION` in `sw.js` and `APP_VERSION` in `index.html` so installed copies update.

Local test: `python -m http.server 5181` in this folder and open http://127.0.0.1:5181/.
