# dsh-advanced-patrol

Session-level, timer-driven LLM patrol for DeepSeek Harness (DSH). Each session picks a patrol preset and an interval; on every tick the model performs multi-turn tool operations.

## Presets

Four presets ship under `presets/`, one file each:

| Preset | File |
| --- | --- |
| standard | `presets/standard-patrol.md` |
| context review | `presets/context-review.md` |
| knowledge entry | `presets/knowledge-entry.md` |
| stuck rescue | `presets/stuck-rescue.md` |

Presets are resolved at runtime from `src/presets.js`; switch per session.

## Wiring

Bundle patch: `cordis.patch.yml`. Entry point `index.js` re-exports the host and client halves (`./src/host`, `./src/client`).

## Tests

```sh
npm test        # node --test test/*.test.js
```
