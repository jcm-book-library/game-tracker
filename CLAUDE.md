# Game tracker: notes for Claude sessions

Sister app to the book tracker "Jackets & Manuscripts" (reference: `jcm-book-library/my-book-library`,
branch `claude/keen-sagan-yf9rqf`, `v3/reading-log.html`). Copy its patterns, styles and helper code.

## Way of working
- **Orchestrate with other models to make best use of usage credits.** Keep app design and core code
  in the main session; hand mechanical work to cheaper subagents (Haiku for lookups and data
  gathering, Sonnet for Playwright test runs, read-back comparisons, and routine edits).
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
