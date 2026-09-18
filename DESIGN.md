# The Reading Room

## 1. Atmosphere & Identity

A quiet personal library, not a storefront. Cream paper, forest-green ink,
coral details, generous margins, and literary serif headings. The signature is
an original illustrated shelf: dimensional paper edges, leaning cloth spines,
and a sunlit arch. Illustration is decorative, never a fake catalog entry.

The existing standalone summary supplies the palette and Georgia/system-sans
pairing. Its brand, navigation, hero, metadata strip, chapter headings, source
links, and illustrated cards were inspected; the summary stays untouched.
Frontend editorial, interaction, perfection, and designpowers review references
inform the new page. This is an extraction of the existing visual language,
not a clone of an unrelated brand. No image assets or external fonts are needed.

## 2. Color

| Token | Value | Role |
| --- | --- | --- |
| `--paper` | `#f5f1e9` | Page background |
| `--white` | `#fffdf8` | Paper highlights and input |
| `--ink` | `#172f2a` | Main text and book cloth |
| `--green` | `#27634f` | Actions and illustration |
| `--muted` | `#63716a` | Supporting text |
| `--line` | `#d5d8cc` | Fine rules |
| `--coral` | `#d88869` | Decorative warm accent |
| `--rust` | `#a3472d` | Accessible accent text and focus |
| `--lime` | `#d6e7b8` | Book artwork and selection |
| `--sand` | `#e9e2d4` | Illustration recess and cover stage |
| `--sage` | `#aeb9a1` | Decorative cloth spine |
| `--shadow` | `#172f2a26` | Object shadows only |

No semantic alert palette is needed: empty search is neutral, not an error.

## 3. Typography

Serif: Georgia, Times New Roman, serif. Sans: system-ui, sans-serif. These are
intentional local stacks, with no network font dependency.

| Token | Size | Use |
| --- | --- | --- |
| `--display` | clamp(3.5rem, 6.5vw, 6rem) | Hero, regular weight, 1.02 line height |
| `--heading` | clamp(2rem, 3vw, 2.75rem) | Section title |
| `--title` | clamp(1.75rem, 2.6vw, 2.25rem) | Book title |
| `--lead` | 1.125rem | Introductory copy |
| `--body` | 1rem | Body copy and controls |
| `--small` | .875rem | Supporting information |
| `--label` | .6875rem | Uppercase metadata, .14em tracking |

Headings use -.045em tracking; body line height is 1.7. Illustration lettering
uses SVG coordinates; it is decorative and duplicates no required information.

## 4. Spacing & Layout

4px base: `--s1` 4px, `--s2` 8px, `--s3` 12px, `--s4` 16px,
`--s5` 20px, `--s6` 24px, `--s8` 32px, `--s10` 40px, `--s12` 48px,
`--s16` 64px, `--s20` 80px. Content width 1160px; fluid gutters 24-64px.
Hero is an asymmetric two-column spread, stacking below 760px. Catalog entries
use a 240px cover stage beside the reading description; below 540px they stack.
The page scrolls naturally, without fixed overlays or nested scroll containers.
SVG coordinates are illustration geometry, not UI spacing tokens.

## 5. Components

- Masthead: book-mark SVG, serif wordmark, small collection anchor. Fine bottom rule.
- Eyebrow: small uppercase label and coral dash; never an interactive badge.
- Text action: green link with arrow; underline on hover, rust focus ring, no nested controls.
- Book card: semantic article, decorative cover, category, linked heading,
  author, descriptive paragraph, language metadata, and a clearly named reading link.
  Entire article is not clickable. Cover lifts when a contained link is hovered or focused.
- Search: labeled native search input, decorative magnifier, polite result count.
  Hidden until JavaScript initializes. Empty results show a clear-search button;
  clearing restores entries and returns focus to the input.
- Shelf illustration: responsive inline SVG, aria-hidden, no interactive fake books.
- Footer: small collection note and real back-to-top anchor.

## 6. Motion & Interaction

`--ease`: cubic-bezier(.16,1,.3,1). `--quick`: 220ms. `--entrance`: 700ms.
One initial 16px rise/fade establishes the hero; no loops, cursor tracking,
scroll hijacking, timers, or animation library. Real book artwork rises 4px and
rotates -2deg on hover/focus-within to signal that its reading links are active.
Native CSS transitions can reverse immediately. Reduced motion disables all
animations, transitions, transforms, and smooth scrolling. Content remains
visible if JavaScript is unavailable. Search is an immediate native filter.

## 7. Depth & Surface

Mixed treatment: thin structural rules; warm tonal illustration recesses;
object shadows only on physical books and the shelf. UI controls are flat.
`--book-shadow`: 8px 12px 20px var(--shadow). Radius `--radius`: 4px.
No floating dashboard cards, gradients behind text, or decorative UI chrome.
SVG gradients render cloth light and paper edges using palette tokens.

## 8. Accessibility Constraints & Accepted Debt

Target WCAG 2.2 AA. Reading and browsing must work without JavaScript. Keyboard
users have a skip link, visible 3px focus outlines with 5px offsets, and native
links/buttons. Search is labeled and reports results politely; empty state is
text, not color alone. Mobile controls are at least 44px high. Screen-reader
users do not hear decorative cover or shelf artwork. Reduced-motion users see
the same content with no movement. Long titles wrap; no fixed content heights.

No accepted accessibility debt. The original summary is out of scope. Browser
visual QA and any performance measurements must be reported separately; this
document does not imply a completed audit.
