# 🎞️ *vbn-game*
## **Cinematic Intro Guide**
**Document Type:** Style, Formatting, & Visual Reference  
**Version:** 1.0  
**For:** Writers, Directors, Animators, and VO Artists  
**Project Folder:** `/references/Cinematic Intros/`  

---

## 🎬 **Purpose**
Each *Cinematic Intro* serves as a short (30–60 second) film vignette that defines a character's presence, tone, and mythology within *vbn-game*.  
These intros are used in-game, for promotional videos, or as session openings.  
Every scene should:  
- Establish **who** the character is through **action, atmosphere, and voice**.  
- Maintain a consistent **neo-noir gothic style** blending 1990s Arizona realism with vampiric decadence.  
- End with the signature **fade-to-black + title card** moment.

---

## 🎯 **Required First Step: Check Character Goals & Quest Ties**

Before writing a single line, query the `npc_goals` table (Supabase) for the character being introduced, joined on `character_id`. Do not skip this even for characters who seem simple (animals, mortals, background NPCs) — goals get added continuously and are not reliably reflected in older biography text.

For each goal row, check:
- **`goal_text`** — what the character is actually trying to do. This should shape the scene's central action, not just flavor a generic vignette.
- **`quest_slug`** — if populated, look up that quest in the `quests` table (`slug`, `title`, `summary`, `act_stage`). A populated quest_slug means the character's canonical introduction *is* that quest beat, not an invented standalone scene. Check for a linked design doc (referenced in the quest summary) before assuming none exists.
- **`secrecy`** — a goal marked `hidden` is often the real dramatic engine of the scene (an internal tension the character is fighting, not just an ST-only fact). Build the scene's tension around it rather than ignoring it because it's "not supposed to be known."
- **`priority`** — higher-priority goals should dominate the scene over lower-priority ones if multiple goals exist.

**Case study (learn from this):** An early draft of Silver Dollar's intro (a ghouled show horse) was written as a generic "uncanny animal at night" vignette without checking goals first. His actual goals showed a `quest_slug` tie to **Silver Bit**, a main quest where a routine riding lesson is bait for a Painted Desert ambush — a completely different, much more specific scene. The rewrite used the quest's actual premise and folded in a `hidden`-secrecy goal (restraint around a mortal bystander) as the scene's real tension. Always check goals before drafting; do not treat this step as optional for "minor" characters.

If the `npc_goals` query returns **zero rows** for the character, **STOP. Do not draft the scene.** A cinematic intro written with no goals to ground it is exactly how the Silver Dollar mistake happened — do not repeat it by proceeding anyway. Report back that goals are missing and who/what needs to write them first (the NPC goals pass) before any scene work resumes on that character. This is a hard gate, not a suggestion — no exceptions for characters that "seem simple."

---

## 🚫 **Keep Game Mechanics Oblique in Prose**

Cinematic intros are read as scenes, not character sheets. Never name a Trait, Discipline, Merit/Flaw, Path rating, or other mechanical term directly in the scene description, shot text, or VO — even when it's the most precise word available. Convey the same information through action, sensation, or behavior instead.

| Don't write | Write instead |
|---|---|
| "the Violent trait finally off the chain" | "whatever's usually kept leashed finally loose" |
| "a 5-Trait Animal Ghoul" | "a bonded animal retainer" |
| "hooves and teeth exactly where his sheet says he goes" | "hooves and teeth moving with a precision no barn animal earns honestly" |
| "her hidden goal to protect him" | "something in her that won't let him go, even now" |
| "his Auspex picks up on..." | "he notices what nobody else in the room does..." |

This restriction applies to the cinematic prose sections only (Opening Cutscene, Scene Card description, VO). **GM Notes, ST creative lock, and Reusing-as-a-PC-scene sections are ST-facing documentation, not in-scene prose** — mechanical terms are fine there when they add real clarity (e.g. "Presence and Dominate shape negotiation gravity" in a GM Notes block is appropriate; the same phrasing inside the Opening Cutscene is not).

---

## 🎭 **This Is a LARP, Not an FPS**

vbn-game resolves conflict through discrete challenge resolution — social contests, mental contests, negotiation, a resolved test at the table — not real-time positioning, cover mechanics, or twitch action. Any cinematic intro that includes a confrontation, standoff, or threat beat needs to make that resolution style legible, not just avoid contradicting it.

