# Credits & Disclosures

Full disclosure of pre-existing code, libraries, and external resources used
in **Ravensmoor: The Forgotten Name**, per the hackathon's originality rules.

## Libraries

| Resource | Version | Source | License | Used for |
|---|---|---|---|---|
| three.js | r128 | `cdnjs.cloudflare.com` | MIT | Rendering/running the explorable 3D world (scene, camera, lighting, meshes, animation loop). Loaded directly from CDN — unmodified. |

## Fonts

| Resource | Source | License | Used for |
|---|---|---|---|
| Cinzel | Google Fonts | Open Font License | Display typography |
| Cormorant Garamond | Google Fonts | Open Font License | Body typography |
| EB Garamond | Google Fonts | Open Font License | Utility/UI typography |

## AI services

| Service | Model | Used for |
|---|---|---|
| Anthropic API | `claude-sonnet-4-6` | Live, in-game NPC conversation with persistent memory. Requires API access in the hosting environment; falls back to static dialogue otherwise. |

## Original work

Everything else — the full story script and branching structure, the
reputation/faction/quest/achievement systems, the save system, all UI/CSS
design, the 3D world's scene construction, NPC behavior and rivalry logic,
the weather/day-night/festival systems, and the minimap — was written for
this project.

*(If any part of this was carried over from a prior personal project,
template, or earlier experiment, list it here explicitly, noting what was
reused vs. newly built during the hackathon window.)*

## AI-assisted development

AI tools were used during development — see the README for which tools and
how, and the accompanying `ai-traces.zip` for full logs, prompts, and chat
history from the build process.
