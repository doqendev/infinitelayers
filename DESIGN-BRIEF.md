# Infinite Layers — design brief

Ground-up redesign of the Infinite Layers storefront (Shopify). This brief is self-contained;
paste it into Claude Design as the starting context.

---

## What we sell

Fan merchandise across two source libraries:

- **Music** — bands and artists
- **Screen** — TV shows and films

Product types are identical across both: t-shirts, hoodies, keychains, posters.

**The differentiator is personalization.** Customers customize designs — band logos, character
art, custom text — and see a live preview before ordering. This is the core of the business,
not a side feature.

## Brand position

Infinite Layers is **a customization studio with two source libraries**, not a music store
bolted to a movie store. Music and screen are *material*, not identity.

The name works on two levels, and both should read in the design:

- **Layers of customization** — the literal layers of a personalized design
- **Layers of themes** — the breadth of fandoms covered

Working tagline direction: *every fandom, made personal.*

### The positioning tension — read this before designing

The store serves two modes that pull in opposite directions:

|  | Fan (self-purchase) | Gift buyer |
|---|---|---|
| Enters by | Fandom — knows what they want | Recipient — knows the person, not the catalogue |
| Wants | Depth, authenticity, accuracy | Discovery, suggestions, reassurance |
| Filters by | IP, product type | Budget, occasion, recipient |
| Value | Repeat, high LTV, word of mouth | Seasonal spikes, higher AOV |
| Fatal flaw | Impenetrable to outsiders | Reads as generic and cheap |

**Resolution: look like a fan store, navigate like a gift shop.**

Fan-credible art direction is the default. Gifting is surfaced as a parallel entry path and a
seasonal mode — never as the brand's face. This is not a compromise: the gift buyer is buying
for someone who knows the difference, so if the store reads generic they worry the recipient
will think the gift is cheap. **Fan credibility is what makes the gift feel good to give.**

Band-merch audiences are unusually sensitive to authenticity. Nothing should look like a
generic gift shop.

---

## Information architecture — decided

**One storefront. Mixed catalogue. No category split, and no choice at the front door.**

Music and screen fans overlap heavily, and gift buyers shop for a whole person — "my brother,
who's into metal and Star Wars" is one shopping trip here and two dead ends on a split site.
A segmented store would never put the Star Wars keychain beside the Metallica one, which is
exactly the moment that converts.

Decisions:

- **Category (Music / Screen) is a lens** — a filter and a visual accent. Never a wall, never a door.
- **The homepage leads with fandom tiles, not category tiles.** Nobody searches "music merch";
  they search "Metallica hoodie." The fandom tiles carry the SEO and the intent.
- **The gift finder is a parallel entry path** that deliberately spans both categories.
- **Gift mode is seasonal-switchable**, not permanent — the homepage flips gift-forward for Q4
  and back out again without a redesign.

---

## Art direction — the crop-ratio system

This is the key mechanic. **Vary texture and proportion, never layout.**

Grid, spacing scale, components, and buttons stay identical across both categories. Only three
things change:

|  | Music | Screen |
|---|---|---|
| **Crop ratio** | 1:1 square — vinyl sleeve | 2.39:1 widescreen, letterboxed |
| **Texture** | Halftone, grain, screenprint, torn edge | Film-still framing, deeper colour grade |
| **Type accent** | Condensed / compressed, gig-poster DNA | Wide sans or title-card serif |

The aspect ratio does the work: square reads as *record*, widescreen reads as *film*. It's
semantic rather than decorative, legible without a label, and costs nothing structurally.

This solves the main risk of a mixed catalogue — that the grid reads as *random* rather than
*curated*. With the ratio system, a mixed scroll has visual rhythm and looks deliberate.
Without it, mixing looks like an unsorted inventory dump.

---

## Pages to design

In priority order.

1. **Homepage — three variants** at different split strengths: fully unified grid, subtly
   accented, and strongly split. Seeing them side by side settles the direction.

2. **Personalization PDP — in both skins.** Highest-value page in the store and the hardest to
   build. The preview is canvas-based and updates live as the customer types or picks a variant.
   Do not skip this in favour of easier pages.

3. **Collection page, twice** — once for a music IP, once for a screen IP. Same layout, different
   accent. This is the real test of whether the crop-ratio system holds.

4. **Gift finder** — browse by recipient, budget, and occasion, with a deliberately mixed grid.
   This is the page that proves the mixed model visually.

5. **Gift guide / curated collection** — mixed IPs under one theme ("for the music-and-movies
   obsessive"). Maximally heterogeneous content; tests the ratio rhythm under stress.

6. **Layered gift bundle builder** — stack a tee + keychain + poster for one fandom into a single
   gift. The name made literal, and the clearest single expression of the brand.

---

## Constraints

- **Shopify storefront.** The stack (Hydrogen/React vs Liquid theme) is not yet chosen — the
  design should not depend on exotic runtime behaviour that only one option supports.
- **Multi-language, multi-market.** The current store ships 55 locale files with market contexts
  for Spain, France, Australia, Canada, and international. Layouts must survive text expansion
  and varying currency formats.
- **The personalization preview is live and canvas-based** — it re-renders as the customer types
  or changes variant. Design it as an interactive surface, not a static product image.
- **Q4 gifting seasonality.** Gift-forward merchandising has to be switchable without a redesign.
- Scope items that a pure merch store doesn't need: gift wrapping, gift notes, delivery-by date,
  gift cards.

---

## Design context to import first

Do this before generating anything — quality depends far more on context than on prompt wording.

- Screenshots of the current Infinite Layers site, **especially the personalization PDP**
- Brand assets: logo, fonts, palette
- The existing theme codebase: `doqendev/IL` (Shopify Online Store 2.0, `Charge` theme by
  Swissuplabs) — importable via Claude Design's Import menu

## What to ask for

Options, not answers. Several variations per page across different dimensions — some by-the-book
and matching existing patterns, some novel in layout, metaphor, or visual treatment. The goal is
atomic variations to mix and match, not one perfect comp.
