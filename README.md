# Bubble Check — Answer Sheet Scanner

A phone-camera answer-sheet scanner and auto-grader for the 30-item, 4-choice
(A/B/C/D) bubble sheet used at Mabuhay Elementary School. Runs entirely in the
browser — no server, no data ever leaves the phone.

## How it works

1. **Capture** — take a photo of one half of the cut answer sheet.
2. **Align** — drag 4 dots onto the corners of the bubble grid (not the header).
   The app un-warps the photo into a straight rectangle, so a tilted or
   angled phone photo still lines up correctly.
3. **Grade** — the app finds the darkest (shaded) bubble in each row automatically.
   You can tap any bubble to correct a misread before scoring — this is what
   makes it reliable in practice, since no camera-based detection is perfect
   on every lighting condition.

Answer keys and saved results are stored locally on the device (localStorage)
and can be exported as CSV.

## Publish it on GitHub Pages (free hosting)

1. Create a new GitHub repository (e.g. `bubble-check`).
2. Upload `index.html` from this folder to the root of that repository.
3. On GitHub: **Settings → Pages → Source → Deploy from a branch**, choose
   the `main` branch and `/ (root)` folder, then **Save**.
4. After a minute, your app will be live at:
   `https://<your-username>.github.io/bubble-check/`
5. Open that link on your phone (Chrome or Safari) — camera capture works
   automatically since GitHub Pages serves over HTTPS.

No build step, no dependencies, no npm install — it's a single static HTML file.

## Notes on accuracy

- Works best with even, direct light and the sheet held flat.
- The 4-corner alignment step is the most important part for accuracy —
  take your time lining the dots up exactly on the outer edge of the bubble
  block (outside of column A, outside of column D, top of row 1, bottom of row 30).
- If a student darkened two bubbles in one row, or pressed too lightly, the
  app may misread it — always glance over the yellow/green/red rings before
  saving a score, and tap to fix anything that looks wrong.
- This tool is for one sheet layout: 30 items, 4 choices (A–D), one column,
  matching `Horizontal_2Set_30_Items_Short.pdf`. A different layout would
  need the row/column math in `index.html` adjusted.
