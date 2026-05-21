# Callio Wave Add-in 🎙️

![Private](https://img.shields.io/badge/Code-Private%20%C2%B7%20Client%20Work-red?style=flat)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![WebExtensions](https://img.shields.io/badge/WebExtensions%20API-4285F4?style=flat&logo=googlechrome&logoColor=white)

> **Browser extension for Grandstream Wave softphone that surfaces AI call summaries and caller history in real-time — the moment a call ends.**

> ⚠️ This is a **portfolio showcase** — source code is proprietary and not included.

---

## 🧩 The Problem

When call center agents using Grandstream Wave finished a call, they had to:

1. Manually switch to the CRM tab
2. Search for the caller by phone number
3. Read through previous notes to get context
4. Write their own summary of what was discussed

This context-switching was slow, error-prone, and interrupted the agent's workflow at the exact moment they needed to take action.

---

## 💡 The Solution

Callio Wave Add-in is a browser extension that **automatically detects when a call ends** in the Grandstream Wave softphone tab and immediately displays a floating overlay showing:

- The AI-generated summary of the call (from [MigraCRM](https://github.com/deadlyrat/migra-crm-showcase))
- Caller history (previous calls, notes, action items)
- Suggested next actions

No tab switching. No searching. Everything right there, at the right moment.

---

## 🏗️ How It Works

```
Grandstream Wave (browser tab)
        │
        │  Extension monitors DOM for call-end events
        ▼
  [Callio Wave Extension]
  Vanilla JavaScript · WebExtensions API
        │
        │  Polls MigraCRM backend when call ends
        ▼
  [MigraCRM API]  ──► Returns: AI summary + caller history
        │
        ▼
  Overlay rendered in the Grandstream Wave tab
  (caller name · sentiment · summary · previous calls · action items)
```

---

## ✨ Features

| Feature | Description |
|---------|-------------|
| 🔔 **Call-end detection** | Monitors the Grandstream Wave DOM for call completion events |
| 📋 **AI Summary overlay** | Displays the Gemini-generated call summary directly in the softphone UI |
| 👤 **Caller history** | Shows previous interactions, notes, and CDR records for the caller |
| ✅ **Action items** | Surfaces suggested next steps from the AI analysis |
| ⚡ **Zero friction** | No manual trigger — the overlay appears automatically as the call ends |

---

## 🛠️ Tech Stack

| Concern | Technology |
|---------|-----------|
| Extension | Vanilla JavaScript · WebExtensions API (Chrome/Firefox) |
| Backend integration | REST polling against [MigraCRM](https://github.com/deadlyrat/migra-crm-showcase) API |
| Rendering | DOM injection into Grandstream Wave UI |

---

## 🔗 Related

This extension is a companion to **MigraCRM** — it has no value standalone. The AI summaries and caller history it displays are produced by MigraCRM.

👉 See [migra-crm-showcase](https://github.com/deadlyrat/migra-crm-showcase) for the full system architecture.

---

## 📬 Contact

Source code is proprietary. For enquiries: 📧 [pablozam1931@gmail.com](mailto:pablozam1931@gmail.com)

---

*Part of the [deadlyrat](https://github.com/deadlyrat) portfolio.*
