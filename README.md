# Game Tracker

Sister app to the book tracker *Jackets & Manuscripts*. One self-contained page, `app.html`, used two ways:

- published as a private claude.ai artifact that reaches Google Sheets through the artifact `mcp` capability;
- built into `index.html` (`python3 tools/build-pages.py`) for GitHub Pages at `jcm-book-library.github.io/game-tracker/`, signing in with Google (GIS token client + Sheets REST) and reusing the book app's saved Client ID (`localStorage["mbl_config"]`).

## Data (Google Sheet: Entertainment Tracker)

- `🎮`: one row per game. Columns A–K are the original ones (Title, Rating /10, Status, Platform, Purchase, Genre, Director, Starring, Released, Date Finished, Notes); the app shows Director as **Studio** and Starring as **Cast**.
- Added 2026-10-19 (L–T): `id`, `Hours`, `Time to Beat`, `Started`, `Tier`, `Up Next Order`, `Why`, `Triaged`, `Added`.
- Tabs added 2026-10-19: `🎮 Play Log` (`date | minutes | gameId | title | hoursAfter | loggedAt | source | note`) and `🎮 Settings` (`key | value`).
- Plan: status **Next Up** = Up next (the app keeps Status and Tier in step); Soon / Someday live in Tier for Playlist games.
- Finished = Played (end of story, not 100%). Completion rate = Played ÷ (Played + DNF).

## Sheet changes log

### 2026-10-18
- Backup of the whole tab: `🎮 backup 2026-10-18` (verified identical by script: 157 rows × 11 columns, 624 dropdown cells).
- Duplicates merged (kept the row with most data):
  - Gran Turismo 7: kept the Playing row, copied Released 2023 from the Played/"Ongoing" row, deleted that row.
  - Red Dead Redemption (PS3): kept the row with Released 2010, deleted the other.
  - Doom Eternal: kept the PS4 Played row (2020), set Status to Replay and Notes to "Replay on PS5 (to purchase)", deleted the PS5 Replay row.
- Typos fixed: "Gran Turimo 6" → "Gran Turismo 6", "Doom: The Dark Age" → "Doom: The Dark Ages".
- Read back and compared by script: 153 games, matches the expected result exactly, 612 dropdown cells intact.

### 2026-10-19
- Added columns L–T (`id`, `Hours`, `Time to Beat`, `Started`, `Tier`, `Up Next Order`, `Why`, `Triaged`, `Added`) with column K's formatting.
- `id` filled 1–153 in sheet order (numbers; new games get highest + 1). Never renumber.
- Tier dropdown (Up next / Soon / Someday, chips). The 4 Next Up games set to Up next, order 1–4, triaged 2026-10-19.
- Started / Triaged / Added, and the existing full dates in Released / Date Finished, shown as `d mmm yy`.
- New tabs `🎮 Play Log` (headers only) and `🎮 Settings` (dailyGoalMinutes 60, streakMinMinutes 15, yearGoalGames 12, streakStartDate blank).
- Read back and compared by script: A–K unchanged, 153 unique sequential ids, dropdowns intact.
