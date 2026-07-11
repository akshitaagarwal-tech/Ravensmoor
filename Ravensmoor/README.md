<div align="center">

# 🕯️ RAVENSMOOR
### *The Forgotten Name*

*You know everyone's name at this school. They all know yours.*
*You're the only one who doesn't.*

**[▶ PLAY THE GAME](#)** &nbsp;·&nbsp; **[📂 SOURCE CODE](#)** &nbsp;·&nbsp; **[🎬 DEMO GIF/VIDEO](#)**

![status](https://img.shields.io/badge/status-playable-brightgreen)
![engine](https://img.shields.io/badge/engine-three.js-black)
![platform](https://img.shields.io/badge/platform-browser-blue)
![build](https://img.shields.io/badge/build-24hr%20hackathon-orange)
![ai](https://img.shields.io/badge/AI-Claude--powered%20NPCs-8A63D2)

</div>

---

> *"You were never supposed to return," the voice had said. It hadn't been a*
> *threat. It had been a warning — and you had come back anyway.*

---

## 📖 Table of contents

- [The pitch](#-the-pitch)
- [Why it's more than a text-adventure](#-why-its-more-than-a-text-adventure)
- [60-second evaluation](#-60-second-evaluation)
- [How to play](#-how-to-play)
- [Under the hood](#️-under-the-hood)
- [What was built in the 24-hour window](#-what-was-built-in-the-24-hour-window)
- [AI tools used](#-ai-tools-used)
- [Prior work / external resources](#-prior-work--external-resources)
- [Known limitations](#-known-limitations)
- [Run it locally](#-run-it-locally)
- [Submission contents](#-submission-contents)

---

## 🎯 The pitch

You arrive at Ravensmoor Academy having forgotten your own name — and
everyone around you already seems to know exactly who you are. **Ravensmoor**
is a choice-driven gothic narrative that you don't just *read*, you **walk
through**: click your way down a branching story on the page, then step
straight into a fully explorable 3D campus, sit at the table of one of four
rival Orders, get pulled into other students' feuds, and chase down seven
scattered mysteries that all circle back to the same question — *who were
you, before someone made you forget?*

It ships as a **single self-contained HTML file.** No installs, no accounts,
no build pipeline. Open the link, and you're standing at the gates.

## ✨ Why it's more than a text-adventure

Most browser narrative games are text and buttons. Ravensmoor layers a real
game world underneath the prose.

**📜 Story & progression**
- A hand-written branching story engine with real consequences: **4
  reputation traits** (courage, wisdom, cunning, loyalty), **faction
  standing** with rebels and professors, and **3 distinct epilogue endings**
  shaped by how you played
- **4 rival Orders** to pledge yourself to — Ember, Still Water, Root, Silver
  Tongue — each with its own hall, its own hearth, its own loyalty
- **7 hidden mysteries** scattered across named locations (the Bell Tower,
  the Whispering Cellar, the Hollow Vault beneath the lake), each with its
  own clue and its own payoff
- **5 memory fragments** to physically recover, and **17 tracked
  achievements**
- Full **save/load**, a **journal**, and an **achievements** screen

**🗺️ A living 3D world, not a menu**
- Third-person explorable campus built on three.js — real-time movement,
  camera, a **minimap**
- A **day/night cycle** and **seasonal weather system** (rain, snow, fog)
  that shifts on its own while you play, plus season-specific **festivals**
  with their own names and lantern events
- **NPCs with their own lives** — students and professors who move around
  the grounds on their own, and occasionally clash with each other in
  unscripted **rivalry flare-ups** you can walk in on and choose to
  de-escalate or provoke

**🤖 Experimental live-AI NPC conversation**
- NPCs aren't just dialogue trees — you can **type a message directly to
  them**. Where API access is available, their replies are generated live by
  Claude and they **remember what you told them** across the conversation,
  updating a relationship score and even recalling promises you made
- Where API access *isn't* available, it degrades gracefully to
  hand-written dialogue automatically — the game is never broken by the
  absence of this feature (see [Known limitations](#-known-limitations))

**🎨 Craft**
- A fully custom parchment-and-candlelight visual language — no template,
  no starter kit — built from scratch with Cinzel/Cormorant Garamond
  typography and hand-tuned CSS

## 🏆60-second evaluation

| Criterion | Where to look |
|---|---|
| **Originality** | Not a reskinned template — hand-written story + hand-built 3D scene. Check [Prior work](#-prior-work--external-resources) for the two external libraries used (three.js, Google Fonts) — everything else is original. |
| **Technical depth** | Combines a full narrative state machine with a real-time three.js world (custom NPC AI, weather system, minimap, day/night cycle) *and* a live LLM integration for NPC dialogue with persistent memory. |
| **Creative use of AI** | NPCs you can freely converse with, whose replies and memories are generated live via Claude — not scripted branches pretending to be a chat. |
| **Completion / polish** | Full game loop: start → branching story → explorable world → mysteries → endings → achievements, all wrapped in a coherent, finished visual theme. |
| **Fun factor** | Multiple endings, a discovery loop (7 mysteries, 5 memories, 17 achievements) that rewards exploring the world, not just clicking through text. |

## 🎮 How to play

**On the page — the story**

| Input | Action |
|---|---|
| Click a choice | Advance the story |
| `Esc` | Close journal / achievements / settings |

Progress autosaves as you go; a manual save button is also available in
Settings.

**In the world — press "Enter the Grounds" from the story**

| Input | Action |
|---|---|
| `W` `A` `S` `D` / arrow keys | Move |
| Mouse | Look around |
| `Shift` | Sprint |
| `E` | Interact with the nearest NPC, zone, or event |
| Touch controls | Available on mobile / tablet |

No installation, no account. Everything runs client-side; saves live in
`localStorage`, so progress is per-browser, per-device.

## 🛠️ Under the hood

Single self-contained `index.html` — no build step, no bundler, no server.
Open it and it runs.

| Layer | What it does |
|---|---|
| **Rendering** | three.js (r128) — custom low-poly scene, animated NPCs, dynamic lighting, weather particles, a hand-rolled canvas minimap |
| **Story engine** | Hand-written node/choice graph driving text, branching, and state — reputation, faction standing, quests, achievements, and mysteries all feed back into what the story *and* the world show you |
| **Persistence** | `localStorage`-based save/load, no backend required |
| **Live NPC dialogue** | Optional call-out to Claude (`claude-sonnet-4-6`) for freeform NPC conversation with memory of what you've said, with a static-dialogue fallback when no API access is present |

## 🧱 What was built in the 24-hour window

*(Fill in with specifics — judges weight this heavily, and vague claims cost
points. Check off / rewrite based on what you actually built, and call out
anything carried in from before the window.)*

- [ ] Full branching story script and the node/choice engine driving it
- [ ] Reputation, Order-allegiance, faction standing, quest, and achievement
      systems
- [ ] Save/load system
- [ ] The three.js world: player movement/camera, minimap, day-night cycle,
      seasonal weather, festival events
- [ ] NPC population: movement, scheduling, rivalry flare-up behavior
- [ ] The live-AI NPC chat layer and its memory/relationship system
- [ ] Full visual design system (theme, fonts, HUD, modals, journal)

## 🤝 AI tools used

*(Fill in specifically — name the tool and roughly what for)*

- Claude — [story writing / code scaffolding / debugging / etc.]
- [Any other tools]

Full prompts, chats, and logs from the build are included as a separate zip
in the submission — see [Submission contents](#-submission-contents).

## 📚 Prior work / external resources

- **[three.js](https://threejs.org/)** r128 — loaded via cdnjs CDN, MIT
  licensed. Used for all 3D rendering; not modified, not authored by us.
- **Google Fonts** — Cinzel, Cormorant Garamond, EB Garamond, via the Google
  Fonts CDN, for the visual theme.
- *(Add any tutorial, starter template, or prior personal experiment
  referenced, if any)*

Full disclosure list in [`CREDITS.md`](./CREDITS.md).

## ⚠️ Known limitations

- The live-AI NPC chat calls the Anthropic API directly from the browser and
  depends on API access being available in the hosting environment. On a
  standard static deploy without a backend proxy and key, those calls fail —
  the game detects this and **automatically falls back** to its static,
  hand-written NPC dialogue, so nothing breaks for players.
- Save data is local to the browser/device; there's no cloud sync.

## 💻 Run it locally

No build tools needed.

```bash
git clone <your-repo-url>
cd ravensmoor
open index.html   # or just double-click it
```

## 📦 Submission contents

- Deployed game URL — top of this README
- This repository, including commit history
- This README
- [`CREDITS.md`](./CREDITS.md) — full disclosures for third-party code/fonts
- A separate zip of AI-agent traces (prompts, chats, logs) from the build
  process
