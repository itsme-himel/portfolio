# Portfolio site: design

## Intent
A single-page personal portfolio that reads as professional with an academic side.
Minimal, plain wording, no marketing language.

## Goals
- One page holding: About, Experience (2), Research (ongoing Master's thesis), Education (2),
  Projects, Certifications, Activities, contact links.
- Readable on a phone, by keyboard, in light and dark, and when printed (doubles as a PDF CV).

## Non-goals
Blog, contact form, analytics, animation, skill bars, CMS, multiple pages.

## Anti-goals
Buzzwords or filler sentences. Empty sections. Anything that looks like a template.

## Approaches considered
- A, Document: one serif column, thesis first. Suits academic readers; gets long as projects grow.
- B, Sidebar: identity and section nav fixed on the left, content on the right, experience first.
  Suits recruiters; looks sparse if content is thin. **Chosen by the owner.**

## Design (B)
- Layout: 15rem left column (name, one-line role, section nav, contact links, CV link), sticky on
  wide screens; content column on the right. Below ~640px the sidebar becomes a header and the nav
  a wrapped row of links.
- Section order: About, Experience, Research, Education, Projects, Certifications, Activities.
- Entries: title, organisation, date right-aligned in monospace, then up to three plain bullets.
  Projects are a two-column grid with a one-line description and stack labels.
- Thesis: its own Research section, marked "In progress", with working title, supervisor and
  expected date. No claimed results.
- Type: IBM Plex Sans for text, IBM Plex Mono for dates and stack labels. 16px base, text columns
  capped near 62 characters.
- Colour: neutral greys with one dark green accent for section labels, links and the current nav
  item. Light and dark via `prefers-color-scheme`. Contrast at least 4.5:1.
- Behaviour: nav links are in-page anchors; a small inline script underlines the current section in the nav.

## Builder's calls (not decided by the owner)
- Plain `index.html` + `styles.css`, no framework or build step.
- Hosted on GitHub Pages from this repo (URL `<user>.github.io/portfolio`).
- Fonts from Google Fonts with a system fallback stack.
- Metadata: title, description, canonical, Open Graph tags, favicon. No JSON-LD.
- Print stylesheet hides the nav and lays the page out in one column.

## Needed from the owner
Real content for every section (a CV is enough), plus the email and profile links to show.
