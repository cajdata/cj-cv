# Design System: chrisjohnson.cv

The shipped design is a light, editorial, technical-document look. Think printed spec sheet, not dashboard. An earlier dark "industrial" concept (safety orange, cyan, charcoal surfaces) was abandoned before launch; nothing from it applies to the live site.

## Principles

- Quiet precision. No gimmicks: no fake terminals, no fake telemetry, no decorative animation.
- Hairline rules and whitespace define structure. No cards, no shadows, no rounded corners.
- Strong left alignment. No centered body copy.
- No em dashes in copy.
- Every metric on the site is a real number confirmed by Chris. Do not invent or round up.

## Color

| Token | Value | Use |
|---|---|---|
| `--bg` | `#F6F3EE` | Page background (warm paper) |
| `--ink` | `#111111` | Primary text, dark rules |
| `--ink-mid` | `#555555` | Body and secondary text |
| `--ink-light` | `#666666` | Labels and metadata (passes WCAG AA on bg at ~5.2:1) |
| `--rule` | `#D8D4CC` | Hairline borders |
| `--accent` | `#0B3D91` | Links, metric values, CTA hover (used sparingly) |

## Typography

- IBM Plex Sans for headings and body. The H1 is large (62px) and light (300) with a bold first name.
- IBM Plex Mono for eyebrow labels, stats, tags, nav brand, and buttons. Uppercase with letterspacing is reserved for labels, never body copy.
- Fonts load from Google Fonts with preconnect and an async swap (`media="print"` trick) so render is never blocked. Keep the `<noscript>` fallback.

## Layout

- Single column, max-width 960px, 28px side padding.
- Fixed top nav (50px) with a bottom hairline.
- Sections use numbered mono eyebrow labels ("01 / Impact") in a 160px/1fr grid head.
- Buttons and tags are sharp-cornered, mono, uppercase; filled (`--ink`) or ghost.

## Pages

- `index.html`: portfolio. Hero with stats, impact metrics, skills table, STAR-format project entries, footer contact.
- `resume.html`: print-formatted resume (Arial, letter size, 8.5in max width, `@page` rules, small-screen media query). Must remain printable to 2 pages.

## Conventions

- External links: `target="_blank" rel="noopener noreferrer"`. Internal anchor links: no target.
- SEO surfaces (titles, meta descriptions, JSON-LD, OG tags, `llms.txt`) target the phrase "Chris Johnson Network Engineer" and must stay consistent with each other and with the visible page content.
