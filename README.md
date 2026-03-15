# 🎨 AI Deco Assistant
### Gemini 2.0 Flash Vision · 3-Pass Multi-Layer · BPM Triggers · by D.M

An intelligent Geometry Dash level decorator powered by Google Gemini's vision AI.
Instead of decorating blindly, this mod **screenshots your editor**, sends it to Gemini,
and places deco that works **around your actual layout**.

---

## ✨ Features

### 🔭 Vision-Aware Layout Analysis
The mod captures your editor as an image before each pass. Gemini analyzes:
- Where the ground line is
- Where gameplay blocks and spikes are
- What empty space is available
- What was already placed in previous passes

Deco is placed to **avoid overlapping gameplay** objects.

### 🎭 3-Pass Multi-Layer System
Every decoration run does **3 separate passes**, each with a fresh screenshot:

| Pass | Layer | Z | Scale | Purpose |
|------|-------|---|-------|---------|
| 1 | Background | -3 | 1.5–4.0 | Big atmospheric shapes, sets the mood |
| 2 | Midground | -1 | 0.8–2.0 | Detail fill, builds visual depth |
| 3 | Foreground + Triggers | 1–3 | 0.3–1.2 | Accents, glow, color/pulse triggers |

This is the same layering approach used by top GD decorators like Knobbelboy and ViPriN.

### 🎵 BPM-Aware Trigger Placement
Enter your song's BPM and all color/pulse triggers in Pass 3 are snapped to the
**beat grid** automatically. Triggers land on actual beats.

`Beat interval (units) = 311 × (60 / BPM)`

### 🎨 Style Presets
Five built-in prompts that produce consistent, professional results:

| Preset | Vibe |
|--------|------|
| **HELL** | Hellfire, deep reds, lava glow, bone shapes |
| **SPACE** | Cosmic void, nebula glows, lens flares, crystal formations |
| **OCEAN** | Abyssal depth, bioluminescent particles, light rays |
| **NEON** | Cyberpunk black, hot pink and blue neon, grid lines |
| **NATURE** | Enchanted forest, fireflies, vine silhouettes, golden light |

You can also write your own custom prompt.

### 📐 Section-Based Decoration
Restrict decoration to a specific X range so you can decorate **one section at a time**:
- Enter X start/end manually, OR
- Select objects in the editor and hit **SEL** — it reads their bounds automatically

### 🗂 Object Palette Control
Toggle **OWN:ON** to restrict Gemini to only safe, always-owned object IDs.
Prevents it from generating objects you haven't unlocked.

### 👁 Preview Mode
When enabled, placed objects appear at **50% opacity** so you can review
before committing. Hit **CONFIRM** to keep or **REJECT** to wipe.

### 📊 Confidence Rating
Gemini rates its own confidence (0–100%) on how clearly it can see your layout.
If below 70%, you get a warning before objects are placed.

### 📤 Chat Log Export
Hit **LOG** to save the full conversation history to `ai_deco_log.txt` in your
GD writable folder. Reuse good prompts on future levels.

---

## 🎮 In-Editor UI

A **pink star button** appears on the right side of the editor screen.
Tap it to open the AI Deco Assistant popup.

```
┌─────────────────────────────────────────┐
│         AI Deco Assistant               │
│    Gemini 2.0 Flash | 3-Pass Vision     │
├─────────────────────────────────────────┤
│  [Chat area — AI responses appear here] │
│                                         │
│  [HELL] [SPACE] [OCEAN] [NEON] [NATURE] │
│  BPM:[120]  X:[start] to [end]  [SEL]   │
│  [___ describe your vibe ________] [GO] │
│  [UNDO]    [LOG]    [OWN:OFF] [PRV:ON]  │
│  Status: Type a vibe and hit GO!        │
└─────────────────────────────────────────┘
```

---

## 🔑 API Key

This mod uses **Gemini 2.0 Flash** which is **completely free** with a Google account.

1. Go to [aistudio.google.com](https://aistudio.google.com)
2. Sign in with Google
3. Tap **Get API Key** → **Create API key**
4. In GD: Geode menu → AI Deco Assistant → Settings → paste key

---

## ⚙️ Settings

| Setting | Description |
|---------|-------------|
| `api-key` | Your Gemini API key from AI Studio |


---

## 📝 Credits

- **Mod code & design** — D.M
- **AI engine** — Google Gemini 2.0 Flash
- **Mod framework** — [Geode SDK](https://geode-sdk.org)
- **Inspiration** — Tidal Wave, Yatagarasu, Bloodbath decoration style

---

*Made with 💜 for the GD community.*
