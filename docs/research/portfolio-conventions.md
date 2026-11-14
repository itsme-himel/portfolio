# Conventions for a minimalist single-page portfolio (hybrid academic/industry profile)

Researched 2026-11-14. Profile in scope: 2 work experiences, ongoing Master's thesis, 2 education entries, certifications, personal projects, extracurricular activities.

## How to read this note

Each claim carries a verification tag:

- **[V]** Read directly in the source owner's own repository or file (URL given).
- **[S]** Search-engine summary of the owner's page only. The page itself was not opened.
- **[I]** Inference or recommendation drawn from the [V] evidence. Not stated by any source.
- **[unverified]** Looked for and not found, or the owning source was not read.

Limits of this research session:

- Only GitHub was reachable. `www.w3.org`, `docs.github.com`, `developers.google.com`, `capd.mit.edu`, `careerservices.fas.harvard.edu` and `gradschool.cornell.edu` failed to resolve (outside the session's allowed network domains). After those six failures, `developer.mozilla.org`, `web.dev` and `schema.org` were not attempted.
- W3C, MDN, web.dev, schema.org and GitHub Docs were therefore read from the repositories those organisations publish from. The WCAG text is the `main` branch of `w3c/wcag` (editor's source), which can differ in notes from the published Recommendation at https://www.w3.org/TR/WCAG22/. The web.dev text is from the archived `GoogleChrome/web.dev` repository and may be older than the live page.
- **University career-center pages and Google Search Central were not read.** Everything attributed to them is [S] and should be re-checked before being relied on.
- Stanford career guidance was not researched at all.

## 1. Section order

### What the templates do [V]

| Source | Order found |
|---|---|
| Jon Barron's site (single page, no `<nav>`) | Name and bio paragraph, link row (Email / CV / Bio / Scholar / Twitter / Github), Research, Miscellanea, Micropapers, Recorded Talks, Academic Service, Teaching. [index.html](https://github.com/jonbarron/jonbarron_website/blob/master/index.html) |
| academicpages CV page | Education, Work experience, Skills, Publications, Talks, Teaching, Service and leadership. [_pages/cv.md](https://github.com/academicpages/academicpages.github.io/blob/master/_pages/cv.md) |
| academicpages header nav | Publications, Talks, Teaching, Portfolio, Blog Posts, CV, Guide. [_data/navigation.yml](https://github.com/academicpages/academicpages.github.io/blob/master/_data/navigation.yml) |
| al-folio CV data | Education, Experience, Volunteer, Awards, Publications, Skills, Languages, Interests, Certificates, Projects, References. [_data/cv.yml](https://github.com/alshedivat/al-folio/blob/main/_data/cv.yml) |
| al-folio landing page | Bio with photo, announcements, latest posts, selected papers, social icons. [_pages/about.md](https://github.com/alshedivat/al-folio/blob/main/_pages/about.md) |
| Hugo Blox academic CV landing page | Biography block (about, education, interests, "Download CV" button), research statement, featured publications, recent publications, talks, news. [content/_index.md](https://github.com/HugoBlox/theme-academic-cv/blob/main/content/_index.md) |
| JSON Resume schema (industry-oriented; al-folio accepts it as CV input) | basics, work, volunteer, education, awards, certificates, publications, skills, languages, interests, references, projects. [schema.json](https://github.com/jsonresume/resume-schema/blob/master/schema.json) |

Observations:

- All four academic templates open with identity and a short biography before any list. [V, table above]
- The two academic CV layouts put Education before Experience; the industry-oriented JSON Resume schema puts work before education. [V, table above]
- None of the templates has a section for an in-progress thesis, for certifications on the landing page, or for extracurriculars under that name. al-folio and JSON Resume have `Certificates` and `Volunteer`. [V, table above]
- The academic landing pages are built around publications. This profile has none listed, so that slot has no direct equivalent. [I]

### What career centers say [S, not read directly]

- Cornell Graduate School's CV/resume handout is summarised as saying to arrange categories in order of importance to the reader, and that a resume is typically used for non-academic industry positions while a CV is the standard in academia. https://gradschool.cornell.edu/wp-content/uploads/2024/08/CV-Resume-Handout.pdf
- MIT CAPD's CV page is summarised as advising that the most important section goes first, and listing Name and Contact, Education, Research Experience, Fellowships/Awards as common headings. https://capd.mit.edu/resources/cvs/
- Harvard's GSAS guide is summarised as saying to use a resume rather than a CV for most non-research, non-academic jobs. No section-order statement was found. https://careerservices.fas.harvard.edu/resources/gsas-cv-cover-letter-guide/

### Recommended order for this profile [I]

1. **Header**: name as the single `<h1>`, one-line descriptor, two to four sentence bio, link row (email, CV PDF, GitHub, LinkedIn). Follows the pattern common to all four templates.
2. **Education**, with the ongoing Master's first and the thesis nested under it. Rationale: the academic CV layouts lead with education, the academicpages sample lists entries newest first, and the degree in progress is the current primary activity.
3. **Experience** (the 2 roles, newest first).
4. **Projects**.
5. **Certifications**.
6. **Extracurricular activities** (the `Volunteer` / "Service and leadership" slot).
7. **Footer** with contact links repeated.

If the site is aimed mainly at industry recruiters, swap 2 and 3, matching the JSON Resume order. The only rule the career centers appear to state is "most important to the reader first" [S], so the choice depends on the audience and is a decision for the site owner, not something a source settles.

## 2. Presenting an ongoing thesis

- The academicpages sample CV lists an unfinished degree inline in Education with the year and the word "expected": "Ph.D in Version Control Theory, GitHub University, 2018 (expected)". [V] [_pages/cv.md](https://github.com/academicpages/academicpages.github.io/blob/master/_pages/cv.md)
- al-folio and JSON Resume model an education entry as institution, area, studyType, startDate, endDate, courses, highlights. There is no thesis field; a thesis has to go in `highlights` or in a `projects` entry. [V] [resume.json](https://github.com/alshedivat/al-folio/blob/main/assets/json/resume.json)
- A 2015 MIT careers workshop deck is summarised as suggesting the thesis title and advisor under Education, with the research described under Research Experience. [S] https://postdocs.mit.edu/document/gecd-broad-mit-academic-industry-cv-workshop-2015-09-21
- No primary source was found that prescribes wording for a thesis in progress. [unverified]

Recommendation [I]: nest it under the Master's entry with a visible status and no claimed results:

    MSc <programme>, <university>            2025 – 2027 (expected)
    Thesis (in progress): <working title>
    Supervisor: <name>, <group>. One sentence on the question and method.

If the thesis is the strongest item on the page, it can instead be the first entry in Projects with the same "in progress" label and a back-reference from Education. List it in one place only.

## 3. Typography and line length

- Line length: web.dev quotes Bringhurst: "Anything from 45 to 75 characters is widely regarded as a satisfactory line length ... The 66-character line ... is widely regarded as ideal." It recommends `max-inline-size` in `ch` or `rem`, not `px`, and uses `66ch` in its example. [V] [web.dev typography](https://github.com/GoogleChrome/web.dev/blob/main/src/site/content/en/learn/design/typography/index.md). The Bringhurst text itself was not consulted.
- WCAG 1.4.8 (level AAA, so not required for AA) asks that a mechanism exists for width of no more than 80 characters, non-justified text, and line spacing of at least 1.5 within paragraphs. The criterion notes that the browser may supply the mechanism. [V] [SC 1.4.8](https://github.com/w3c/wcag/blob/main/guidelines/sc/20/visual-presentation.html)
- Technique C20 says to set column widths in relative units so lines can average 80 characters or fewer; its example is `max-width: 70em`. [V] [C20](https://github.com/w3c/wcag/blob/main/techniques/css/C20.html)
- Base size: the browser default root font size is 16px; MDN advises `rem` units. [V] [MDN text fundamentals](https://github.com/mdn/content/blob/main/files/en-us/learn_web_development/core/text_styling/fundamentals/index.md). web.dev's fluid example is `clamp(1rem, 0.75rem + 1.5vw, 2rem)`, so text never goes below the user's preferred size. [V, web.dev typography, linked above]
- Line height: use unitless values; web.dev's examples pair `66ch` with `1.65` and say shorter lines can take larger values. [V, web.dev typography]
- Text must survive user overrides of line height 1.5, paragraph spacing 2x, letter spacing 0.12x and word spacing 0.16x the font size (WCAG 1.4.12, AA). Avoid fixed-height text containers. [V] [SC 1.4.12](https://github.com/w3c/wcag/blob/main/guidelines/sc/21/text-spacing.html)
- Fonts: "every web font file you add could potentially degrade the user experience as it increases page load time". If a web font is used: WOFF2, `rel="preload"` with `crossorigin`, and a `font-display` value. [V, web.dev typography; [MDN web fonts](https://github.com/mdn/content/blob/main/files/en-us/learn_web_development/core/text_styling/web_fonts/index.md); [MDN font-display](https://github.com/mdn/content/blob/main/files/en-us/web/css/reference/at-rules/@font-face/font-display/index.md)] A system font stack avoids the question entirely. [I]
- Reference point: Barron's page uses one family (Lato), 14px body, 22px `h2`, 32px name, an 800px maximum page width and a single breakpoint at 600px. [V] [stylesheet.css](https://github.com/jonbarron/jonbarron_website/blob/master/stylesheet.css). al-folio defaults to `max_width: 930px`. [V] [_config.yml](https://github.com/alshedivat/al-folio/blob/main/_config.yml). 14px is below the 16px browser default, so it is a precedent, not a recommendation. [I]

## 4. Accessibility requirements

Target WCAG 2.2 level AA. Criteria that apply to a static single page [V, each linked to its source file under https://github.com/w3c/wcag/tree/main/guidelines/sc]:

| SC | Level | Requirement | Consequence for this site |
|---|---|---|---|
| [1.1.1](https://github.com/w3c/wcag/blob/main/guidelines/sc/20/non-text-content.html) | A | Text alternative for non-text content; decoration ignorable by assistive technology | `alt` on a portrait; empty `alt` or `aria-hidden` on decorative icons |
| [1.3.1](https://github.com/w3c/wcag/blob/main/guidelines/sc/20/info-and-relationships.html) | A | Structure is programmatically determinable | Real headings, lists, `<header>`, `<main>`, `<nav>`, `<footer>` |
| [1.4.1](https://github.com/w3c/wcag/blob/main/guidelines/sc/20/use-of-color.html) | A | Color is not the only visual means of conveying information | Links in body text need more than a color change |
| [1.4.3](https://github.com/w3c/wcag/blob/main/guidelines/sc/20/contrast-minimum.html) | AA | Text contrast at least 4.5:1; large text 3:1 | Check grey secondary text (dates, locations) in both color schemes |
| [1.4.4](https://github.com/w3c/wcag/blob/main/guidelines/sc/20/resize-text.html) | AA | Text resizable to 200 percent without loss | Relative units; no `user-scalable=no` |
| [1.4.10](https://github.com/w3c/wcag/blob/main/guidelines/sc/21/reflow.html) | AA | No two-dimensional scrolling at 320 CSS px width | Single column at narrow widths |
| [1.4.11](https://github.com/w3c/wcag/blob/main/guidelines/sc/21/non-text-contrast.html) | AA | 3:1 for UI components and meaningful graphics | Icon-only links, focus ring |
| [1.4.12](https://github.com/w3c/wcag/blob/main/guidelines/sc/21/text-spacing.html) | AA | No loss of content under the text-spacing overrides | See section 3 |
| [2.2.2](https://github.com/w3c/wcag/blob/main/guidelines/sc/20/pause-stop-hide.html) | A | Auto-starting motion longer than five seconds needs pause/stop/hide | Easiest met by having no such motion |
| [2.4.1](https://github.com/w3c/wcag/blob/main/guidelines/sc/20/bypass-blocks.html) | A | Bypass blocks "repeated on multiple web pages" | See note below |
| [2.4.2](https://github.com/w3c/wcag/blob/main/guidelines/sc/20/page-titled.html) | A | Page has a descriptive title | `<title>` |
| [2.4.4](https://github.com/w3c/wcag/blob/main/guidelines/sc/20/link-purpose-in-context.html) | A | Link purpose clear from text or context | No bare "here" or "link"; name icon links |
| [2.4.6](https://github.com/w3c/wcag/blob/main/guidelines/sc/20/headings-and-labels.html) | AA | Headings describe topic or purpose | Plain section names |
| [2.4.7](https://github.com/w3c/wcag/blob/main/guidelines/sc/20/focus-visible.html) | AA | Keyboard focus indicator is visible | Do not remove outlines |
| [2.4.11](https://github.com/w3c/wcag/blob/main/guidelines/sc/22/focus-not-obscured-minimum.html) | AA | Focused component not entirely hidden by author content | Applies if the nav is sticky |
| [2.5.8](https://github.com/w3c/wcag/blob/main/guidelines/sc/22/target-size-minimum.html) | AA | Targets at least 24 by 24 CSS px, with spacing and inline-text exceptions | Nav links and icon links; links inside sentences are exempt |
| [3.1.1](https://github.com/w3c/wcag/blob/main/guidelines/sc/20/language-of-page.html) | A | Page language programmatically determinable | `<html lang="…">` |

Notes:

- **Skip link.** 2.4.1 is worded for blocks repeated across multiple pages, and the Understanding document says that for pages not in a set a skip mechanism "may be helpful (but not required)". [V] [Understanding 2.4.1](https://github.com/w3c/wcag/blob/main/understanding/20/bypass-blocks.html). A skip link is therefore good practice, not a strict AA requirement, on a one-page site. [I] MDN's pattern: a link placed as early as possible in `<body>` pointing at `<main id>`, hidden offscreen until focused. [V] [MDN `<a>`](https://github.com/mdn/content/blob/main/files/en-us/web/html/reference/elements/a/index.md)
- **Anchor navigation.** `<nav>` is for major blocks of navigation links; if a page has more than one, label them. [V] [MDN `<nav>`](https://github.com/mdn/content/blob/main/files/en-us/web/html/reference/elements/nav/index.md). With a fixed or sticky header, MDN documents `scroll-padding` on the scroll container as the way to keep anchor targets from being hidden under it. [V] [MDN scroll-padding](https://github.com/mdn/content/blob/main/files/en-us/web/css/reference/properties/scroll-padding/index.md). The MDN `scroll-margin-top` page describes the property only in scroll-snap terms; its use on anchor targets is common practice but was not confirmed there. [unverified] [MDN scroll-margin-top](https://github.com/mdn/content/blob/main/files/en-us/web/css/reference/properties/scroll-margin-top/index.md). Sticky headers are named in the 2.4.11 Understanding document as typical content that obscures focus. [V] [Understanding 2.4.11](https://github.com/w3c/wcag/blob/main/understanding/22/focus-not-obscured-minimum.html)
- **Reduced motion.** 2.3.3 Animation from Interactions is level AAA. [V] [SC 2.3.3](https://github.com/w3c/wcag/blob/main/guidelines/sc/21/animation-from-interactions.html). Technique C39 uses `prefers-reduced-motion` to disable motion. [V] [C39](https://github.com/w3c/wcag/blob/main/techniques/css/C39.html); [MDN prefers-reduced-motion](https://github.com/mdn/content/blob/main/files/en-us/web/css/reference/at-rules/@media/prefers-reduced-motion/index.md). If `scroll-behavior: smooth` is used, put it inside `@media (prefers-reduced-motion: no-preference)`. [I]
- **Color scheme.** `prefers-color-scheme` detects the light/dark preference; the `color-scheme` property makes browser-drawn UI (canvas, scrollbars, form controls) match. [V] [MDN prefers-color-scheme](https://github.com/mdn/content/blob/main/files/en-us/web/css/reference/at-rules/@media/prefers-color-scheme/index.md); [MDN color-scheme](https://github.com/mdn/content/blob/main/files/en-us/web/css/reference/properties/color-scheme/index.md). Dark mode is not a WCAG requirement, but 1.4.3 applies to every scheme shipped. [I] al-folio follows the system preference and adds a toggle; Barron's stylesheet has no dark mode. [V] [al-folio README](https://github.com/alshedivat/al-folio/blob/main/README.md)
- **Focus styles.** MDN: removing focus styles "makes keyboard navigation inaccessible for sighted users"; the indicator should reach 3:1. [V] [MDN :focus-visible](https://github.com/mdn/content/blob/main/files/en-us/web/css/reference/selectors/_colon_focus-visible/index.md)
- **Zoom.** `user-scalable=no` blocks low-vision users from zooming. [V] [MDN viewport meta](https://github.com/mdn/content/blob/main/files/en-us/web/html/reference/elements/meta/name/viewport/index.md)
- **Target size.** MDN recommends 44 by 44 CSS px for links, above the 24 px AA minimum. [V, MDN `<a>`]
- **Print.** `@media print` hides navigation and restyles for paper; `@page` sets margins. [V] [MDN printing](https://github.com/mdn/content/blob/main/files/en-us/web/css/guides/media_queries/printing/index.md). For a CV-like page a print stylesheet can stand in for a separate PDF. [I]

## 5. Metadata and SEO minimum

In `<head>` [V unless tagged]:

- `<meta charset="utf-8">`, a `<title>`, `<meta name="description">` and `<meta name="author">`. MDN notes the title and description are what search results show. [MDN webpage metadata](https://github.com/mdn/content/blob/main/files/en-us/learn_web_development/core/structuring_content/webpage_metadata/index.md)
- `<meta name="viewport" content="width=device-width, initial-scale=1">` and `<html lang>`. [MDN viewport meta, linked above; SC 3.1.1]
- A favicon. [MDN webpage metadata]
- `<link rel="canonical">`, defined as the preferred URL for the document. [MDN rel](https://github.com/mdn/content/blob/main/files/en-us/web/html/reference/attributes/rel/index.md). Useful when the site is reachable at both a `github.io` address and a custom domain. [I]
- Open Graph tags for link previews. Barron's page ships `og:title`, `og:description`, `og:type`, `og:url`, `og:image` and `twitter:card`; that is the whole of its social metadata. [index.html](https://github.com/jonbarron/jonbarron_website/blob/master/index.html). The Open Graph specification (ogp.me) was not read. [unverified]

Structured data:

- schema.org defines `Person` and `ProfilePage` ("Web page type: Profile page"), with Person properties including `jobTitle`, `worksFor`, `alumniOf`, `affiliation`, `knowsAbout`, `hasCredential`, `email`, and `sameAs` ("URL of a reference Web page that unambiguously indicates the item's identity"). [V] [schema.ttl](https://github.com/schemaorg/schemaorg/blob/main/data/schema.ttl)
- Google's profile-page documentation is summarised as requiring `mainEntity` (a Person or Organization) with `name`, and recommending `dateCreated` / `dateModified`. Whether Google treats a self-published one-person site as an intended use was not confirmed. [S] https://developers.google.com/search/docs/appearance/structured-data/profile-page
- Google is summarised as choosing title links from `<title>`, the visible main heading and other sources, and as building snippets mainly from page content, using the meta description when it describes the page better. [S] https://developers.google.com/search/docs/appearance/title-link
- Precedent is weak: Barron's page has no JSON-LD, and al-folio ships `serve_schema_org: false` and `serve_og_meta: false` by default. [V, index.html and _config.yml linked above]

Minimum [I]: title, description, viewport, lang, canonical, favicon, five Open Graph tags, and one JSON-LD block of `ProfilePage` with `mainEntity` a `Person` carrying `name`, `url`, `jobTitle`, `alumniOf` and `sameAs` (GitHub, LinkedIn). Keep the `<title>` and the `<h1>` consistent.

Hosting on GitHub Pages [V]:

- A user site must live in a repository named `<user>.github.io`, lowercase, one per account. [what-is-github-pages.md](https://github.com/github/docs/blob/main/content/pages/getting-started-with-github-pages/what-is-github-pages.md); [create-repo-name.md](https://github.com/github/docs/blob/main/data/reusables/pages/create-repo-name.md)
- The entry file is `index.html`, `index.md` or `README.md` at the top level of the publishing source. Branch publishing runs Jekyll by default; an empty `.nojekyll` file in the root of the source disables it. No server-side languages. [creating-a-github-pages-site.md](https://github.com/github/docs/blob/main/content/pages/getting-started-with-github-pages/creating-a-github-pages-site.md)
- Sites are public even when the repository is private. [private_pages_are_public_warning.md](https://github.com/github/docs/blob/main/data/reusables/pages/private_pages_are_public_warning.md)
- Limits: published site up to 1 GB, soft 100 GB per month bandwidth, soft 10 builds per hour; not for commercial transactions or SaaS. [github-pages-limits.md](https://github.com/github/docs/blob/main/content/pages/getting-started-with-github-pages/github-pages-limits.md)
- HTTPS is supported and can be enforced; all assets must then be loaded over `https://`. [securing-your-github-pages-site-with-https.md](https://github.com/github/docs/blob/main/content/pages/getting-started-with-github-pages/securing-your-github-pages-site-with-https.md)

## 6. What to leave out

Supported by a source:

- Empty template sections. academicpages' nav file states that removing a link removes it from the header; Talks, Teaching and Blog are template defaults, not obligations. [V, navigation.yml]
- Analytics, cookie consent, scroll progress bar, image zoom and similar extras. They are optional flags in al-folio and absent from Barron's page. [V, al-folio _config.yml; Barron index.html]
- Extra web font files, since each one costs load time. [V, web.dev typography]
- Auto-playing or looping motion and scroll-triggered animation: the first raises 2.2.2, the second is what C39 and 2.3.3 address. [V, SC 2.2.2, C39]
- Justified text, long unconstrained lines, fixed pixel widths for text columns. [V, SC 1.4.8, C20, web.dev typography]
- `user-scalable=no` and removed focus outlines. [V, MDN viewport meta, MDN :focus-visible]
- A sticky header, unless `scroll-padding` and focus-obscuring are handled. Barron's page has no navigation at all. [V for the facts; the "leave out" is I]
- Anything sensitive in the repository: the published site is public. [V, GitHub Pages warning]

Judgment only [I]:

- A "References" section (present in JSON Resume and al-folio data, but it publishes other people's contact details) and a street address (al-folio's sample includes one).
- Skill bars or self-rated percentages. Barron's page has none and the academicpages sample CV lists skills as plain text.
- A contact form. GitHub Pages has no server side; a `mailto:` link is what Barron's page uses.
- Thesis results that do not exist yet.
- With 2 jobs and 2 degrees the page is short; one bullet list per entry is enough and a timeline widget or per-project subpage adds nothing.

Not established: whether to include a portrait photo. Barron, al-folio and Hugo Blox all show one on the landing page [V], but career-center guidance on photos was not read. [unverified]
