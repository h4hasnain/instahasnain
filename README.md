# Insta Hasnain — Firebase starter

## Features
- Firebase Email/Password sign-up and sign-in
- Firestore user profiles and username reservation
- Upload images (15 MB max) and videos (100 MB max) to Firebase Storage
- Live feed using Firestore snapshots
- Likes and comments
- Profile page, search, sign-out

## Setup
1. Create a Firebase project at https://console.firebase.google.com/
2. In Project settings > General > Your apps, register a Web app and copy its Firebase config.
3. Open `index.html` and replace the `firebaseConfig` placeholder values with your project's config.
4. Firebase Console > Authentication > Sign-in method: enable **Email/Password**.
5. Create a **Cloud Firestore** database.
6. In Firestore > Rules, paste `firestore.rules` and publish.
7. Enable **Storage** in Firebase Console. In Storage > Rules, paste `storage.rules` and publish.
   - Firebase Storage may require a billing-enabled project depending on current Firebase plan/policies.
8. Run the page from a local web server or host it on Firebase Hosting. Avoid opening it as `file://` if the browser blocks modules.
   - Easy local option: use VS Code Live Server.
   - Firebase Hosting: install Firebase CLI, run `firebase init hosting`, use this folder as the public directory, then `firebase deploy`.

## Important notes
- Firebase config is public client configuration, not a server secret. Security Rules protect data.
- Do not publish with open rules such as `allow read, write: if true`.
- This starter is a functional baseline, not a production-hardened Instagram clone. Add rate limits, moderation/reporting, pagination, thumbnail/transcoding, account recovery, and abuse prevention before public launch.
- The feed is for signed-in users of the same Firebase project. It is not connected to Instagram.
- Followers/following counters are profile display placeholders; follow graph is not implemented yet.
- This version lets users upload image/video posts and view likes/comments. Profile picture upload and video transcoding are not included.
