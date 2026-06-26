# Pokemon GO Trade Cooldown Tracker

Frontend: HTML + CSS + JavaScript  
Database: Firebase Firestore  
Hosting: GitHub Pages

## 1. Create Firebase project

1. Go to https://console.firebase.google.com
2. Create a project
3. Go to Build > Firestore Database
4. Create database
5. Choose a region
6. Start in test mode first

## 2. Create Firebase web app

1. Go to Project settings
2. In Your apps, click Web app
3. Register app
4. Copy the Firebase config
5. Open `index.html`
6. Replace the `firebaseConfig` object with your real config

Example location inside `index.html`:

```js
const firebaseConfig = {
  apiKey: "PASTE_YOUR_API_KEY",
  authDomain: "PASTE_YOUR_PROJECT_ID.firebaseapp.com",
  projectId: "PASTE_YOUR_PROJECT_ID",
  storageBucket: "PASTE_YOUR_PROJECT_ID.appspot.com",
  messagingSenderId: "PASTE_YOUR_SENDER_ID",
  appId: "PASTE_YOUR_APP_ID"
};
```

## 3. Add Firestore rules

For quick personal use, copy the contents of `firestore.rules` into:

Firestore Database > Rules

Then publish the rules.

Important: these rules allow anyone who has your website link to read/write/delete cooldown data. For a private version, add Firebase Authentication later.

## 4. Upload to GitHub Pages

1. Create a new GitHub repository
2. Upload these files to the root of the repo:
   - `index.html`
   - `README.md`
   - `firestore.rules`
3. Go to repository Settings > Pages
4. Source: Deploy from a branch
5. Branch: `main`
6. Folder: `/root`
7. Save

GitHub will give you a URL like:

```text
https://your-username.github.io/your-repo-name/
```

## Notes

- The countdown uses saved `endAt` timestamps, so it still works while your laptop is off.
- Firestore sync means you can open the same website from another device and see the same cooldown data.
- This app tracks cooldowns only; it does not automate gameplay.
