# Attendance Sheet Builder

Turns the biometric timesheet (.xlsx) into the monthly attendance register (.xlsx).
Runs entirely in the browser — no server, no data leaves your computer.

## Host it on GitHub Pages (free)
1. Create a new repository on github.com (e.g. `attendance-builder`). Public repos get Pages free.
2. Upload `index.html` (and this README) to the repository root → Commit.
3. Settings → Pages → Source: "Deploy from a branch" → Branch: `main`, folder `/ (root)` → Save.
4. After ~1 minute the app is live at `https://<your-username>.github.io/attendance-builder/`.

## How it converts the Final Status row
| Timesheet | Attendance |
|---|---|
| P, POW | P |
| WO | WO |
| H | PH if the date is in the holiday list, otherwise L (leave) |
| A, L, LV | L (leave); A becomes PH if the date is a holiday (optional) |
| - | blank (no record / not joined) |

Output columns: BioMatric Code, NAME, one column per day. Totals (P, PH, WO, Lv) are Excel COUNTIF formulas.

## Things to know
- The timesheet has day numbers only (e.g. `23 (Sun)`); the app works out the month from the weekdays. Check the date in Step 2.
- Holiday list is preloaded with Central Govt gazetted holidays (Delhi) for 2026–2027. Edit it in the app; edits are saved in your browser.
- Libraries loaded from cdnjs: SheetJS 0.18.5 (read), ExcelJS 4.4.0 (write). Needs internet.
