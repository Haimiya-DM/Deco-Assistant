# 📱 Mobile Setup Guide
### Build & install AI Deco Assistant on Android — no PC needed

This guide uses **GitHub Actions** to compile the mod in the cloud.
Your phone is used only for editing files and downloading the result.

---

## 📋 What You Need

- Android phone with Geometry Dash installed
- [Geode](https://geode-sdk.org) mod loader installed on GD
- A GitHub account (free at github.com)
- A Google account (for Gemini API)
- Any mobile browser

**Time:** ~15 minutes first time, ~5 minutes for updates.

---

## PART 1 — Get Your Gemini API Key

1. Open your browser → go to **aistudio.google.com**
2. Sign in with your Google account
3. Tap **Get API key** in the sidebar
4. Tap **Create API key** → **Create API key in new project**
5. Copy the key (starts with `AIza...`) — save it somewhere

> ✅ Gemini 2.0 Flash is **completely free** — no credit card needed.

---

## PART 2 — Create the GitHub Repo

1. Go to **github.com** → sign in (or create a free account)
2. Tap **+** (top right) → **New repository**
3. Settings:
   - Name: `ai-deco-mod`
   - Visibility: **Public**
   - ✅ Add a README file
4. Tap **Create repository**

---

## PART 3 — Add Your API Key as a Secret

> This keeps your key private and makes it available to the build.

1. In your repo → **Settings** tab (top)
2. Left sidebar → **Secrets and variables** → **Actions**
3. Tap **New repository secret**
4. Name: `GEMINI_API_KEY`
5. Secret: paste your `AIza...` key
6. Tap **Add secret**

---

## PART 4 — Create All 5 Files

In GitHub, tap **Add file** → **Create new file** for each file below.
After pasting content, scroll down and tap **Commit changes**.

---

### File 1: `mod.json`

Type `mod.json` as the file name. Paste the contents from the [mod.json](mod.json) file.

---

### File 2: `CMakeLists.txt`

Type `CMakeLists.txt` as the file name. Paste from [CMakeLists.txt](CMakeLists.txt).

---

### File 3: `.github/workflows/build.yml`

> GitHub will auto-create the folders when you type the full path.

Type `.github/workflows/build.yml` as the file name (exactly including the dots and slashes).
Paste from [build.yml](.github/workflows/build.yml).

---

### File 4: `src/main.cpp`

Type `src/main.cpp` as the file name.
Paste the full content from [main.cpp](src/main.cpp).

---

### File 5: `README.md` (optional but nice)

Already exists from when you created the repo. You can leave it or replace it.

---

## PART 5 — Watch the Build

1. Go to your repo → **Actions** tab (top menu)
2. You should see a workflow called **Build Mod** running (yellow spinner)
3. Wait 3–6 minutes
4. When you see a ✅ green checkmark — it succeeded!

> ❌ If it fails: tap on the failed run → read the error. Most common issue is a typo in one of the files. Check that `mod.json` and `CMakeLists.txt` match exactly.

---

## PART 6 — Download the .geode File

1. Click on the ✅ green build run
2. Scroll down to the **Artifacts** section
3. Tap **dm.ai-deco-assistant** to download a `.zip`
4. Extract the `.zip` on your phone — you'll find a `.geode` file inside

---

## PART 7 — Install the Mod

1. Move the `.geode` file to:
   ```
   Android/data/com.robtopx.geometryjump/files/geode/mods/
   ```
   Use any file manager app (Files by Google, MT Manager, etc.)

2. Open **Geometry Dash**
3. Geode will detect the new mod automatically
4. You'll see a notification at the bottom — tap **Restart** if prompted

---

## PART 8 — Add Your API Key

1. In GD main menu → tap the **Geode** button (bottom right)
2. Find **AI Deco Assistant** → tap the ⚙️ gear icon
3. Tap the `Gemini API Key` field
4. Paste your `AIza...` key
5. Tap **Apply**

---

## PART 9 — Using the Mod

1. Create or open a level in the **GD editor**
2. Look for the **pink star button** on the right side of the screen
3. Tap it to open the **AI Deco Assistant**
4. Follow any of these workflows:

### Quick Start
```
1. Tap a preset (HELL / SPACE / OCEAN / NEON / NATURE)
2. Set your BPM in the BPM field
3. Hit GO
4. Wait ~30 seconds for 3 passes to complete
5. Hit CONFIRM or REJECT
```

### Custom Vibe
```
1. Type your own description in the text field
   e.g. "volcanic hellscape with purple lightning and black crystals"
2. Hit GO
```

### Section Decoration
```
1. Select the gameplay objects in the section you want to decorate
2. Tap SEL — it reads their X bounds automatically
3. Type your vibe and hit GO
4. Only that section will be decorated
```

---

## 🔄 Updating the Mod

To make changes (new features, bug fixes):

1. Edit any file in your GitHub repo
2. Commit the change
3. Actions will automatically rebuild
4. Download new `.geode` and replace the old one in your mods folder

---

## ❓ Troubleshooting

| Problem | Solution |
|---------|----------|
| Build fails | Check that all 4 files are created with exact content |
| API error in mod | Double-check your API key in Geode settings |
| No pink button | Make sure the mod is in the correct folder and GD was restarted |
| Objects overlap gameplay | Use lower confidence prompts, or enable section mode |
| Build takes forever | GitHub free tier can be slow — wait up to 10 mins |
| `.geode` file not found after extracting | Look inside any nested folders in the `.zip` |

---

## 📂 Writable GD Folder Path

The mod saves `ai_deco_log.txt` here when you tap LOG:
```
Android/data/com.robtopx.geometryjump/files/ai_deco_log.txt
```

---

*Guide written for GD 2.2074 + Geode 4.3.1 on Android.*
