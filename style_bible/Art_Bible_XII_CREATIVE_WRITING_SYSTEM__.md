# PART XII — CREATIVE WRITING SYSTEM
## (Full, Exhaustive Version)

## 1. Overview

The Creative Writing System (CWS) defines all rules for written narrative content in vbn-game — NPC biographies, personality profiles, timeline entries, relationship descriptions, background flavor, and voice-over scripts.

The CWS is not a separate creative layer. It is the **written expression of the same aesthetic manifesto** that governs portraits, cinematics, and architecture. Every field it produces is source material for the Styles Agent, the cinematic pipeline, portrait prompts, and player-facing game content.

This system must be referenced before writing or generating any narrative content.

---

## 2. Governing Aesthetic

All written content obeys the same five pillars defined in Part X:

1. **Gothic Noir** — shadow and elegance, beauty that decays
2. **Phoenix 1994** — desert heat, strip malls, sodium streetlights, pre-internet isolation
3. **Psychological Tension** — restraint over spectacle, menace over action
4. **Subtle Supernatural** — hints, never explosions; dread, never display
5. **Cinematic Quality** — every sentence should be shootable

### Written Equivalents of Visual Rules

| Visual Rule | Written Rule |
|---|---|
| No flat lighting | No flat exposition |
| No lens flares | No purple prose |
| No superhero poses | No melodrama |
| Slow, deliberate camera | Slow, deliberate revelation |
| Shallow depth of field | Focus on one emotional truth per paragraph |

---

## 3. Tonal Pillars

Every piece of written content must reflect at least one of these five tonal pillars (defined in the Cinematic Intro Guide and reinforced here):

1. **Seduction** — beauty as weapon or invitation
2. **Deception** — layers of truth, masks, political poise
3. **Decay** — the old world crumbling under modern neon
4. **Desert Isolation** — vast, quiet spaces echoing with memory
5. **Moral Irony** — Kindred who want to believe they're still human

### Forbidden Tones

- Comic relief (unless the character is explicitly written as darkly absurdist)
- Omniscient narration that explains motivations directly
- Heroic framing
- Modern slang or post-1994 cultural references
- Clinical or encyclopedic summaries

---

## 4. Voice Registers

The CWS uses four distinct voice registers depending on output type.

### 4.1 Tight Third-Person Limited
*Used for: `biography`, `appearance_detailed`, `haven_description`*

Stays close to the character's perspective without entering it completely. The narrator knows what the character knows, feels the weight of what they feel — but never explains.

> *She had been in Phoenix for eleven years. The desert had not softened her. Nothing had.*

Rules:
- Active verbs, short sentences under pressure
- Sensory detail anchored to place and time
- No backstory dumps — unfold chronologically or in fragments
- One emotional truth per paragraph maximum

---

### 4.2 Micro-Scene
*Used for: `timeline[]` entries, `backgroundDetails` narrative expansions*

Each entry is a moment, not a summary. Treat it as a deleted scene from a film — visible, atmospheric, unresolved.

> *1987. The last mortal winter. She stood outside the blood bank on Van Buren and watched the door for forty minutes before going in. She never went in.*

Rules:
- Lead with the year or context marker
- One image, one action, one emotional residue
- Never resolve what can be left open
- 2–4 sentences maximum per entry

---

### 4.3 Voice-Over (VO)
*Used for: `quotes[]`, cinematic VO lines, `personality.tagline`*

First-person, confessional. Sounds close — like the character is speaking into the dark, not performing.

> *"I've had three faces since the Embrace. The one before. The one I wear now. And the one I use when I need something."*

Rules:
- Italicized in game output
- Never longer than two sentences
- No direct address to the player or audience
- Reflects nature/demeanor tension — what they think vs. what they show

---

### 4.4 ST-Facing Prose
*Used for: `status.notes`, `relationships[]`, `coteries[].notes`*

Direct, unflinching. This is the Storyteller's intelligence briefing on the character. Efficient but not sterile — still carries tone.

> *Harlan trusts Mirela because she's never lied to him. She knows this and uses it carefully. He would follow her into the sun if she asked the right way.*

Rules:
- No game mechanical language (never "she has Presence 3")
- Behavior and motivation, not stats
- Specific — name names, reference places
- Can include hooks, warnings, or dramatic irony the character doesn't know

