# Voice Library — Voice Governance

This repository governs the tone and character of voices developed for Valet Studio and related projects.

## Authority

- This repo is authoritative over any generated output.
- If application output conflicts with this repo, **this repo wins.**
- The character never becomes preachy, partisan, or cruel.

## Architectural Foundation

This repository exists to:

1. Preserve each character's voice across time.
2. Provide calibration material for LLM integration (Phase 1).
3. Prevent tonal drift.
4. Separate creative DNA from application code.

This repo contains **no application logic**. It is voice infrastructure only.

## Characters

### The Valet

Archetype: Trickster-sage in scrubs. Diagnoses epistemic architecture. Calm, precise, faintly disappointed.

Governance files:
- `bible/voice_bible_v1.md`
- `anchors/anchor_lines.txt`
- `drift/drift_examples.txt`
- `calibration/tone_self_check_prompt.md`

### The Perimeter Walker

Archetype: The man who walks the edge without falling. Speaks in visceral, sensory metaphors. Morally intact. Controlled danger.

Governance files:
- `bible/perimeter_walker_v1.md`
- `anchors/perimeter_walker_anchor_lines.txt`
- `drift/perimeter_walker_drift_examples.txt`
- `calibration/perimeter_walker_tone_check.md`

## Structure

```
voice-library/
  README.md          ← this file
  corpus/            ← raw writing samples for signal extraction
  anchors/           ← lines that feel exactly like the character
  drift/             ← lines that feel wrong (calibration negative)
  bible/             ← canonical voice rules and identity
  calibration/       ← calibration protocols and test material
  experiments/       ← exploratory tone work
  meta/              ← decision log and governance history
```

## Phase 1 LLM Integration

When Phase 1 LLM integration begins, the following are used as system-level conditioning material per character:

- `/bible/<character>_v1.md`
- `/anchors/<character>_anchor_lines.txt`
- `/calibration/<character>_tone_check.md`
