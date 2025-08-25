## Music & DAB-Related Projects (CLI, Streaming, APIs, GUIs)

### • DABHounds
**CLI tool** to convert YouTube/Spotify playlists into DABMusic libraries.  
**Language/Tech**:  Python 
**Link**: https://github.com/sherlockholmesat221b/DABHounds

### • Dab-Android-Beta-V2
**Flutter app** for music streaming using the DAB Music API.  
**Platform**: Android (Flutter).  
**Link**: https://github.com/holmesisback/Dab-Android-Beta-V2

### • godab
**Go CLI downloader** targeting `dab.yeet.su`.  
**Language**: Go (Golang).  
**Link**: https://github.com/jacopo-degattis/godab

### • Dyno-Music
**Playwright script** that scrapes and automates downloads from `dab.yeet.su`.  
**Tech**: JavaScript (Playwright).  
**Link**: https://github.com/super-roomi/Dyno-Music

### • OpenSpot
Free, **open-source music streaming app** with a polished, responsive UI.  
- **Tech stack**: React Native + Next.js for mobile and web; also includes Electron-based desktop builds.  
- **Key features**: High-quality streaming, one-click downloads, “Liked Songs,” no login required, offline support, modern UI (Framer Motion, Tailwind CSS).  
**Link**: https://github.com/BlackHatDevX/openspot-music-app

### • Harmony
**Music manager** built with **Electron**.  
**Platform**: Desktop (cross-platform).  
**Link**: https://github.com/jvegaf/harmony

### • Singularity (Flutter)
**Music player app** built with Flutter.  
**Platform**: = mobile
**Link**: https://github.com/atinba/Singularity

---

### Summary Table

| Project             | Type / Platform           | Primary Tech Stack                   | Highlights |
|---------------------|---------------------------|---------------------------------------|------------|
| DABHounds           | CLI (playlist converter)  | Python                                | Supports DABMusic library conversion |
| Dab-Android-Beta-V2 | Mobile App                | Flutter                               | Streams using DAB Music API |
| godab               | CLI downloader            | Go                                    | Downloads from `dab.yeet.su` |
| Dyno-Music          | Scraper automation        | JavaScript (Playwright)               | Automates multi-track downloads |
| OpenSpot            | Web / Mobile / Desktop    | React Native, Next.js, Electron       | Modern UI, offline, no-login streaming :contentReference[oaicite:1]{index=1} |
| Harmony             | Desktop music manager     | Electron                              | Organize and manage music locally |
| Singularity         | Mobile/Desktop player     | Flutter                               | Music playback with Flutter |

---


# 🌐 Wrap Your Web App with Electron

This repository demonstrates how to wrap any web-based application using [Electron](https://www.electronjs.org/). Electron allows you to run web apps as native desktop applications on Windows, macOS, and Linux.

## 📦 Features

- Load any web URL in a native window
- Customizable app title, icon, and window size
- Cross-platform support (Windows, macOS, Linux)
- Light and minimal boilerplate

---

## 🚀 Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (v14 or higher)
- npm (comes with Node.js)

---



## 📁 Project Structure

```
electron-webapp-wrapper/
├── assets/             # App icon (optional)
├── main.js             # Main Electron process
├── package.json        # Node dependencies and app metadata
└── README.md           # Project instructions (this file)
```

---

## 🧪 Run in Development

```bash
npm start
```

---

## 📦 Build for Production

Install [electron-packager](https://www.npmjs.com/package/electron-packager):

```bash
npm install -g electron-packager
```

Then run:

```bash
electron-packager . MyWebApp --platform=win32 --arch=x64 --icon=assets/icon.ico
```

Replace:
- `MyWebApp` with your app name
- `--platform` with `darwin`, `win32`, or `linux`
- `--icon` with your icon file path

More options available in the [Electron Packager docs](https://github.com/electron/electron-packager).

---

## ✏️ Example `main.js`

```javascript
const { app, BrowserWindow } = require('electron');

function createWindow() {
  const mainWindow = new BrowserWindow({
    width: 1200,
    height: 800,
    icon: __dirname + '/assets/icon.ico',
    webPreferences: {
      nodeIntegration: false,
    },
  });

  mainWindow.loadURL('https://your-web-app.com');
}

app.whenReady().then(createWindow);

app.on('window-all-closed', () => {
  if (process.platform !== 'darwin') app.quit();
});

app.on('activate', () => {
  if (BrowserWindow.getAllWindows().length === 0) createWindow();
});
```

---

## 🖼️ Optional: Add App Icon

1. Place an `.ico` (Windows) or `.icns` (macOS) icon file in the `assets/` folder.
2. Reference it in your `BrowserWindow` config:

```javascript
icon: __dirname + '/assets/icon.ico',
```

---

## 📜 License

MIT License

---

