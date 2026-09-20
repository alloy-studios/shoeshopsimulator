# SOLE & CO. — Update Changelog

Addressing two pieces of playtest feedback: **(1) it is too hard**, and **(2) the shoes
look old, not tuff, and all identical.**

---

## 1. Difficulty

The root cause was an economy bug, not a tuning preference. Wholesale asks averaged
~0.93× a shoe's value and customer offers averaged ~0.94×, so the *average* trade lost
money before rent was even deducted.

### Numbers changed

| Thing | Before | After |
|---|---|---|
| Starting cash | $1,500 | **$2,400** |
| Display slots | 8 | **10** |
| Starting stock | 3 pairs @ 0.70× value | **5 pairs @ 0.55× value** |
| Wholesale ask | 0.55–1.30× value | **0.42–0.95×** (20% chance of a 0.30–0.44× steal) |
| Offer multiplier (meh → love) | 0.74 / 0.88 / 1.00 / 1.14 | **0.86 / 1.02 / 1.20 / 1.38** |
| Customer budget | $90–180 | **$170–330** (22% chance of a 2.6× whale) |
| Patience | 13s + rep | **24s + rep** |
| Shows per customer | 3 | **4** |
| Haggle success | 50% + rep | **62% + rep** |
| Shoppers per day | 4 + rep | **5 + rep** |
| Rent | $130 + $14/day | **$95 + $8/day** |
| Workshop jobs per day | 2 | **3** |
| Clean / Restore / Custom | $25 / $90 / $170 | **$20 / $70 / $140** |
| Trend bonus | +22–55% cat, +15–35% colourway | **+34–75% cat, +22–50% colourway** |
| Upgrade prices | $800–1,500 | **$650–1,250** |
| Rep per profitable sale | +0.10 | **+0.14** |
| Rep lost when a shopper leaves | −0.05 | **−0.03** |

### Upgrades buffed

- **Neon Window Sign** — +3 customers/day (was +2)
- **Restoration Bench** — +2 workshop jobs/day (was +1)
- **Social Campaign** — +15% on every offer (was +12%)

### Verification

Simulated 2,800 flips. A player who buys at ≤0.75× value and sells to a matching
customer now clears **~173% margin**, versus roughly break-even before.

---

## 2. Shoe visuals

### New models — 9 → 12

- **Air Legend 1 Mid** — built off the Jordan 1 reference photo
- **Varsity Dunk Low**
- **Coastal Waffle 78**
- **Summit Trail GTX**

### Six sole architectures (was one shared sole)

Each with its own outsole tread pattern:

| Style | Tread | Models |
|---|---|---|
| `cup` | Flat sidewall, pivot circle, herringbone | AJ1, Dunk, Force, Shelltoe |
| `vulc` | Thin, foxing tape, fine gum ribs | Old Skool, Canvas Hi |
| `air` | Split forefoot/heel pods, visible air window | Max 90 |
| `boost` | Thick speckled foam, heel cage | Streak 350 |
| `stack` | Layered, flared, tread blocks | Monolith Dad, Trail GTX |
| `wedge` | Diagonal wedge line | 574, Waffle 78 |

### Silhouette fixes

- **Heel line — the big "they all look identical" tell.** The heel top sat at ~88% of
  collar height on *every* model, rounding every back into the same pod shape. Now
  derived per model at 60–76%.
- Killed the thick stroked collar band that read as a roll bar bolted to the back of
  every shoe.
- The ankle opening is now a real **cut** — a closed dark band generated from the rim
  curve with a padded lip over it — instead of a floating line.
- Added a heel-counter seam to break up the rear panel.
- Per-model toe bluntness (`toeK` 32–52), shoe length, collar height, and eyelet count
  (4–7 rows).
- Fixed the toe "beak" — toe spring was pushing the midsole out ahead of the upper.
- Slimmed the outsole, which was eating the midsole and making every shoe a black brick.
- De-boated the chunky/boost soles, which had grown to half the shoe.
- The sock runner (Streak 350) had no laces **and** no tongue, so it rendered as a blob.
  Added a knit cuff and midfoot cage lines.

### Colour

- **15 → 17 colourways**, rebuilt for contrast and modern names: Panda, Chicago, Bred
  Toe, UNC Blue, Royal Toe, Volt Strike, Infrared, Grape Ice, Shattered Board, Pine
  Green, Laser Pink, Cyber Sail, Gold Trophy, and more.
- Fixed a colour-role collision where rubber bumpers and shell toes were painted with
  the third accent colour — producing orange toe bumpers on a Converse. Rubber now
  always takes the midsole colour.
- Retuned 5 washed-out colourways that were reducing shoes to single-tone blobs.
- Dropped the glossy gradient sweep. Flat vector reads more modern than wet plastic.
- Bumped internal line weights so panels read as panels.
- Cleaner white studio background on cards, replacing the cream.

### Tried and reverted

Rendering the full pair (a second shoe set behind the first). At any readable offset it
looked like a lump growing out of the heel rather than a second shoe.

---

## Known limitation

At large scale these read as good vector illustrations, not photoreal sneakers. After
seven passes, hand-tuning bezier curves without references hit diminishing returns.

The one thing that measurably worked was the Jordan 1 reference photo — measuring
against it corrected proportions that three prior passes had guessed wrong.

**Next step:** side-view photos of the 3–4 models that matter most, and those get
rebuilt against real measurements the same way.
