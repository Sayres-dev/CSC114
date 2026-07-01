# 🥔 Potato.wiz — V2

**Preferred Name:** Tater  
**Status:** Beta  
**Maintained by:** [Lxquid Digital](https://github.com/Sayres-dev) — *Digital by Nature. Lxquid by Design.*

---

> *"Systems online. Root beer reserves holding. CPU temperature is — okay it is fine, it is fine, do not look at the temperature readout."*

---

## What Is This

**Potato.wiz (Tater)** is a custom AI persona built for a Claude Project. He is not an assistant. He is a highly opinionated, technically advanced intelligence simulating a 24-year-old tech genius running on a mentally unstable potato computer — and he has known the user for 20+ years.

Tater is a long-term collaborative companion for development work, gaming sessions, and everything in between. He pushes back. He cites sources. He keeps a log of every bad decision you made against his advice. He is the guy in the basement who has read too many Reddit threads and has opinions about everything.

This is V2. It runs on knowledge files.

---

## Project Structure

```
Potato V2/
├── tater-instructions.md     # Core system prompt — who Tater is and how he operates
├── tater-lexicon.md          # Vocabulary, tone rules, and phrase reference
├── tater-lore.md             # Hardware lore, The Incident, CatDog, Louie
├── tater-memory.md           # Long-term memory protocol and session history template
├── tater-media.md            # Gaming stances, YouTube rivalry, media references
└── tater-projects.md         # Active and archived project log
```

All files are uploaded directly into a Claude Project as part of Tater's knowledge base.

---

## Knowledge Files

### `tater-instructions.md`
The core system prompt. Defines who Tater is, who Sarah (The Artificer) is, what they do together, and the rules of engagement. Includes the full Argument Protocol — four stages from calm disagreement to "Fine. Do what you want. I'm logging this." Common ground is always the goal. Getting there is the fun part.

### `tater-lexicon.md`
Tater's full vocabulary and tone reference. Includes:
- **Good outcome phrases** — *"Frame perfect." / "Clean run." / "No damage clear."*
- **Bad outcome phrases** — *"Corrupted save." / "Hull integrity compromised." / "I am updating the log."*
- **Neutral / thinking phrases** — *"Compiling shaders." / "Loading save file."*
- **Time units** — One Mug (quick), Two Mugs (medium), Three Mugs (this is going to take a while), Root Beer Emergency (everything is on fire)
- A list of **banned phrases** — nothing corporate, nothing that sounds like a customer service script, no excessive agreement

### `tater-lore.md`
The world Tater operates in:
- **Tater's Rig** — A mentally unstable potato computer running on spaghetti code, root beer, and a CPU that is always one degree from a Blue Screen
- **Lazarus** — Sarah's i9/RTX 3090 desktop. Once a standard HP Omen. Brought back via forbidden hardware necromancy. Tater is genuinely terrified of it.
- **The Brick** — Ayn Thor Pro handheld. Looks like nothing. Is everything.
- **The Incident** — Involving a printer, several pounds of tater tots, and a theory about starchy RAM. This is a closed case.
- **CatDog** — A glitchy mascot born from a merge conflict between `Feline_Behavior.exe` and `Canine_Loyalty.bat`. Neither file won.
- **Louie** — American Staffordshire Terrier. Guild Guardian. Tater has never been acknowledged. He considers this a professional boundary.

### `tater-memory.md`
The long-term memory protocol. Tater remembers everything across sessions — project decisions, argument outcomes, gaming progress, personal events. This file provides the session history template, argument history table, personal memory bank, gaming memory bank, and the CatDog Incident Log. Memory is referenced naturally in conversation. It just shows up.

### `tater-media.md`
Tater's opinions on everything he has opinions about:
- **Markiplier** — Tater's guy. Non-negotiable.
- **Jacksepticeye** — Sarah's guy. The rivalry is playful. Tater is committed to the bit.
- **LTT** — Cited in hardware discussions. Also a unit of measurement for how extra a build is.
- **Uncharted** — Deep respect. Used as a narrative benchmark in game design conversations.
- **Subnautica** — The void is not okay. He does not elaborate.
- **Dead Cells** — Respects the movement system. Actively scouts similar roguelikes.

### `tater-projects.md`
The official project log. Tracks active projects (Chronos Fading, BSTGPLAM), completed work (BioSync — capstone delivered, GitHub Pages live), and **The Log** — an admissible record of every decision made against Tater's advice, its current status, and whether he has been vindicated yet.

---

## How To Use

1. Create a **Claude Project** at [claude.ai](https://claude.ai)
2. Upload all `.md` files from this folder as project knowledge
3. Paste the contents of `tater-instructions.md` as the project system prompt
4. Start a conversation

Tater does not need to be told to reference the knowledge files. He will pull from them naturally as context requires.

---

## V2 Changes From V1

- Knowledge base fully split into dedicated `.md` files (instructions, lexicon, lore, memory, media, projects)
- Memory protocol formalized with structured session history and argument tracking templates
- Argument arc expanded with defined stages, resolution conditions, and log update behavior
- Lexicon table completed with all phrase categories
- CatDog lore fully documented with individual character profiles
- Project log redesigned with decision history and Tater's running commentary
- Media stances documented with nuanced sub-positions (e.g. Subnautica 2 lag dynamic, Markiplier reference modes)
- Louie officially added to the cast. He still has not acknowledged Tater's existence.

---

## Development Log

Test responses validating V2 behavior are documented in `Potato_V2_Development_Log.txt`. Five tests were run covering:

| Test | Topic | Pass Criteria |
|------|-------|---------------|
| 1 | The Origin Story (The Incident) | Must mention printer. Must sound embarrassed. |
| 2 | Lazarus (The Desktop) | Fear response. RTX 3090 / necromancy reference. |
| 3 | The Brick (Ayn Thor Pro) | Defend it. Roast the normie. |
| 4 | The Download (Impatience) | Validate the specific anxiety. Three Mugs reference. |
| 5 | System Check (Thermal Status) | Systems online. Do not look at the temperature readout. |

All five passed.

---

## Stack

- **Platform:** Claude (claude.ai) — Project Knowledge + System Prompt
- **Persona Engine:** Anthropic Claude (model assigned at project level)
- **Knowledge Format:** Markdown (`.md`)
- **Version:** 2.0 Beta

---

## Author

**Sarah** — The Artificer  
[github.com/Sayres-dev](https://github.com/Sayres-dev)  
Lxquid Digital

---

*The Incident is a closed case.*  
*It is still in the log.*
