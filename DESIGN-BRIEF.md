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

### Mobile adaptation of the ratio system — required

The ratio system does **not** survive a naive port to mobile. At a 390px viewport, a 2.39:1 crop
is roughly 163px tall against a 1:1 crop at 390px. In a two-up mobile grid the screen items look
shrunken and weak beside the music ones, which inverts the intended balance.

Two workable directions — design both and compare:

- **Single-column feed.** Full-width cards stacked, alternating 1:1 and 2.39:1. The ratio
  difference becomes deliberate scroll rhythm rather than a size mismatch. Reads like a social
  feed, which suits the audience.
- **Compress the ratio on small screens.** Screen items shift 2.39:1 → 16:9 or 3:2 below the
  tablet breakpoint, keeping the two-up grid viable. Category still reads, imbalance disappears.

Whichever wins, the distinction must stay legible at 390px without relying on a label.

---

## Mobile first — not a follow-up pass

**The majority of traffic is mobile.** Design every screen at 390px first and let desktop be the
adaptation, not the other way round. A desktop comp that gets "made responsive" afterwards will
fail on the pages that matter most here.

Every page in the list below needs a mobile comp. Where only one can be produced, produce the
mobile one.

The hard mobile problems, in order of difficulty:

1. **The personalization PDP.** This is the crux of the whole build. The customer needs to see a
   live canvas preview *while* typing custom text — but the on-screen keyboard covers roughly half
   the viewport the moment the field is focused. If the preview sits below the input, it is
   invisible at the exact moment it matters. Solutions to explore: a sticky preview pinned above
   the fold with the controls scrolling beneath it, a preview that docks to a compact strip while
   editing, or a full-screen preview mode with a floating edit control. **This one page justifies
   several variants on its own.**
2. **Gift-finder filters.** Budget, occasion, and recipient can't be a desktop sidebar. They need a
   bottom sheet or a horizontally scrolling chip row, with active filters visible without
   reopening the panel.
3. **Variant + personalization together.** Size, colour, *and* custom text on one small screen,
   without the page becoming an endless scroll before add-to-cart.
4. **The bundle builder.** Assembling three items into one gift is inherently multi-step; on mobile
   it likely needs a staged flow rather than a single dense page.

Also required throughout: sticky add-to-cart on product pages, thumb-reachable primary actions,
tap targets sized for real hands, and image weight kept low enough for mobile data.

## Pages to design

In priority order. **Each needs a mobile comp; desktop is secondary.**

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
- **Mobile is the primary viewport.** See the mobile section above — this is a constraint on every
  page, not a later pass.
- **The personalization preview is live and canvas-based** — it re-renders as the customer types
  or changes variant. Design it as an interactive surface, not a static product image. On mobile
  it must stay visible while the keyboard is open.
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
