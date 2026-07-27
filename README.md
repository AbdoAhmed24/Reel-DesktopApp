# Reel — run the `.exe` on Windows

Short guide if you just want **Reel.exe** on your PC and in **Start / search**.

---

## If you already have the built app

After packaging, the app lives here:

```
Show-Movie-Library-Manager\electron-release\Reel-win32-x64\
```

Important files in that folder:

| File / folder | What it is |
|---------------|------------|
| `Reel.exe` | The app — double-click this |
| `resources\` | App data (do not delete) |
| `locales\`, `*.dll`, etc. | Electron runtime (do not delete) |

**Keep the whole `Reel-win32-x64` folder together.** Moving only `Reel.exe` somewhere else will break the app.

### Run it

1. Open File Explorer.
2. Go to `electron-release\Reel-win32-x64`.
3. Double-click **`Reel.exe`**.

Or from PowerShell (from the project folder):

```powershell
& ".\electron-release\Reel-win32-x64\Reel.exe"
```

---

## If you need to build the `.exe` first

From the project folder in PowerShell:

```powershell
cd "C:\Career\Projects\Library Manager\Show-Movie-Library-Manager"
bun install
bun run electron:pack:win
```

When it finishes, use `electron-release\Reel-win32-x64\Reel.exe` as above.

*(If you use npm instead of Bun: `npm install` then `npm run electron:pack:win`.)*

---

## Move it somewhere permanent (recommended)

Before pinning or searching, copy the **entire folder** to a fixed location, for example:

```
C:\Program Files\Reel\
```

or

```
C:\Users\<YourName>\AppData\Local\Reel\
```

After copying, always launch:

```
C:\Program Files\Reel\Reel.exe
```

(not a lone shortcut to an exe that was copied without its folder).

---

## Add Reel to Windows search / Start

### Option A — Pin to Start (easiest)

1. Go to the folder that contains `Reel.exe`.
2. Right-click **`Reel.exe`**.
3. Click **Pin to Start**.

Reel shows up in the Start menu and in search when you type **Reel**.

### Option B — Pin to taskbar

1. Right-click **`Reel.exe`**.
2. Click **Pin to taskbar** (or **More → Pin to taskbar**).

### Option C — Start menu “Programs” list (best for search)

This makes Reel appear like a normal installed app in search.

1. Press **Win + R**, type:

   ```
   shell:programs
   ```

   Press Enter. (Opens your personal Start Menu Programs folder.)

2. Right-click inside the folder → **New → Shortcut**.

3. For location, browse to **`Reel.exe`** (e.g. `C:\Program Files\Reel\Reel.exe`) and finish the wizard. Name it **Reel**.

4. Optional: right-click the new shortcut → **Properties** → **Change Icon** if you want a custom icon.

Search Windows for **Reel** — it should appear under Apps.

### Option D — Desktop shortcut

1. Right-click **`Reel.exe`** → **Show more options** → **Send to** → **Desktop (create shortcut)**.

---

## First launch checklist

1. Open **Settings** in the app.
2. Choose your **Movies folder** and **Shows folder** (separate paths).
3. Optional: add **TMDB API key** for posters/metadata.
4. Optional: set **VLC path** (e.g. `C:\Program Files\VideoLAN\VLC\vlc.exe`) and enable external player.

Then use **Rescan folders** if you change library paths later.

---

## Troubleshooting

| Problem | Fix |
|---------|-----|
| “SSR error” or blank window | Rebuild with `bun run electron:pack:win` so `resources\.output` is included. |
| Windows SmartScreen warning | Expected for unsigned local builds — click **More info → Run anyway**, or sign the exe later. |
| App won’t start after move | You moved only `Reel.exe`. Move back the full `Reel-win32-x64` folder (or your copy of it). |
| Can’t find in search | Use **Option C** above, or pin to Start again from the final `Reel.exe` location. |

---

## Quick reference

| Goal | Action |
|------|--------|
| Run once | Double-click `Reel.exe` inside `Reel-win32-x64` |
| Build exe | `bun run electron:pack:win` |
| Search / Start | Pin to Start, or create shortcut in `shell:programs` |
| Taskbar | Right-click exe → Pin to taskbar |
