# IMRANS-AI

## What's Fixed in v2.1
- ✅ **No Visual Studio / C++ required** — removed `better-sqlite3`
- ✅ Uses a plain JSON file as database — works everywhere
- ✅ `dotenv` included — `.env` loads automatically

---

## Project Structure

```
jarvis/
├── backend/
│   ├── server.js        ← Node.js + Express + Claude API
│   ├── package.json     ← Pure-JS deps only
│   ├── .env.example     ← Copy to .env, add your key
│   └── jarvis-db.json   ← Created automatically (your data)
└── frontend/
    └── index.html       ← The JARVIS UI
```

---

## STEP 1 — Node.js

Download LTS from **https://nodejs.org** and install.

```powershell
node --version   # must be v18+
```

---

## STEP 2 — Get Your API Key

1. Go to **https://console.anthropic.com**
2. Sign in → API Keys → Create Key
3. Copy the key (starts with `sk-ant-...`)

---

## STEP 3 — Add Your Key

Open PowerShell inside `jarvis\backend\` and run:

```powershell
copy .env.example .env
notepad .env
```

Edit the file — replace the placeholder with your real key:
```
ANTHROPIC_API_KEY=sk-ant-api03-YOUR-REAL-KEY-HERE
PORT=4000
```
Save and close.

---

## STEP 4 — Install & Run

```powershell
cd jarvis\backend
npm install
npm start
```

Expected output:
```
╔══════════════════════════════════════════╗
║       J.A.R.V.I.S Backend Online        ║
║  URL     : http://localhost:4000         ║
║  API Key : ✅ Configured                 ║
╚══════════════════════════════════════════╝
✅ Ready! Open: http://localhost:4000
```

---

## STEP 5 — Open in Browser

Go to: **http://localhost:4000**

Or double-click `frontend/index.html` (voice works better via localhost).

---

## Features

| Feature | How to use |
|---------|-----------|
| 💬 Chat | Type + Enter or SEND button |
| ⚡ Stream | Click STREAM button — words appear live |
| 🎤 Voice | Click mic button or Arc Reactor → speak |
| 🔁 Auto-voice loop | Enable VOICE tab — listens again after reply |
| 📋 Tasks | Say "add task: do the thing" |
| 🔔 Reminders | Say "remind me to call at 15:00" |

---

## Troubleshooting

**"BACKEND OFFLINE" in UI**
→ Run `npm start` in `backend/` folder and keep terminal open

**API key error**
→ Check `.env` is inside `backend/` folder (not the jarvis root)
→ No spaces: `ANTHROPIC_API_KEY=sk-ant-...` ✅

**npm install fails**
→ Delete `node_modules` folder → run `npm install` again
→ Or try: Run PowerShell as Administrator

**Microphone not working**
→ Allow mic permission in browser
→ Use Chrome — best voice support
→ Must use `http://localhost:4000` not `file://`

---

## Every Time You Start

```powershell
cd jarvis\backend
npm start
# Open http://localhost:4000 in Chrome
```