**Watch for scenes that accidentally read as action-game staging:**
- A tense approach or standoff that implies the player should be thinking about cover, sightlines, or reaction time, rather than what to say or offer.
- Escape beats framed around speed or physical evasion rather than social maneuvering, misdirection, or a resolved contest.
- Any GM Notes language that describes a confrontation in terms a shooter or stealth game would use ("chase," "firefight," "combat encounter") when the actual table resolution is a conversation and a roll.

**What to do instead:**
- Let tension come from stakes and dialogue, not positioning. A character avoiding violence should say so, or act in ways that make the preference for words over weapons explicit (Juan Delgado's "running down here just means being caught somewhere with worse lighting" is the model — it names the calculation instead of dramatizing a chase).
- In GM Notes, state plainly how the beat resolves at the table: a single social/mental test, an in-character negotiation, a contest — not staged like combat. If a scene has a clear non-violent resolution method, say so explicitly rather than assuming the ST will infer it.
- This doesn't mean tension or danger should be softened — a scene can still feel like real risk. It means the risk should read as "what happens if I say the wrong thing" rather than "what happens if I don't take cover in time."

---

## 📚 **Check Organizational & Religious Lore Before Depicting It**

If a scene involves an in-world organization, cult, faction ritual, or institution — not just a character — check for an existing reference doc before inventing generic flavor. Likely locations: `reference/Organizations/`, `reference/history/`, and any doc named in a character's biography or `npc_goals` notes.

**Case study:** An early draft of Amira Lamia's intro depicted her Wednesday Lilith-circle ritual as a generic candlelit gathering — no wrong details exactly, just invented rather than sourced. The actual chronicle has specific canon: `Organizations/Cult_of_Lilith_Phoenix.md` names Paris Giovanni as the cell's founder and effective High Priest, and real-world Bahari/Path of Lilith source material (*Chaining the Beast*, MET *Sabbat Guide*) specifies scarlet robes with black briar patterns, scars deliberately shown, and — explicitly — that this is **not** a BDSM-club aesthetic ("pain without enlightenment is a mere fact of biology"). None of that was wrong to invent generically, but it was less specific and less true than what already existed to check against.

This is the same failure mode as skipping goals or a quest design doc: writing something plausible instead of something sourced. If a reference doc exists, use it. If it doesn't, say so plainly in the scene's frontmatter or GM Notes rather than presenting invented detail as if it were canon.

**Supernatural afflictions and entities specifically:** if a scene depicts possession, infection, a curse, or any other supernatural condition affecting a character, check that entity's own character record's `custom_data` field (Supabase), not just its biography text — detection mechanics, perceptible tells, and mechanical rules are often stored there as structured data and are easy to miss if you only read the prose biography. A scene drafted without this check risks getting the entity's basic rules wrong (e.g. assuming a condition is undetectable to ordinary observers when the record specifies otherwise) — check before deciding how visible or subtle to make something.

---



## 🖋️ **Text Formatting & Structure**

Use a **hybrid screenplay / narrative format**, combining cinematic clarity with the lyrical, stylized narration that defines *vbn-game*.  

### **Document Sections**
1. `### ?? *Opening Cutscene: "Title"*` — scene name and mood indicator  
2. **[INT./EXT. – LOCATION – TIME]** — film-style scene heading  
3. **Cinematic Description** — 1–3 paragraphs of visual and sensory setup  
4. **Character Action & Dialogue** — formatted as in-screen captions or spoken lines  
5. **[CUT TO:], [FADE OUT:], [DISSOLVE:]** — transition markers  
6. Optional **Voice-Over (VO)** — italicized, indented, or captioned  
7. **Scene Card (GM / LARP Narration)** — plain-text version for table use  
8. **GM Notes** — Disciplines, hooks, emotional beats  

---

### **Text Styling Rules**

| Element | Style | Notes |
|----------|--------|-------|
| **Scene Headings** | `**[INT./EXT. LOCATION – TIME]**` | Always uppercase; bold for clarity. |
| **Dialogue / Quotes** | `> **Character:** "Line."` | Use blockquote + bold speaker name. |
| **Voice-Over (VO)** | `**[VO – Character]:** *"Line of narration."*` | Italics inside VO brackets. |
| **Actions & Descriptions** | Plain text | Keep sentences active, cinematic. |
| **Transitions** | `[CUT TO:]`, `[FADE OUT]`, etc. | Always bracketed and uppercase. |
| **Emphasis** | *Italics* for tone or sensory cues | e.g., *soft amber light*, *velvet hush*. |
| **End Cards** | Bold caps centered | Example: **VBN-GAME – CHAPTER ONE: THE PRINCE IS DEAD** |

---

## 🎨 **Visual & Color Palette**

**Overall Tone:** Neo-noir gothic — where the desert's warmth meets cold immortality.

| Element | Hex | Usage | Notes |
|----------|------|--------|------|
| **Deep Crimson** | `#7A1E1E` | Accents, blood tones, typography highlights | Emotional core color. |
| **Muted Gold** | `#B89B64` | Lighting, typography highlight, UI accent | "Old money" elegance. |
| **Ash Gray** | `#2F2F2F` | Backgrounds, shadows, neutral tone | Balances warm palette. |
| **Ivory White** | `#F5F2E7` | Text on dark backgrounds | Matches candlelight hue. |
| **Desert Amber** | `#C87B3E` | Warm light (Arizona, firelight) | Used for scene lighting and reflections. |
| **Noir Blue-Black** | `#0D0E10` | Primary shadow / night tone | For darkness, sky, interiors. |

---

### **Lighting Themes**
| Scene Type | Lighting Style | Notes |
|-------------|----------------|-------|
| **Camarilla Elysium** | Gold + shadow contrast | Decadence, restraint. |
| **Street / Desert Scenes** | Sodium orange + blue ambient | Urban decay meets mysticism. |
| **Toreador / Setite Locations** | Warm spotlights + soft lens bloom | Sensual, theatrical tone. |
| **Malkavian / Investigative** | Harsh contrast, flickering neon, cigarette smoke | Classic noir. |
| **Giovanni / Political** | Candlelight, marble reflections | Control and wealth motifs. |

---

## 🎧 **Sound & Score Direction**

| Layer | Description | Usage |
|--------|--------------|-------|
| **Ambient** | Environmental texture: wind, insects, murmured crowd | Always subtle, never silent. |
| **Music** | Slow jazz, string pads, faint choir | Reinforces emotional tempo. |
| **VO Tone** | Soft reverb, dry microphone mix | Sounds "close," like confession. |
| **SFX** | Diegetic realism — footsteps, glass, smoke | Minimal but sharp. |
| **Silence** | Use pauses for tension before lines or cuts. | "Air is the tension in the room." |

---

## 🧭 **Tone and Voice**

Every line of narration or dialogue should reflect one of the following tonal pillars:  
1. **Seduction** – beauty as weapon or invitation.  
2. **Deception** – layers of truth, masks, and political poise.  
3. **Decay** – the old world crumbling under modern neon.  
4. **Desert Isolation** – vast, quiet spaces echoing with memory.  
5. **Moral Irony** – Kindred who *want* to believe they're still human.

---

## 🕰️ **Timing Guidelines**

- **Runtime:** 30–60 seconds  
- **Average shot count:** 7–9  
- **Average line count:** 5–7 (including VO and dialogue)  
- **End beat:** Minimum 3-second fade to black before title card  
- **VO pacing:** 1 line every 6–8 seconds (allow for ambient visual time)  

---

## 🧩 **Scene Consistency Notes**

- All intros end with the **signature title card**:  
  ```
  [CUT TO BLACK]  
  **VBN-GAME – [Subtitle or Chapter Title]**
  ```  
- If the character is a PC ally or antagonist, include **one thematic sentence** foreshadowing their role (e.g., "He'd find the truth — or die twice trying.")
- Maintain a **realistic Phoenix geography**, even when stylized.  
- Avoid explicit supernatural displays unless subtle (Presence glances, Auspex intuition, etc.)  

---

## 🧠 **File Structure (Repo Recommendation)**

```
/references/
   ├── Cinematic Intros/
   │     ├── 00_Style_Guide.md
   │     ├── 01_EddyValiant_Intro.md
   │     ├── 02_CordeliaFairchild_Intro.md
   │     ├── 03_SarahHansen_Intro.md
   │     ├── 04_Kerry_Gangrel_Intro.md
   │     └── ...
```
