# 📚 Fall-2024-B — Class Assignments & Quizzes Tracker

> A real-time shared web app for BS Computer Science Semester 4 students to track assignments and quizzes collaboratively — no login required.

---

## 🌐 Live App

👉 **[https://your-username.github.io/fall-2024-b](https://your-username.github.io/fall-2024-b)**

> Replace the link above with your actual GitHub Pages URL after deploying.

---

## 📌 What Is This?

**Fall-2024-B** is a lightweight, single-file web application built for a university class section. Any student can open the link and instantly:

- See all upcoming assignments and quizzes posted by classmates
- Add new items that appear live for everyone
- Track deadlines with automatic status indicators (Ongoing / Ending Soon / Ended)
- Filter and search by subject, type, or status

No account. No login. No installation. Just open the link and go.

---

## ✨ Features

| Feature | Details |
|---|---|
| 📋 Assignments & 📝 Quizzes | Both types supported, clearly labeled |
| 🟢 Live Status | Ongoing / Ending Soon / Ended — updates automatically |
| ☁️ Real-time Sync | Powered by Firebase Firestore — all classmates see the same data instantly |
| 🔍 Search | Search by title or subject name |
| 🗂️ Filter & Sort | Filter by subject, type, or status; sort by deadline or subject |
| 🌙 Dark / Light Mode | Toggle between themes |
| 📱 Mobile Friendly | Fully responsive — works on phones and tablets |
| 🗑️ Delete | Remove an item for everyone if it was posted by mistake |

---

## 🎓 Subjects Covered

- Comp Organisation \| Assembly Lang. (Lab / Th)
- Mobile Application \| Development (Lab / Th)
- Programming for Artificial Intelligence (Lab / Th)
- Parallel \| Distributed Computing (Lab / Th)
- HCl \| Computer Graphic (Lab / Th)
- Web Technology (Lab / Th)

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Frontend | React 18 (via CDN + Babel) |
| Database | Firebase Firestore (real-time NoSQL) |
| Hosting | GitHub Pages |
| Styling | Pure CSS-in-JS (no frameworks) |
| Fonts | Libre Baskerville + IBM Plex Sans + IBM Plex Mono |

> This is a **zero-build** app — no Node.js, no npm, no bundler needed. Everything runs from a single `index.html` file.

---

## 🚀 Setup & Deployment

### Step 1 — Firebase Setup

1. Go to [console.firebase.google.com](https://console.firebase.google.com) and create a project named `fall-2024-b`
2. Click **Firestore Database** → **Create database** → choose **Test mode**
3. Go to **Project Settings** → **Your apps** → click the `</>` Web icon → copy your `firebaseConfig`
4. Go to **Firestore → Rules** and publish the following:

```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if true;
    }
  }
}
```

### Step 2 — Paste Your Config

Open `index.html` in any text editor and find this block near the top:

```js
firebase.initializeApp({
  apiKey:            "...",
  authDomain:        "...",
  projectId:         "...",
  ...
});
```

Replace the values with your real Firebase credentials and save.

### Step 3 — Deploy to GitHub Pages

1. Create a new **public** GitHub repository
2. Upload `index.html` (rename `Fall2024B.html` → `index.html`)
3. Go to **Settings → Pages** → set Branch to `main` → Save
4. Your app goes live at `https://your-username.github.io/repo-name/`
5. Share the link with your class 🎉

---

## 📁 Project Structure

```
fall-2024-b/
└── index.html        ← The entire app (HTML + CSS + JS + Firebase)
└── README.md         ← This file
```

That's it. One file runs the whole thing.

---

## 🔒 A Note on Security

This app uses **open Firestore rules** (`allow read, write: if true`) which means anyone with the link can add or delete items. This is intentional for a trusted class group with no login requirement.

If you want to restrict access in the future, consider adding Firebase Authentication.

---

## 🤝 How to Use (for classmates)

1. Open the app link in any browser
2. Click **"+ Add"** to post a new assignment or quiz
3. Fill in: Type, Subject, Title, Source, Deadline, and optional Notes
4. Click **"☁ Add for Class"** — it appears for everyone instantly
5. Click any card to see full details or delete it

---

## 👨‍💻 Built With

- [React](https://react.dev/)
- [Firebase](https://firebase.google.com/)
- [Google Fonts](https://fonts.google.com/)
- [GitHub Pages](https://pages.github.com/)

---

## 📄 License

This project is open for personal and educational use by classmates of Fall-2024-B.
