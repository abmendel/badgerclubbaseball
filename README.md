# Badger Club Baseball HQ

The UW–Madison club baseball dashboard (NCBA D1 & D2): schedule, matchups, team and player stats, national ranks, roster, and the club board's calendar, deadlines, tasks, dues, attendance, carpools and form responses.

Runs for free:

- **Site:** GitHub Pages (this repo, `main` branch, root folder).
- **Shared club data:** Firebase Firestore on the free Spark plan (no card).
- **Board sign-in:** Google accounts through Firebase Authentication. Only accounts on the board editors list can see board-only data or make changes; everyone else with the password gets the member view.
- **Form responses:** read straight from the board's Google Sheets with the signed-in board member's own Google access (read-only).

## Files

| Path | What it is |
|---|---|
| `index.html` | The whole dashboard. `FIREBASE_CONFIG` near the top points it at the club's Firebase project. |
| `data/d1.json`, `data/d2.json` | NCBA rosters, schedules, results, standings and stats. Refreshed by asking Claude to "refresh the club dashboard stats". |
| `vendor/firebase.js` | Firebase web SDK, bundled locally. |
| `firestore.rules` | Security rules to paste into the Firebase console (Firestore → Rules). Replace `OWNER_EMAIL` with the owner's Google account. |
| `assets/logo.png` | Logo. |

## Board editors

The site owner signs in, opens **Data refresh → Board editors**, and lists the Google accounts that can edit. Only the owner (set in `firestore.rules`) can save that list.
