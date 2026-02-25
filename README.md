# Chakra Balance Advisor

**37 questions to help determine which chakras may need attention and how to support their healthy functioning.**

🌐 **Live app:** https://marcusg999.github.io/ChakraBalanceQuiz/

---

## Features

- **37-question quiz** mapping to all 7 chakras (Root → Crown)
- **Animated result cards** with pulsing chakra symbols, a score bar, chakra description, signs of imbalance, and balancing practices
- **Dark mode** — automatically follows your OS preference; override with the ☀️/🌙 toggle in the header (preference is saved in `localStorage`)
- **Progress indicator** — tracks how many questions you've answered in real time
- **Mobile-first responsive design** — safe-area aware, works on phones, tablets, and desktops
- **No dependencies** — pure HTML/CSS/JavaScript, no build step required

---

## Theming & Dark Mode

The app uses CSS custom properties (design tokens) for all colours, spacing, and typography. Two themes are defined:

| Token | Light | Dark |
|---|---|---|
| `--bg-page` | `#f0edf8` | `#0f0d1a` |
| `--bg-card` | `#ffffff` | `#1c1830` |
| `--accent`  | `#7c3aed` | `#a78bfa` |
| `--text-primary` | `#1a1030` | `#f0edf8` |

Dark mode is applied via:
1. `@media (prefers-color-scheme: dark)` — respects OS/browser setting automatically.
2. `[data-theme="dark"]` / `[data-theme="light"]` on `<html>` — set by the in-app toggle, persisted via `localStorage`.

---

## Scoring Logic

Questions are grouped into chakra buckets (preserving the original logic):

| Chakra | Questions |
|---|---|
| Root (Muladhara) | 1–5 |
| Sacral (Svadhisthana) | 6–10 |
| Solar Plexus (Manipura) | 11–15 |
| Heart (Anahata) | 16–21 |
| Throat (Vishuddha) | 22–26 |
| Third Eye (Ajna) | 27–32 |
| Crown (Sahasrara) | 33–37 |

Each answer is scored 1–5. If a chakra's average score ≤ 3 it is shown in the results as needing attention.

---

## Running Locally

Just open `index.html` in any modern browser — no server or build step needed.

```bash
open index.html          # macOS
xdg-open index.html      # Linux
start index.html         # Windows
```
