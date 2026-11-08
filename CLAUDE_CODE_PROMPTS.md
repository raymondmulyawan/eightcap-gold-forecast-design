# Prompts for Claude Code

Put this whole `design_handoff_gold_price_forecast/` folder in the root of your website repo, open Claude Code in that repo, and paste these prompts one at a time. Review the result after each step before moving on.

---

## Prompt 1: Orient (no code yet)
```
Read design_handoff_gold_price_forecast/README.md in full, then open
design_handoff_gold_price_forecast/reference/gold-price-forecast-2030.html to see the design.

Then explore this repo and tell me:
1. The framework, routing and styling approach used.
2. How existing blog articles are built (template, CMS fields, components) — find the
   closest existing article page, e.g. how-to-trade-gold or how-to-trade-crude-oil.
3. Which existing components we can reuse: header, footer, breadcrumbs, buttons,
   CTA band, awards callout, author block, related-articles cards, FAQ accordion, tables.
4. What is missing and needs building.

Propose a short build plan. Don't write code until I approve the plan.
```

## Prompt 2: Content model
```
Following the approved plan, create the content and data for the Gold Price Forecast
article. Use the "Data and state" section of the README. Copy all text exactly from
reference/Gold Price Forecast 2030.dc.html (the data arrays are in the
<script data-dc-script> block at the bottom, the rest of the copy is in the markup).
Keep bracketed placeholders like $[price] and [Eightcap analyst to supply] as-is.
Put the data wherever this repo keeps blog content (CMS schema, MDX frontmatter or a
data file), so it can be updated monthly without touching layout code.
```

## Prompt 3: Build the page
```
Build the article page at /en-au/traders/insights/blogs/gold-price-forecast/ to match
the reference pixel for pixel at desktop width, following the README section by section
(hero, meta strip, sticky sidebar TOC, the 17 main-column blocks in order, footer).
Reuse existing site components wherever possible. Only create new components for:
dated news list, price-today stat grid, two-column annual averages table, turning-points
timeline, forecast table with type pills, scenario cards, tip tiles, disclaimer box.
Use the exact hex values, font sizes, spacing and radii from the README. Note that the H1
is 40px, not the 56px shown in the source.
Copy images from design_handoff_gold_price_forecast/assets into the repo's image
folder and use the framework's optimised image component with the given alt text.
```

## Prompt 4: Interactions, SEO and accessibility
```
Add:
- Smooth-scroll TOC anchors with scroll-margin-top so headings clear the sticky header,
  and an active-section highlight in the sidebar TOC (IntersectionObserver).
- An FAQ accordion: first item open, one item open at a time, aria-expanded, and the +
  icon rotating 45° over 160ms.
- Title tag, meta description and canonical URL from the README.
- JSON-LD: Article (with dateModified = lastUpdated, reviewedBy) and FAQPage matching
  the visible FAQ text exactly. Add BreadcrumbList.
- Semantic tables (thead/th scope) for the averages and forecast tables.
- Keyboard focus styles on all links and buttons.
Then run the linter, type checks and build, and fix any errors.
```

## Prompt 5: Visual QA
```
Run the site locally and compare the page against
design_handoff_gold_price_forecast/reference/gold-price-forecast-2030.html at 1440px
wide, section by section. List any differences in spacing, type, colour or alignment,
then fix them. Check that every internal link in the README's "Internal links used" list
is present and points to the right URL.
```

## Prompt 6 (later): Mobile
```
Make the page responsive using the "Responsive" notes in the README, following the same
patterns as our existing mobile blog pages: a stacked hero, a collapsible "In this
article" TOC, single-column grids, tables that become cards or scroll horizontally,
44px tap targets and a sticky bottom CTA bar. Don't change the desktop layout.
```
