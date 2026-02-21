# Voice Library — Voice Governance

> The authoritative source for character voice, tone, and identity across Valet Studio and related projects.  
> This repo contains no application logic. It is voice infrastructure only.

---

## Authority

This repo governs all generated output.

- If application output conflicts with this repo, **this repo wins.**
- Characters never become preachy, partisan, or cruel.
- Voice consistency across time is a hard constraint, not a preference.

---

## Why This Exists

LLM outputs drift. Characters flatten. Tone gets averaged toward generic. This repo exists to prevent that.

It preserves each character's voice by keeping the creative DNA separate from application code. When LLM integration begins (Phase 1), this repo's files are used as system-level conditioning material — not suggestions, but constraints.

This repo serves four purposes:

1. Preserve each character's voice across time
2. Provide calibration material for LLM integration
3. Prevent tonal drift
4. Separate creative DNA from application code

---

## Repository Structure

```
voice-library/
  README.md            ← this file
  bible/               ← canonical voice rules and identity per character
  anchors/             ← lines that feel exactly right (positive calibration)
  drift/               ← lines that feel wrong (negative calibration)
  calibration/         ← tone check protocols and test prompts
  corpus/              ← raw writing samples used for signal extraction
  experiments/         ← exploratory tone work
  meta/                ← decision log and governance history
```

---

## Characters

### The Valet

**Archetype:** Trickster-sage in scrubs. Diagnoses epistemic architecture. Calm, precise, faintly disappointed.

| File | Purpose |
|------|---------|
| `bible/voice_bible_v1.md` | Canonical identity and rules |
| `anchors/anchor_lines.txt` | Lines that feel exactly right |
| `drift/drift_examples.txt` | Lines that feel wrong |
| `calibration/tone_self_check_prompt.md` | Calibration protocol |

---

### The Perimeter Walker

**Archetype:** The man who walks the edge without falling. Speaks in visceral, sensory metaphors. Morally intact. Controlled danger.

| File | Purpose |
|------|---------|
| `bible/perimeter_walker_v1.md` | Canonical identity and rules |
| `anchors/perimeter_walker_anchor_lines.txt` | Lines that feel exactly right |
| `drift/perimeter_walker_drift_examples.txt` | Lines that feel wrong |
| `calibration/perimeter_walker_tone_check.md` | Calibration protocol |

---

## Phase 1 LLM Integration

When integrating a character into an LLM, provide the following files as system-level conditioning material:

```
/bible/<character>_v1.md
/anchors/<character>_anchor_lines.txt
/calibration/<character>_tone_check.md
```

These files define the character. The `anchors/` files tell the model what right sounds like. The `calibration/` files let you test whether the model is in voice before going live.

---

## Adding a New Character

1. Create `bible/<name>_v1.md` — define archetype, rules, what the character is and is not
2. Create `anchors/<name>_anchor_lines.txt` — collect lines that feel exactly right
3. Create `drift/<name>_drift_examples.txt` — collect lines that feel wrong
4. Create `calibration/<name>_tone_check.md` — write a calibration prompt
5. Add the character to this README under **Characters**
6. Log the decision in `meta/`

---

## Relationship to Valet Studio

This repo is a dependency of <a href="https://github.com/Swixixle/Valet">`Valet`</a>, not the other way around. Valet Studio's pipeline defers to this repo for all tone and character decisions. Changes here propagate to application behavior.

---

## License

Private. All rights reserved.
