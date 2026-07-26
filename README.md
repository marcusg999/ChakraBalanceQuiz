# Chakra Balance Advisor

**37 questions to help determine which chakras may need attention and how to support their healthy functioning.**

🌐 **Live app:** https://marcusg999.github.io/ChakraBalanceQuiz/

---

## Features

- **Guided one-question-at-a-time flow** — a welcome screen, then each of the 37 questions on its own focused card instead of one long list of dropdowns
- **Tappable Likert answers** with keyboard support (press `1`–`5` to answer, `←`/`→` to move) and gentle auto-advance
- **Auto-saved progress** — answers and position are persisted to `localStorage`, so you can close the tab and resume where you left off
- **Per-chakra progress rail** — a seven-segment bar fills as you complete each energy centre's questions
- **Whole-system results** — an *energy overview* of all 7 chakras (balanced vs. needs-attention, with meters) followed by detailed cards for the centres that need attention: chakra symbol, energy level, description, signs of imbalance, and balancing practices
- **Meditative visual design** — ambient aurora background, glassmorphism cards, serif display type, and per-chakra colour accents
- **Dark & light themes** — automatically follows your OS preference; override with the ☀️/🌙 toggle (saved in `localStorage`)
- **Accessible & responsive** — radiogroup semantics, focus-visible states, `prefers-reduced-motion` support, safe-area aware, mobile-first
- **No dependencies** — a single self-contained `index.html`, no build step required

---

## Theming & Dark Mode

The app uses CSS custom properties (design tokens) for all colours, spacing, and typography. Two themes are defined:

| Token | Light | Dark |
|---|---|---|
| `--bg-base` | `#f4f1fb` | `#0b0916` |
| `--surface` | `rgba(255,255,255,0.72)` | `rgba(28,23,48,0.66)` |
| `--accent`  | `#7c3aed` | `#a78bfa` |
| `--text-primary` | `#241a3d` | `#f2eefb` |

Dark mode is applied via:
1. `@media (prefers-color-scheme: dark)` — respects OS/browser setting automatically.
2. `[data-theme="dark"]` / `[data-theme="light"]` on `<html>` — set by the in-app toggle, persisted via `localStorage`.

---

## Scoring Logic

Each question is mapped to the chakra it actually relates to **by theme** (using the original question numbering), rather than by contiguous position:

| Chakra | Questions |
|---|---|
| Root (Muladhara) | 1, 8, 19, 20, 26 |
| Sacral (Svadhisthana) | 2, 9, 22, 24, 30, 35 |
| Solar Plexus (Manipura) | 3, 13, 15, 25, 28, 29, 33 |
| Heart (Anahata) | 4, 10, 14, 21, 34 |
| Throat (Vishuddha) | 5, 17, 23 |
| Third Eye (Ajna) | 6, 12, 16, 18, 37 |
| Crown (Sahasrara) | 7, 11, 27, 31, 32, 36 |

Each answer is scored 1–5. A chakra's score is the **average of its mapped questions**; if that average is 3 or below, the chakra is shown in the results as needing attention. In the app, questions are **presented grouped by chakra** (Root → Crown) so the assessment flows through one energy centre at a time; the grouping does not affect scores.

---

## Running Locally

Just open `index.html` in any modern browser — no server or build step needed.

```bash
open index.html          # macOS
xdg-open index.html      # Linux
start index.html         # Windows
```
