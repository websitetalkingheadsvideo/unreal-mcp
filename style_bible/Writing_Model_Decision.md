# Writing model decision — local creative generation

**Decision (2026-07-28):** `gemma2:27b` is the default local model for **creative scene
writing** (cinematic intros, teasers, coterie/meeting scenes). Wired as `WRITING_MODEL`
in the LCARS scene pipeline (`C:\hermes\lcars_server.py`).

**Why this note exists:** so we don't re-run the model bake-off every few months.
Below is what was actually tested and why the others lost.

## Hardware context
- Machine **AMBER**, NVIDIA **RTX 3060, 12 GB VRAM**, ~32 GB system RAM.
- Practical ceiling: models up to ~13B run fully on-GPU (fast); ~22–32B run with
  partial RAM offload (slow but usable); **70B is a mirage** (~75% offloads to RAM →
  10–40 min per generation at a quality-degrading quant). Don't chase 70B on this card.

## Bake-off — same character (Basher), same prompt, same canon
| Model | Time/intro | Result |
|---|---|---|
| **gemma2:27b** | ~9 min | ✅ **Winner.** Full scene, clearly the best prose — sensory, specific, real dialogue voice, closest to the hand-crafted bar. |
| mistral-nemo (12B) | ~2.5 min | ✅ Full scene, competent but generic prose and flat dialogue. Fine fast fallback. |
| Rocinante-12B (creative Nemo tune) | ~12 min | ❌ Broken as pulled — wrong chat template in Ollama; answered with a Python tutorial. |
| Cydonia-24B (creative Mistral-Small tune) | timed out (20 min) | ❌ Too big for 12 GB; can't finish a scene. Not viable on this card. |

Prose gap example (same beat):
- nemo: *"built like a Mack truck… 'Another night, another dollar.'"*
- gemma2: *"Scars crisscross his knuckles, testaments to years spent delivering 'persuasion'… 'Just enough to make 'em think twice about crossing us again.'"*

## Caveats / open items
- **Speed:** gemma2:27b ≈ 9 min/intro (partial offload). Fine for unattended/overnight
  batches; use `mistral-nemo` when speed matters.
- **"Safe" model risk:** Gemma has guardrails and can soften the darkest WoD content
  (feeding, torture, cult rites). Handled Basher's violence fine; **test on genuinely
  dark material before trusting it there** (Lilith-cult / Bahari, Sabbat rites, etc.).
- If a future card has ≥24 GB VRAM, re-test **Cydonia-24B** (uncensored, made for dark
  fiction) — it's the likely winner once it can actually run.
- Rocinante could be salvaged with a corrected Modelfile/template, but gemma2 already
  wins on prose, so not worth it now.

## Pipeline notes
- Canon accuracy comes from **Supabase injection** (character clan/disciplines/merits),
  not the model — verified (Basher's disciplines matched his sheet). A better model buys
  **prose**, not correctness.
- House-voice constraints from the **vbn-creative-writing** skill / Art Bible XII (era
  lock 1994, no dice/mechanical language, show-don't-tell, disciplines-as-experience,
  metaplot filter) are now folded into the scene prompt (`HOUSE_VOICE_CONSTRAINTS`).
