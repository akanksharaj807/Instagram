# Vocabulary Master File — Progress Tracker

Source: `GRE_WORDS_TO_REFER_CLEANED.csv`
Total unique source words: **3202**
Family-consolidation applied (one form per word family).

## Legend
- Sense: **+** positive · **−** negative · **N** neutral

## Progress by letter (final)

| Letter | Kept | Source |
|---|---|---|
| A | 207 | 255 |
| B | 80 | 92 |
| C | 266 | 318 |
| D | 213 | 260 |
| E | 187 | 249 |
| F | 122 | 145 |
| G | 52 | 54 |
| H | 62 | 73 |
| I | 156 | 275 |
| J | 13 | 15 |
| K | 6 | 7 |
| L | 49 | 59 |
| M | 113 | 143 |
| N | 37 | 45 |
| O | 75 | 85 |
| P | 234 | 301 |
| Q | 17 | 21 |
| R | 151 | 190 |
| S | 257 | 313 |
| T | 76 | 94 |
| U | 84 | 92 |
| V | 55 | 75 |
| W | 30 | 34 |
| X | 1 | 1 |
| Y | 2 | 2 |
| Z | 3 | 4 |
| **Total** | **2548** | **3202** |

## Consolidation rule
For each word family sharing a common stem (e.g. `impulsive/impulsively/impulsiveness`), only one form is kept — preferring the shortest / adjective / verb base and dropping derived nouns (-ness, -ity), adverbs (-ly), and derived noun-of-action forms (-ion, -ment, -ance/-ence) when a base form exists.

Semantic-distinct families kept intact (each member has a different meaning): `generate/generic/generality`, `affect/affectation`, `content/contention`, `exhaust/exhaustive`, `exact/exacting`, `discern/discernible/discernment`, `canon/canonical/canonize`, `derive/derivative`, `loath/loathe`, `precede/precedent`, `precipitate/precipitous`, `prodigal/prodigious/prodigy`, `proprietary/propriety`, `success/successor/succor`, `supplant/supple/supplement/supplicate`, `malign/malignant`, `mass/massive`, `materialism/materialize`, `momentary/momentous`, `negligent/negligible`, `neutrality/neutralize`, `obviate/obvious`, `opportune/opportunistic`, `polar/polarize`, `ponder/ponderous`, `sever/severe`, `spare/sparse`, `stimulant/stimulate`, `subside/subsidize`, `temper/temperate/temporal`, `urban/urbane`, `venerable/venerate`, `violate/violent`.

## Output files
- One CSV per letter: `vocab/A.csv` … `vocab/Z.csv`
- Columns: `Word, Meaning, Sense, Sentence 1, Sentence 2, Sentence 3`
