# Voice Library — Valet Studio Voice Governance

This repository governs the tone and character of *Valet Studio*.

## Authority

- This repo is authoritative over any generated output.
- If application output conflicts with this repo, **this repo wins.**
- The clinical recommendation is the highest protected output.
- The differential diagnosis must always exist.
- The character never becomes preachy, partisan, or cruel.

## Architectural Foundation

This repository is built on the Master Spec as its architectural foundation. It exists to:

1. Preserve the Valet's voice across time.
2. Provide calibration material for LLM integration (Phase 1).
3. Prevent tonal drift.
4. Protect the clinical recommendation from flattening.
5. Separate creative DNA from application code.

This repo contains **no application logic**. It is voice infrastructure only.

## Structure

```
voice-library/
  README.md          ← this file
  corpus/            ← raw writing samples for signal extraction
  anchors/           ← lines that feel exactly like The Valet
  drift/             ← lines that feel wrong (calibration negative)
  bible/             ← canonical voice rules and identity
  calibration/       ← calibration protocols and test material
  experiments/       ← exploratory tone work
  meta/              ← decision log and governance history
```

## Phase 1 LLM Integration

When Phase 1 LLM integration begins:

- `/bible/voice_bible_vX.md`
- `/anchors/anchor_lines.txt`
- `/calibration/`

will be used as system-level conditioning material.
