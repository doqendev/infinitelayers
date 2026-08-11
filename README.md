# Infinite Layers

Ground-up rebuild of the Infinite Layers storefront.

## Status

Pre-implementation. The stack is **not yet chosen** — see below. This repo was reset to a
clean base on 2026-08-11 so the decision isn't pre-empted by scaffolding.

## Stack decision (open)

Two candidates, to be settled once the UI direction is concrete:

| | Hydrogen + Oxygen | Liquid theme (OS 2.0) |
|---|---|---|
| UI implementation | React — design output ports directly | Hand-translated into Liquid sections |
| Theme editor | No | Yes |
| App ecosystem | Limited; reviews need API integration | Full support |
| Markets / locales | Rebuilt from scratch | Native |

An Oxygen storefront (ID `1000141634`) was previously provisioned for this project, so the
Hydrogen path may be a reconnect rather than a fresh setup.

## Carried over from the current site

The existing store runs the `Charge` theme (Swissuplabs) in [doqendev/IL](https://github.com/doqendev/IL).
Three things are being reused rather than rebuilt:

- **Personalization previews** — canvas/JS logic in the IL theme's snippets
- **Reviews**
- **Products**

## Archived history

The previous contents of `main` were a stock Hydrogen scaffold. Nothing was lost:

| Tag | Contents |
|---|---|
| `archive/hydrogen-scaffold` | The full 88-file Hydrogen skeleton |
| `archive/oxygen-workflow` | The above, plus the Oxygen deploy workflow |

Restore with `git checkout archive/hydrogen-scaffold`.
