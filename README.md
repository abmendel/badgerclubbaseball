# Badger Club Baseball HQ

The UW–Madison club baseball dashboard (NCBA D1 & D2): schedule, matchups, team and player stats, national ranks, roster, and the club board's calendar, deadlines, tasks, dues, attendance, carpools and form responses.

Runs for free:

- **Site:** GitHub Pages (this repo, `main` branch, root folder).
- **Shared club data:** Firebase Firestore on the free Spark plan (no card).
- **Two passwords, no owner:** the board password and the member password are two shared Firebase logins (`board@badgerclub.example`, `member@badgerclub.example`), checked by Firebase. The board password can see and change everything; the member password sees the team tabs. Anyone with the board password can change either password in **Data refresh → Change passwords**.
- **Form responses:** "Sync now" asks whichever board member is syncing to allow read-only Google Sheets access with their own Google account. It doesn't change who is signed in to the dashboard.

## Files

| Path | What it is |
|---|---|
| `index.html` | The whole dashboard. `FIREBASE_CONFIG` near the top points it at the club's Firebase project. |
| `data/d1.json`, `data/d2.json` | NCBA rosters, schedules, results, standings and stats. Refreshed by asking Claude to "refresh the club dashboard stats". |
| `vendor/firebase.js` | Firebase web SDK, bundled locally. |
| `firestore.rules` | Security rules to paste into the Firebase console (Firestore → Rules). |
| `assets/logo.png` | Logo. |

## Handing off to next year's board

Nothing to transfer: give the new board the board password and have them change it. To let them manage the Firebase project or this repo too, add them in Firebase (Project settings → Users and permissions) and GitHub (Settings → Collaborators).