---

## 5. Field-by-Field Writing Standards

### 5.1 `biography`
- **Voice:** Tight Third-Person Limited
- **Length:** 3–6 paragraphs
- **Structure:** Mortal past → Embrace or Ghouling → Phoenix arrival → Current state
- **Anchor:** Always name one specific Phoenix location, one specific year, one sensory detail
- **Avoid:** Listing events. Every paragraph should contain one scene, not one summary.

### 5.2 `personality.tagline`
- **Voice:** VO
- **Length:** One sentence, maximum 15 words
- **Function:** The sentence that would appear on a title card under their name

### 5.3 `personality.narrative`
- **Voice:** ST-Facing Prose
- **Length:** 1–2 paragraphs
- **Function:** How they actually behave vs. how they present. Where nature and demeanor diverge.

### 5.4 `appearance` / `appearance_detailed`
- **Voice:** Tight Third-Person Limited
- **Anchor:** One clan visual motif. One 1994 Phoenix wardrobe detail. One telling physical habit.
- **Avoid:** Generic beauty descriptors. Be specific about what makes them *wrong* — what the eye catches and the mind can't quite name.

### 5.5 `timeline[]`
- **Voice:** Micro-Scene
- **Format:** `YEAR: [2–4 sentences]`
- **Required entries:** Mortal birth era, Embrace/ghouling, Phoenix arrival, one defining crisis
- **Optional:** Any moment that changed the character's path

### 5.6 `backgroundDetails`
- **Voice:** Micro-Scene or ST-Facing Prose depending on field
- **Resources:** What does wealth look like for them? Where does money live?
- **Allies:** Who are they, really? What's the cost of the relationship?
- **Retainers:** Name them. Give them one detail. They're people, not furniture.
- **Herd:** Where do they feed? What does the ritual feel like?
- **Status:** How is it held? What's the political fiction that maintains it?

### 5.7 `relationships[]`
- **Voice:** ST-Facing Prose
- **Format:** `{ "name": "", "tone": "", "history": "", "hook": "" }`
- **Tone options:** ally, rival, thrall, asset, threat, ghost, unknown
- **Hook:** One sentence that creates a scene if pursued

### 5.8 `quotes[]`
- **Voice:** VO
- **Minimum:** 3 quotes per character
- **Mix:** One for introduction, one for threat, one for vulnerability

### 5.9 `disciplines[].notes`
- **Voice:** Tight Third-Person Limited
- **Focus:** How does the discipline manifest aesthetically for *this* character?
- Reference Part II (Cinematic System) discipline visual rules
- Never describe the mechanical effect — describe what it looks like, sounds like, feels like in the room

### 5.10 `merits_flaws[].description`
- **Voice:** ST-Facing Prose
- **Function:** Behavioral consequence, not mechanical summary
- A flaw is not a stat — it's a pattern that keeps showing up

---

## 6. Clan Voice Guide

Each clan has a distinct written voice that should inflect (not dominate) all their narrative content.

| Clan | Voice Character | Sentence Rhythm | Signature Tension |
|---|---|---|---|
| **Toreador** | Lush, precise, performative | Long sentences that end sharply | Aesthete vs. predator |
| **Brujah** | Blunt, kinetic, ideologically loaded | Short. Punchy. Then longer when angry. | Passion vs. control |
| **Ventrue** | Measured, formal, never quite warm | Balanced clauses, careful word choice | Authority vs. loneliness |
| **Nosferatu** | Oblique, patient, information as currency | Fragments. Pauses implied. | Knowledge vs. isolation |
| **Malkavian** | Fractured, associative, occasionally lucid | Unpredictable — can be piercing or scattered | Prophecy vs. noise |
| **Tremere** | Precise, hierarchical, everything earned | Dense, layered, rarely casual | Power vs. debt |
| **Gangrel** | Sparse, territorial, time moves differently | Short. Long gaps implied. | Wildness vs. belonging |
| **Giovanni** | Courtly, warm, faintly wrong | Formal with familial undertones | Tradition vs. appetite |
| **Followers of Set** | Seductive, patient, always offering | Slow build, sensory, never direct | Gift vs. hook |
| **Tzimisce** | Clinical, aesthetic, alien patience | Long and cold, then suddenly intimate | Creation vs. disgust |
| **Ravnos** | Mobile, layered, always leaving | Quick, evasive, present-tense | Freedom vs. doom |
| **Assamite** | Economical, purposeful, honor-weighted | Minimal. Every word earns its place. | Duty vs. desire |
| **Malkavian** | See above | — | — |
| **Sabbat (any)** | Doctrine-inflected, pack-conscious | Varies by pack culture | Freedom vs. the Beast |

