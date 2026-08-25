# Accessibility Inspection Checklist — Kagutungan Falls Website

| Requirement | Yes/No | Evidence / Correction |
|---|---|---|
| `lang` attribute is present | Yes | Every page opens with `<html lang="en">`. |
| Images have appropriate alt text | Yes | All content images (hero, gallery, route map) have descriptive `alt` text; decorative images (the small brand mark icon) use `alt=""` on purpose so screen readers skip them, and the visible site name next to it carries the meaning instead. |
| Headings are properly organized | Yes | Each page has exactly one `<h1>`, followed by `<h2>` section headings and `<h3>` sub-points, with no level skipped. |
| Form controls have labels | Yes | Every input/textarea on the Contact page has a `<label for="...">` tied to its `id`; hints are linked with `aria-describedby`. |
| Links have meaningful text | Yes | Links read as actions/destinations ("Read about the falls", "See the full route") instead of "click here". |
| Page can be navigated using keyboard | Yes | All interactive elements are native `<a>`, `<button>`, `<input>`, `<textarea>` — no custom widgets that trap or skip keyboard focus. A visible focus outline is styled in `style.css` (`:focus-visible`) so keyboard users can always see where they are. A "Skip to main content" link is the first focusable element on every page. |
| Text has sufficient contrast | Yes | Body text (`#1c2420`) on paper background (`#faf7f1`) and white text on the dark green hero (`#1f3d2b`) both exceed WCAG AA contrast for body text. The one place color alone could carry meaning — the active nav link — also gets an underline/box-shadow, not just a color change. |
| Semantic elements are used | Yes | Each page uses `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<figure>/<figcaption>`, and `<footer>` rather than generic `<div>`s for structure. |

## Notes for whoever maintains this site next
- If real photos replace the placeholder SVGs, write new `alt` text describing what's actually in each photo — don't just keep the old alt text.
- If a map embed (e.g. an actual Google Maps iframe) replaces the illustrated route sketch, give the iframe a `title` attribute and keep a text-based turn-by-turn list nearby, since maps alone aren't usable for screen reader visitors.
- Keep the contact phone/email in `contact.html` up to date — placeholders are clearly marked in the page and should be swapped for the barangay's real number and inbox.
