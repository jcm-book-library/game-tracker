# Game tracker: notes for Claude sessions

**Read the house rules first:** [HOUSE-RULES.md](https://github.com/jcm-book-library/control-room/blob/main/HOUSE-RULES.md) in `control-room` (plain text: https://raw.githubusercontent.com/jcm-book-library/control-room/main/HOUSE-RULES.md). They cover Google Sheet safety, branches and pull requests into `main`, using cheaper models to save usage credits, and the build template. The notes below are this repo's own; where they are more specific, they win. The project charter is `project.json`.

Sister app to the book tracker "Jackets & Manuscripts" (reference: `jcm-book-library/my-book-library`,
branch `claude/keen-sagan-yf9rqf`, `v3/reading-log.html`). Copy its patterns, styles and helper code.

## Way of working
- Model use: see "Using models" in the house rules.
- Build in stages; test headless with Playwright (Chromium at `/opt/pw-browsers/chromium`, stubbed
  `window.claude`) at laptop and phone width before every publish; commit and push each stage.
- Owner likes options with a recommendation, bullet points first, and pushback.

## Sheet safety (non-negotiable)
- Sheet "Entertainment Tracker" `1558jWeUc8gCzQuph6wOVyOocvTBhQf22UuCSXza8klc`.
- Only touch the `🎮` tab and tabs this app created (names start with 🎮). Never the book tabs.
- Find a row by `id` right before every write; write only changed cells. Never rewrite whole tabs.
- Dates yyyy-mm-dd, numbers as numbers, text prefixed with `'`. No formula columns in 🎮.
- Keep dropdowns and chip formatting (`customUiMode: CHIP` when setting validation).
- After any bulk change, read back and compare with a script.
- The app shows dates as `19 Nov 26` (owner preference); the sheet stores real dates.