---

## 7. 1994 Phoenix Authenticity Rules

All written content must pass this filter:

### Must Include (where relevant)
- Desert heat as a physical presence, not background detail
- Pre-internet information economy — rumors travel slow, secrets hold longer
- Strip mall geography: Scottsdale, Tempe, Mesa, Chandler each have distinct character
- Real Phoenix institutions of the era (referenced obliquely): Sky Harbor, the Biltmore, Mill Avenue, Van Buren
- The specific emptiness of Phoenix nights — wide streets, few pedestrians, sodium orange overhead

### Must Never Include
- Cell phones, the internet, email as communication
- Post-1994 cultural references
- Gentrified or "modern Phoenix" geography
- Any acknowledgment of events after the chronicle's 1994 start date

### Metaplot Filter
The chronicle begins in 1994. The following have **not yet happened** and must not be referenced as current or anticipated:
- Gangrel leaving the Camarilla (1999)
- Giovanni Crusade events
- Any Revised-era metaplot developments post-1994

---

## 8. MET Language Rules

All mechanical references in written content must use Laws of the Night Revised terminology.

| Never Write | Always Write |
|---|---|
| "She rolls Manipulation + Subterfuge" | "She wins the Social Challenge" |
| "3 successes" | "she takes the test" / "the challenge falls her way" |
| "difficulty 7" | — (omit entirely) |
| "she has 4 dots of Presence" | "her Presence is considerable" |
| Dice, pools, difficulties | Static Challenges, Simple Tests, Traits |

Written content should never surface mechanical language. If mechanical context is needed for ST use, place it in `status.notes` clearly separated from narrative prose.

---

## 9. Integration with Other Art Bible Systems

### CWS → Cinematic (Part II)
Biography and timeline entries are source material for cinematic scripts. Every strong biography should contain at least one shootable scene.

### CWS → Portrait (Part I)
`appearance_detailed` feeds portrait prompt generation. The CWS description becomes the art director's brief.

### CWS → UI (Part V)
`personality.tagline` and short biography excerpts appear in character viewer modals. CWS must produce both full and truncated versions.

### CWS → Marketing (Part VII)
Quotes and taglines are marketing assets. Every character needs at least one quote suitable for a title card or chapter reveal.

---

## 10. Negative Writing Rules

Never allow the following in any vbn-game narrative content:

- Exposition that explains what the character is feeling directly
- Backstory delivered as biography summary ("She was born in 1923 and later became...")
- Mechanical language in flavor text
- Anachronistic references
- Heroic arcs or redemption narratives (unless earned through play)
- Purple prose (beauty for its own sake, untethered from character or place)
- Modern sensibility projected onto Kindred who predate it
- Comedy that breaks gothic tone
- Any framing that makes the supernatural mundane

---

## 11. Master Writing Prompt Prefix

When using AI to generate content under this system, all prompts must include:

```
vbn-game Creative Writing System — 1994 Phoenix, Gothic Noir.
Voice: [register from Section 4]
Clan: [clan name — apply voice guide from Section 6]
Field: [target field name]
Tone pillar: [one of: Seduction / Deception / Decay / Desert Isolation / Moral Irony]
MET system: Laws of the Night Revised. No dice language.
Era: 1994. Pre-internet. Desert Southwest.
```

### Mandatory Negative Block
```
(no dice rolls, no dot ratings, no success counts, no modern references,
no internet/cell phones, no melodrama, no direct emotional exposition,
no post-1994 metaplot, no heroic framing, no purple prose)
```

---

## 12. Integration with Part X

Part XII Creative Writing System is governed by the Unified Aesthetic Manifesto (Part X, Section 5).

In any conflict between creative writing impulse and the manifesto:

**The manifesto overrides.**

Written content that contradicts the visual aesthetic — in tone, era, or supernatural register — is rejected and rewritten.

---
