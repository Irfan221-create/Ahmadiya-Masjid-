AHMADIYA MASJID — OWNER EDITING SETUP

This adds a private owner login at /admin.html. After one-time Firebase setup, the owner can edit site text, address, contact, prayer timings, and gallery image URLs without editing HTML or visiting GitHub for every change. Image upload is not included; gallery fields accept direct HTTPS image URLs.

ONE-TIME SETUP (Android phone)
1. Open https://console.firebase.google.com/ and create a project.
2. Project settings → add a Web app (</>) and copy its config.
3. In BOTH index.html and admin.html, replace config placeholders: apiKey, authDomain, projectId, appId.
4. Firebase Console → Authentication → Get started → enable Email/Password. Add the owner user under Users. Keep the password private.
5. Firestore Database → Create database.
6. Firestore → Rules: paste firestore.rules, replace REPLACE_WITH_OWNER_EMAIL with the exact owner email, then Publish.
7. Upload all files and the assets folder from this package to the ROOT of your GitHub repository and commit. Do not upload only the ZIP.
8. GitHub repo → Settings → Pages → Deploy from a branch → main → /(root) → Save.
9. Open the GitHub Pages URL. Owner panel: same URL plus /admin.html. Sign in and edit; click Save changes. Public site reads the saved content.

SECURITY
- Never put a GitHub password or GitHub Personal Access Token into website code.
- Firebase web config is not a password; Firestore rules and Authentication enforce access.
- Only the exact owner email should have write access. Test that unauthenticated users cannot save.
- Do not publish unverified phone numbers, prayer times, UPI IDs, bank details or donation QR codes.
- Firebase quotas/pricing may change; check the current plan.
