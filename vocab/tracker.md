# Vocabulary Master File — Progress Tracker

Source: `GRE_WORDS_TO_REFER_CLEANED.csv`
Total unique source words: **3202**
Family-consolidation applied (one form per word family).

## Legend
- Sense: **+** positive · **−** negative · **N** neutral

## Progress by letter (after consolidation)

| Letter | Kept | Source | Notes |
|---|---|---|---|
| A | 207 | 255 | consolidated (2 passes) |
| B | 80 | 92 | consolidated (2 passes) |
| C | 266 | 318 | consolidated (2 passes) |
| D | 213 | 260 | consolidated (2 passes) |
| E | 187 | 249 | consolidated (2 passes) |
| F | 122 | 145 | consolidated (2 passes) |
| G | 52 | 54 | consolidated (2 passes) |
| H | 62 | 73 | consolidated (2 passes) |
| I | 156 | 275 | user-curated + consolidated |
| J | 13 | 15 | consolidated (2 passes) |
| K | 6 | 7 | consolidated (2 passes) |
| L | 49 | 59 | consolidated (2 passes) |
| M | 113 | 143 | consolidated |
| N | 37 | 45 | consolidated |
| O | 75 | 85 | consolidated |
| P | 234 | 301 | consolidated |
| Q | 17 | 21 | consolidated |
| R | 151 | 190 | consolidated |
| S | 257 | 313 | consolidated |
| T | — | 94 | pending |
| U | — | 92 | pending |
| V | — | 75 | pending |
| W | — | 34 | pending |
| X | — | 1 | pending |
| Y | — | 2 | pending |
| Z | — | 4 | pending |
| **Kept** | **2297** | **3202** | 72% covered so far |

## Consolidation rule
For each word family sharing a Porter-stemmed root (e.g. `impulsive/impulsively/impulsiveness`), only one form is kept — preferring the shortest / adjective / verb base and dropping derived nouns (-ness, -ity), adverbs (-ly), and derived noun-of-action forms (-ion, -ment, -ance/-ence) when a base form exists.

Semantic-distinct families kept intact: `generate/generic/generality`, `affect/affectation`, `content/contention`, `exhaust/exhaustive`, `exact/exacting`, `discern/discernible/discernment`, `canon/canonical/canonize`, `deliberate/deliberation`, `derivative/derive`, `loath/loathe`.

## Output files
- One CSV per letter: `vocab/A.csv` … `vocab/L.csv`
- Columns: `Word, Meaning, Sense, Sentence 1, Sentence 2, Sentence 3`
