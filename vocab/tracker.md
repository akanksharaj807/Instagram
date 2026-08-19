# Vocabulary Master File — Progress Tracker

Source: `GRE_WORDS_TO_REFER_CLEANED.csv`
Total unique source words: **3202**
Family-consolidation applied (one form per word family).

## Legend
- Sense: **+** positive · **−** negative · **N** neutral

## Progress by letter (after consolidation)

| Letter | Kept | Source | Notes |
|---|---|---|---|
| A | 216 | 255 | consolidated |
| B | 82 | 92 | consolidated |
| C | 276 | 318 | consolidated |
| D | 219 | 260 | consolidated |
| E | 197 | 249 | consolidated |
| F | 123 | 145 | consolidated |
| G | 52 | 54 | consolidated |
| H | 65 | 73 | consolidated |
| I | 156 | 275 | user-curated + consolidated |
| J | 14 | 15 | consolidated |
| K | 6 | 7 | consolidated |
| L | 53 | 59 | consolidated |
| M | — | 143 | pending |
| N | — | 45 | pending |
| O | — | 85 | pending |
| P | — | 301 | pending |
| Q | — | 21 | pending |
| R | — | 190 | pending |
| S | — | 313 | pending |
| T | — | 94 | pending |
| U | — | 92 | pending |
| V | — | 75 | pending |
| W | — | 34 | pending |
| X | — | 1 | pending |
| Y | — | 2 | pending |
| Z | — | 4 | pending |
| **Kept** | **1459** | **3202** | 46% covered so far |

## Consolidation rule
For each word family sharing a Porter-stemmed root (e.g. `impulsive/impulsively/impulsiveness`), only one form is kept — preferring the shortest / adjective / verb base and dropping derived nouns (-ness, -ity), adverbs (-ly), and derived noun-of-action forms (-ion, -ment, -ance/-ence) when a base form exists.

Semantic-distinct families kept intact: `generate/generic/generality`, `affect/affectation`, `content/contention`, `exhaust/exhaustive`, `exact/exacting`, `discern/discernible/discernment`, `canon/canonical/canonize`, `deliberate/deliberation`, `derivative/derive`, `loath/loathe`.

## Output files
- One CSV per letter: `vocab/A.csv` … `vocab/L.csv`
- Columns: `Word, Meaning, Sense, Sentence 1, Sentence 2, Sentence 3`
