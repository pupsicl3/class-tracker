# Class Tracker

A phone-friendly app for tracking students' attendance, payments and class balances.

- Hosting: GitHub Pages (free)
- Database + login: Firebase (free "Spark" plan, no card needed)
- Works offline: changes made without internet sync when the phone reconnects.

## Files

| File | What it is |
|---|---|
| `index.html` | The whole app |
| `firebase-config.js` | Your Firebase settings (paste them here) |
| `firestore.rules` | Security rules to paste into Firebase (who can see the data) |
| `manifest.webmanifest`, `icon-*.png`, `apple-touch-icon.png` | Home-screen icon and app name |

## Setup (one time)

1. **Create a Firebase project** at https://console.firebase.google.com (Add project, Google Analytics off).
2. **Add a web app** (the `</>` icon on the project home page), name it "Class Tracker", skip Firebase Hosting.
   Copy the values from the `firebaseConfig` it shows into `firebase-config.js`.
3. **Turn on login:** Build → Authentication → Get started → Sign-in method → Email/Password → Enable.
   Then Users → Add user: add your friend's email + a password (and yourself if you want access).
4. **Create the database:** Build → Firestore Database → Create database → pick a location near you → Start in production mode.
5. **Lock it down:** Firestore → Rules → paste `firestore.rules`, replace the two emails (lowercase) → Publish.
6. **Put it online:** create a public GitHub repository, upload all these files, then
   Settings → Pages → Deploy from a branch → `main` / root → Save. The site appears at
   `https://<your-username>.github.io/<repo-name>/` after a minute or two.
7. **Allow the site in Firebase:** Authentication → Settings → Authorized domains → Add domain → `<your-username>.github.io`.
8. **On the phone:** open the link, sign in, then Add to Home Screen.

## Changing who has access

Add or remove the user in Firebase → Authentication → Users, and update the email list in Firestore → Rules → Publish.

## Updating the app later

Replace `index.html` in the GitHub repository (Add file → Upload files). The site updates within a couple of minutes.

## Backups

In the app: ⚙ Settings → Download backup. Keep the file somewhere safe. Restore backup puts it back.

## Is it safe that the code and config are public?

Yes. The Firebase settings only identify the project; they don't unlock anything.
Nobody can read or change data without signing in with an account you created
and being on the email list in the rules.
