# Compare Characters Lab

A hosted Grade 5 reading lesson — **"We are inquiring into how to compare and contrast two or more characters in a story or drama, drawing on specific details in the text."**

Built in the GEMS "Learn Like a GEM" house style. Students join a class with a 5‑letter code, take a short **pre‑learning check** that recommends a path (support / core / push), then work through **I Do → We Do → You Do** with three levelled checkpoints (DOK 1→3). The teacher watches everyone's progress on a **live dashboard**.

- **Hosting:** GitHub Pages (static site)
- **Database:** Cloud Firestore
- **Sign‑in:** Firebase Anonymous Auth (students just type a name)

## Files
- `index.html` — page shell + Firebase SDK
- `app.js` — the whole app (lesson, pre‑test, dashboard, Firestore)
- `firestore.rules` — security rules to paste into the Firebase console

## Setup (one time)

### 1. Firebase
1. Go to <https://console.firebase.google.com> → **Add project**.
2. In the project: **Build → Firestore Database → Create database** (Production mode, nearest region).
3. **Build → Authentication → Get started → Sign‑in method → Anonymous → Enable.**
4. **Project settings (gear) → Your apps → Web app (`</>`)** → register an app → copy the `firebaseConfig` object.
5. Paste those values into the `firebaseConfig` block at the top of `app.js`.
6. **Firestore → Rules** → paste the contents of `firestore.rules` → **Publish**.

### 2. GitHub Pages
1. Create a new repository and upload `index.html`, `app.js` (and optionally this README + rules).
2. **Settings → Pages → Build from branch → `main` / root → Save.**
3. Your lesson is live at `https://<user>.github.io/<repo>/`.

## Using it
- **Teacher:** open the link → *Open a class* → share the 5‑letter code → watch the dashboard.
- **Students:** open the link → *Join a class* → enter the code + name.

## Notes
- Anonymous auth means anyone with the link can join — fine for a classroom, not for public release. Add Google sign‑in + stricter rules if you need real identities.
- The pre‑test recommendation is advisory; the teacher can tell a student to switch path verbally.
