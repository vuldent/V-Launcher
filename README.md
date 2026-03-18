# V-Launcher
<div align="center">

<img src="public/vt-logo.svg" width="80" height="92" alt="V Team Launcher"/>

<br/><br/>

**you ever look at steam and think — why does this feel like a chore?**

yeah. so we built our own.

<br/>

[![Release](https://img.shields.io/badge/v1.0.0-A855F7?style=for-the-badge&labelColor=0a0a0a)](https://github.com/vuldent/vteam-launcher/releases)
[![Windows](https://img.shields.io/badge/Windows-7B2FBE?style=for-the-badge&logo=windows&logoColor=white&labelColor=0a0a0a)](https://github.com/vuldent/vteam-launcher/releases)
[![Electron](https://img.shields.io/badge/Electron_29-A855F7?style=for-the-badge&logo=electron&logoColor=white&labelColor=0a0a0a)](https://electronjs.org)
[![React](https://img.shields.io/badge/React_18-7B2FBE?style=for-the-badge&logo=react&logoColor=white&labelColor=0a0a0a)](https://react.dev)

<br/>

![preview](https://raw.githubusercontent.com/vuldent/vteam-launcher/main/preview.png)

</div>

---

## what even is this

V Team Launcher is a desktop game launcher we built from the ground up. it started as a simple launcher for an Eyes: The Horror Game mod and kind of just... kept going. now it tracks your playtime, logs your moods after sessions, manages your saves, shows you a heatmap of when you actually play, and lets you theme the whole UI per game.

it's built on Electron + React. runs on Windows. looks nothing like anything else.

---

## what it does

**the basics**

point it at any `.exe` on your PC and it becomes part of your library. each game gets its own color scheme — switch games and the whole interface shifts. there's a sidebar with instant navigation, and the app opens maximized because small launchers are a waste of time.

**before you launch**

it asks how you're feeling. chill? focused? hyped? tired? based on your answer it adjusts quality settings automatically. if you want to go deeper, turn on Ritual Mode — a hype sequence that plays before every launch. set a session goal too, and it'll check in with you after.

**after you close the game**

a popup appears. rate the session. log your mood. write a note. it compares your session length to the last one — "you played 12 minutes longer than last time" kind of thing. all of it goes into your Play Diary, which is exactly what it sounds like.

**everything else**

- backup and restore save files
- track mods per game with on/off toggles
- log achievements yourself
- browse screenshots from inside the launcher
- combined stats across all games with a 12-week heatmap
- live CPU and RAM monitor
- Discord Rich Presence so your status actually shows the right game
- share cards to flex your stats

**making it yours**

12 color presets. custom accent colors. background themes — stars, orbs, snow, webs, rain. transparent UI mode. adjustable row spacing. corner radius slider. it's a lot of knobs.

---

## there's a secret

type `VULDENT` on your keyboard anywhere in the app.

that's all we're saying.

---

## getting it running

```bash
git clone https://github.com/vuldent/vteam-launcher.git
cd vteam-launcher

npm install --ignore-scripts
npm install electron@29 --save-dev --foreground-scripts

npm run dev
```

to build the actual installer:

```bash
npm run dist
```

lands in `dist/` as a proper Windows `.exe` setup file.

> got an electron error on install? run `rmdir /s /q node_modules\electron` then try the install steps again.

---

## what's under the hood

| | |
|---|---|
| Electron 29 | desktop runtime |
| React 18 | UI |
| Zustand | state management |
| Framer Motion | animations |
| Syne + DM Mono | fonts |
| electron-builder | packaging |

---

## how the folders are laid out

```
vteam-launcher/
├── electron/
│   ├── main.js        — game launching, IPC, session tracking, save backup
│   ├── preload.js     — bridges electron to the React side
│   └── discord.js     — handles Discord support replies
├── public/
│   ├── vt-logo.svg    — the hexagon logo
│   └── icon.ico
└── src/
    ├── App.jsx         — root layout, star background, page routing
    ├── store.js        — all global state lives here
    ├── index.css       — design tokens and base components
    ├── components/     — Sidebar, Settings, Splash, TabBar, Titlebar, etc.
    └── pages/          — Stats, Diary, Saves, Mods, Screenshots, Social, Achievements
```

---

<div align="center">

made by **[Vuldent](https://vuldent.carrd.co)** · V Team

*"your launcher. your rules."*

</div>
