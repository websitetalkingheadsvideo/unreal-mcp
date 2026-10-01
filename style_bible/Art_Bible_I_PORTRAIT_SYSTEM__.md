# PART I — PORTRAIT SYSTEM  
## (Full, Exhaustive Version)

## 1. Overview  
The vbn-game Portrait System defines all rules, aesthetics, camera standards, lighting setups, resolutions, clan-specific motifs, and emotional tone for 1024×1024 character portraits. These portraits appear in the vbn-game website admin UI, character viewer modals, story events, and marketing materials. Portraits must visually align with the gothic–noir, Phoenix 1994 aesthetic of the entire project.

### Portrait cinematic charter (prepend first)

Portrait pipelines often differ by tool (YAML blocks vs prose vs OpenAI revised prompts). That structural variance shifts **default composition** (poster symmetry, splash-art posing, illustration staging). To keep **shot grammar** aligned across backends, **every positive portrait prompt MUST begin with this two-sentence block** before subject, wardrobe, lighting hexes, or environment clauses — unless another rule explicitly overrides framing (e.g. non-portrait deliverables):

> Valley by Night — single grounded photoreal **film still**, neo-noir **Phoenix 1994**, low-saturation desert-modern grit; **one coherent cinematic moment**, natural blocking and lens-realistic framing. **Do not** use poster/key-art staging, symmetrical vanity portraits, splash-art hero poses, illustration layouts, or glamour-editorial cover framing.

Optional negative reinforcement (append to portrait negatives when the model drifts): `poster composition, key art, splash art, symmetrical portrait, magazine cover layout, illustration layout, vanity posing`.

## 2. Resolution & Aspect Ratio  
- **Resolution:** 1024×1024  
- **Aspect Ratio:** 1:1  
- Portraits must remain square for UI consistency.  

## 3. Lighting Philosophy  
Portraits use controlled, noir-inspired lighting:  
- Key light at 35–45°  
- Soft rim light from upper-right  
- Warm/candlelight or cold/moonlight palette  
- Shadows must retain detail  
- No harsh digital specular  

## 4. Camera & Composition  
- Camera height: eye-level  
- Focal length: **50mm** or **85mm**  
- Framing: head + upper torso  
- Eyes must be visible and emotional anchors  
- Background: blurred noir environment or solid textured  

## 5. Color Palette  
Matches UI and cinematic systems:  
- Gothic Black `#0d0606`  
- Dusk Brown-Black `#1a0f0f`  
- Blood Red `#8B0000`  
- Parchment Light `#f5e6d3`  
- Muted Gold `#d4b06d`  
- Teal Moonlight `#0B3C49`  

## 6. Emotional Tone  
Portraits must convey:  
- restrained emotion  
- hidden danger  
- noir tension  
- introspection  
- slow-burning menace  

Never show:  
- exaggerated cartoon emotion  
- bright smiles  
- comedic expressions  

## 7. Clan Motifs  
Each Clan receives subtle visual cues:

### Toreador  
- soft bloom  
- velvet textures  
- warm candlelight  

### Brujah  
- cracked concrete textures  
- warm sodium lighting  
- tougher shadows  

### Gangrel  
- desert moonlight  
- earthy tones  
- slight feral hints (not literal)  

### Nosferatu  
- harsh industrial rim  
- muted palette  
- shadow concealment  

### Malkavian  
- fractured symmetry  
- violet edge light  
- subtle distortion  

### Ventrue  
- marble & gold accents  
- businesslike demeanor  
- cold-blue fill lighting  

### Giovanni  
- grayscale candlelight  
- Italian classic motifs  

### Setite  
- red velvet  
- gold serpents  
- incense haze  

## 8. Technical Rules  
- PNG or WEBP  
- No compression artifacts  
- Noise subtle and filmic  

## 9. Prompt Templates  
**Positive Prompt:**  
(omitted here for brevity, full expansions stored in 01b)

**Negative Prompt:**  
(omitted here, stored in 01b)

## 10. Example Outputs  
(Described in prompt guides)

---

---
