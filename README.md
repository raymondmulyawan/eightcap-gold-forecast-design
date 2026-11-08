# Handoff: Gold Price Forecast 2030 (Eightcap blog article)

## Overview
A long-form SEO blog article for eightcap.com: **"Gold price forecast to 2030: what analysts predict"**. It summarises today's gold price, historical annual averages, dated bank/analyst forecasts, news sentiment and Eightcap's own scenario framework, and moves readers to the XAUUSD trade page and the gold guides.

- Target URL: `/en-au/traders/insights/blogs/gold-price-forecast/`
- Title tag: `Gold Price Forecast 2030: What Analysts Predict | Eightcap`
- Meta description: `Gold price forecast to 2030: today's price, historical averages, what banks like Goldman and JPMorgan predict, and Eightcap's scenarios. Not financial advice.`
- The page is refreshed after every Fed meeting or major bank target change, so all data must live in editable content (CMS fields or a data file), not hard-coded markup.

## About the design files
The files in `reference/` are **design references built in HTML**. They show the intended look, copy and behaviour. They are not production code to copy directly. Recreate the design in the target codebase's existing environment (Eightcap's site stack, components and CMS), reusing existing site components wherever they exist: header, footer, breadcrumbs, buttons, blog author block, related-articles cards, awards strip.

- `reference/gold-price-forecast-2030.html`: self-contained, opens offline in any browser. **Use this to view the design.**
- `reference/Gold Price Forecast 2030.dc.html`: the editable source. Markup uses inline styles, and the data arrays (news, history, forecasts, scenarios, FAQ) live in the `<script data-dc-script>` block at the bottom. **Use this to read exact values and copy.**

## Fidelity
**High fidelity.** Colours, type, spacing and copy are final. The one exception is the bracketed placeholders listed under "Open items". Match the design pixel for pixel at desktop (≥1280px). Mobile hasn't been designed yet; see Responsive below.

## Page layout (desktop)
- Page min-width in the reference is 1280px. Content max-width is **1200px**, centred, with **48px** side padding.
- Body grid below the hero has two columns: a **250px** sticky sidebar and a main column of **max 800px**, with an **80px** gap, `align-items:start`.
- Sections in the main column are separated by **56px** of space (`margin-bottom:56px`).

### 1. Header (reuse the existing site header)
- Sticky, top 0, z-index 50, white background, bottom border `1px #ECEFEE`, padding `14px 48px`.
- Left: the Eightcap wordmark, 30px tall.
- Right, with a 20px gap between items:
  - "Search" text in `#5B6560`.
  - "EN".
  - "Login" pill: background `#EFF1F0`, padding 9px 18px, radius 24px.
  - "Trade now" pill: background `#6C5CE7`, white text, weight 600, padding 10px 22px.
  - Menu icon.

### 2. Hero (`#top`)
- Background `#D7F5E2`. Padding is `36px 48px 0`, so the image sits flush with the bottom edge.
- Breadcrumb: 13px, `#3E5A4A`, `›` separators at 50% opacity, 28px bottom margin. The trail is Home › Knowledge hub › Insights › **Gold price forecast** (current page in `#0B0F14`, weight 500).
- Grid: `1fr 480px`, 64px gap, min-height 400px.
- Left column (48px bottom padding):
  - Eyebrow "COMMODITIES · GOLD": Poppins 12px/600, letter-spacing .08em, uppercase, `#1F7A45`, 18px bottom margin.
  - H1 "Gold price forecast to 2030: what analysts predict": Poppins 600, **40px** (set by the user in the editor; the source shows 56px but 40px is final), line-height 1.05, letter-spacing -0.02em, 20px bottom margin.
  - Intro: DM Sans 19px, line-height 1.55, `#2B3A32`, max-width 580px, 24px bottom margin.
  - Meta row: 14px, 12px gap. "Last updated 29 October 2026" in weight 600, `#0B0F14`, then a "|" divider at 40% opacity, then "Reviewed by Jack McKay, Risk Manager".
- Right column: `assets/gold-forecast-hero.jpeg`, 480×400, object-fit cover, bottom-aligned.
- Below the hero: a **6px** gradient bar, `linear-gradient(90deg,#3EB86B 0%,#3EB86B 45%,#6C5CE7 100%)`.

### 3. Article meta strip
- 20px vertical padding, bottom border `1px #ECEFEE`.
- Left:
  - "6 min read" chip: Poppins 12px/600, `#1F7A45` on `#E4F7EC`, padding 6px 12px, radius 20px.
  - 14px `#5B6560` text: "Refreshed after each Fed meeting or major bank target change".
- Right: a 32px circular avatar and "Eightcap Market Analysts" at 14px.

### 4. Sidebar (sticky, `top:112px`, padding-top 56px)
- "IN THIS ARTICLE" label: Poppins 12px/600 uppercase, `#5B6560`.
- Table-of-contents links:
  - Left rail: 2px `#ECEFEE`.
  - Each link: 14px `#2B3A32`, padding `8px 0 8px 16px`.
  - Hover: a 2px `#3EB86B` left border and text in `#0B0F14`.
  - Links: Gold news · Gold price today · Historical performance · Bank and analyst predictions · Sentiment in the news · Eightcap's scenarios · How to use forecasts · Disclaimer · FAQ.
  - *Enhancement:* highlight the active section on scroll (IntersectionObserver).
- CTA card: background `#F4F6F5`, 3px `#3EB86B` top border, 20px padding, 32px top margin.
  - Title "Follow the gold price live" (Poppins 15px/600).
  - Text "XAUUSD on TradingView, MT4, MT5 and TradeLocker." (13px `#5B6560`).
  - Button "View live chart" (`#6C5CE7`, 13px/600, padding 9px 16px, radius 20px) linking to `/en-au/traders/trade/xauusd/`.

### 5. Main column sections, in order
Shared styles:
- **H2:** Poppins 36px/600, line-height 1.15, letter-spacing -0.015em, 20px bottom margin.
- **H3:** Poppins 22–24px/600.
- **Body:** DM Sans 18px, line-height 1.75, `#1B2620`.
- **Small labels:** Poppins 12px/600, uppercase, .08em tracking.

1. **"Before you read" box** (`#summary`): background `#F4F6F5`, 3px `#3EB86B` top border, padding 32px 36px. It holds a 16px paragraph, then a 1px `#E1E5E3` divider, then a 15px "**Remember:** …" line.
2. **Gold news** (`#news`): intro paragraph with two internal links, then a list of dated rows.
   - Row grid: `110px 1fr`, 24px gap, padding 20px 0, 1px `#E4E7E6` dividers.
   - Date: Poppins 14px/600 `#1F7A45`.
   - Text: 16px. Below it, "Source: …" at 13px `#8A938E`.
   - There are 5 rows; content is in `news[]`.
3. **Gold price today** (`#today`): paragraph, then a 3-cell stat grid.
   - Grid: `1.3fr 1fr 1fr`, 1px `#E4E7E6` gaps and border.
   - Cell 1 (dark, `#0B0F14`, white text): label "XAUUSD · [date, time]" in `#3EE07F`, then the price in Poppins 36px/600, then a "Live price →" link.
   - Cells 2 and 3 (white): "Record high $5,405" in `#1F7A45` (29 Jan 2026, LBMA PM) and "2026 low so far ~$3,943" (30 Jun 2026), each with a 13px caption.
   - Footnote: 13px `#8A938E`.
4. **Historical gold price performance** (`#history`):
   - Paragraph.
   - Two-column table (2010–2017 | 2018–2025):
     - Header row: `#0B0F14` with white Poppins 13px/600 text ("Year" / "Avg (USD/oz)").
     - Rows: 15px, padding 11px 20px, zebra `#FAFBFA`.
     - **2015 and 2025 highlighted** with `#E4F7EC` and bold text.
     - Use tabular numbers.
   - H3 "Turning points", then a vertical timeline:
     - 2px `#D7F5E2` rail, 12px `#3EB86B` dots.
     - Each point: label in Poppins 15px/600 `#1F7A45`, then a 16px paragraph.
     - 5 points, in `turns[]`.
   - Closing line with the recession article link.
5. **Inline image:** `assets/gold-forecast-2.jpeg`, full main-column width, 360px tall, object-fit cover.
6. **Gold price predictions from banks and analysts** (`#analysts`):
   - Two paragraphs.
   - Forecast table with 4 columns: Source 22% · Figure 22% · Horizon 38% · Type 18%.
     - Header: `#0B0F14` with white text.
     - Rows: zebra striping; cells padded 14px 16px.
     - Horizon cell: the horizon text, plus the "where found" source line underneath at 12px `#8A938E`.
     - Type is a pill: 11px Poppins 600, padding 4px 9px, radius 12px, no wrapping. Colours:
       - Base case: `#E4F7EC` / `#1F7A45`
       - Bull scenario: `#ECE9FD` / `#4B3BC4`
       - Third-party estimate: `#F4F0E2` / `#6B5512`
       - No target: `#EFF1F0` / `#5B6560`
     - 10 rows, in `forecasts[]`.
   - H3 "How targets changed in 2026", with 2 paragraphs.
   - H3 "What forecasts say about 2030", with 1 paragraph and a pull-quote (3px `#0B0F14` left border, padding-left 24px).
7. **Mid-article CTA band:** background `#D7F5E2`, padding 28px 32px, flex with a 28px gap.
   - Left: title "Follow gold with Eightcap" (Poppins 20px/600) and copy.
   - Right: a stacked pair of buttons.
     - Primary "View live gold chart" (`#6C5CE7`).
     - Secondary "Try a demo" (transparent, 1px `#0B0F14` border).
     - Both: radius 22px, 14px/600.
8. **Gold sentiment in the news** (`#sentiment`): 2 paragraphs (one links to Market Insights), then a positioning strip.
   - Strip: grid `auto 1fr`, 1px `#E4E7E6` border, padding 24px 28px.
   - It shows a "POSITIONING" label in `#1F7A45` and a 16px sentence ending in a grey source note.
9. **Eightcap's analysis: gold price scenarios** (`#scenarios`):
   - Paragraph with the economic calendar link.
   - Three equal cards (16px gap) with a 1px `#E4E7E6` border and a 3px top border in the accent colour:
     - Bull: `#3EB86B` (label text `#1F7A45`)
     - Base: `#0B0F14`
     - Bear: `#6C5CE7`
   - Each card contains:
     - The label.
     - A name (Poppins 19px/600).
     - "What would have to be true", then text.
     - "What to watch", then text.
     - Pinned to the bottom, after a divider: "EIGHTCAP RANGE, END-2027 / 2030" and the value **[Eightcap analyst to supply]** in `#6C5CE7`.
   - Two paragraphs follow the cards.
10. **Inline image:** `assets/gold-forecast-3.jpeg`, 360px tall.
11. **How to use gold forecasts** (`#use`): paragraph with the risk and trading-plan links, then 3 tip tiles.
    - Tile: `#F4F6F5`, padding 22px 20px, 12px gap between tiles.
    - Number "01–03" in Poppins 28px/600 `#3EB86B`, a 16px/600 title, and 14px `#5B6560` body text.
12. **Awards callout** (`#eightcap`, reuse the site component if one exists): `#F4F6F5`, 3px `#3EB86B` top border, padding 34px 36px.
    - Left: "Trade gold with Eightcap" (Poppins 24px), regulation copy, and a "Create an account" pill (`#6C5CE7`, padding 13px 26px, radius 24px, hover `#5B4BD6`).
    - Right: three **108px** circular award badges (`#D7F5E2` background, `#1F7A45` text). **Replace these with the real award artwork.**
13. **Disclaimer** (`#disclaimer`): 1px `#0B0F14` border, padding 28px 32px, "DISCLAIMER" label, 15px body. Use the compliance-approved wording, shown in the reference.
14. **FAQ** (`#faq`): "GOLD FORECASTS" eyebrow, then the H2 "Frequently asked questions", then a 3-item accordion.
    - Question button: Poppins 18px/500, padding 20px 0, full width.
    - The "+" icon is `#3EB86B` at 22px and rotates 45° when open (160ms ease).
    - Answer: 16px `#5B6560`, right padding 60px.
    - The first item is open by default, and only one item is open at a time.
    - **Add FAQPage JSON-LD that matches the visible text.**
15. **Reviewed by** (reuse the blog author component):
    - "Reviewed by" chip: `#D7F5E2`, radius 6px.
    - 112×130 headshot, radius 6px.
    - "**Jack McKay** | Risk Manager, Eightcap" (Poppins 20px).
    - Bio, with "[Eightcap analyst name]" as the contributor.
16. **Keep reading on gold:** H2 and subcopy, then 3 cards (grid of 3, 20px gap).
    - Card: 1px `#E4E7E6` border, 150px image, tag chip (`#E4F7EC` / `#1F7A45`), title (Poppins 17px/600), and a 14px blurb.
    - The whole card is a link.
17. **Closing CTA band:** `#D7F5E2`, padding 30px 34px.
    - "Ready to trade gold?" and copy with the commodity CFDs link.
    - Buttons "Create an account" (primary) and "Open a demo account" (outline).

### 6. Footer (reuse the existing site footer)
- Black background, padding 64px 48px 40px.
- Five columns (`1.6fr 1fr 1fr 1fr 1fr`, 40px gap): Company information, Company, Go to, Legal, Follow us.
- A centred white wordmark, max 520px wide.
- The risk warning, including the PDS/FSG/TMD reference.

## Interactions and behaviour
- Table-of-contents anchors use smooth scrolling. Sections have `scroll-margin-top: 90px` so they clear the sticky header.
- The sidebar is `position: sticky; top: 112px`.
- FAQ accordion: one item open at a time, the first item open by default, `aria-expanded` on the button, and the + icon rotates 45°.
- Hover states:
  - Links: `#1F7A45`, changing to `#0B0F14` on hover. Underline at 1px thickness with a 2px offset.
  - Primary buttons darken to `#5B4BD6`.
  - Table-of-contents links get the green rail.
- No loading or error states. There are no forms on this page.

## Responsive (not yet designed)
Mobile is to be designed and approved separately. Follow the same adaptations as the crude oil mobile page:
- Hamburger menu.
- Stacked, full-bleed hero.
- The table of contents becomes a collapsible "In this article".
- Tables become cards or scroll horizontally.
- Grids stack to one column.
- A sticky bottom CTA bar.
- 44px tap targets.

## Data and state
Keep this content in the CMS or a data file so it can be refreshed monthly:
- `lastUpdated`, `reviewer`, `contributor`
- `priceToday { price, time, date, ytdChange, source }`, `recordHigh`, `yearLow`
- `news[] { date, text, source }`
- `annualAverages[] { year, avgUsdOz, highlight }`
- `turningPoints[] { when, text }`
- `forecasts[] { source, figure, horizon, whereFound, type }`, where `type` is one of: Base case | Bull scenario | Third-party estimate | No target
- `scenarios[] { label, name, mustBeTrue, watch, eightcapRange }`
- `faqs[] { q, a }` (this also feeds the FAQPage schema)

The only UI state is `openFaqIndex` (default 0, -1 means none open).

## Design tokens
**Colours**
- Ink: `#0B0F14`. Body text: `#1B2620` and `#2B3A32`. Muted: `#5B6560`. Faint: `#8A938E`. Breadcrumb: `#3E5A4A`.
- Green: `#3EB86B`. Green text: `#1F7A45`. Green on dark: `#3EE07F`.
- Mint background: `#D7F5E2`. Mint chip: `#E4F7EC`.
- Purple CTA: `#6C5CE7`, hover `#5B4BD6`. Purple chip: `#ECE9FD` / `#4B3BC4`.
- Grey surface: `#F4F6F5`. Zebra row: `#FAFBFA`. Borders: `#E4E7E6`, `#ECEFEE`, `#E1E5E3`. Login pill: `#EFF1F0`.
- Footer: `#000`, with text in `#9AA09D` and `#8F958F`, and a `#262A28` rule.

**Type**
- Headings: Poppins 400/500/600/700. Body: DM Sans 400/500/700 (both from Google Fonts).
- Sizes: H1 40, H2 36, H3 22–24, card title 16–20, body 18, secondary 16/15/14, small 13, label 12/11.

**Spacing**
- Section gap 56. Container padding 48. Sidebar/main gap 80. Card padding 20–36. Grid gaps 12/16/20/24.

**Radii**
- Pill buttons 20–24. Chips 12–20. Author image 6. Everything else is sharp (0).

**Shadows:** none on this page.

## Assets
- `assets/gold-forecast-hero.jpeg`: hero image (gold bars with an XAU/USD screen). Supplied by the client.
- `assets/gold-forecast-2.jpeg`: inline image after the history section.
- `assets/gold-forecast-3.jpeg`: inline image after the scenarios section.
- `assets/related-article.jpeg`: used for all three related cards in the mock. Swap in each article's real featured image.
- `assets/eightcap-wordmark.png` and `eightcap-wordmark-white.png`: use the brand logo files from the codebase if they exist.
- Avatar, reviewer headshot and award badges are placeholders. Use the real assets.
- Check the licensing on the supplied stock images before going live.

## Open items before publishing
- `$[price]`, `[time]`, `[date]`, `[x]%`, YTD change and source on the day of publishing.
- Eightcap scenario ranges and the analyst's name (from the Eightcap analyst).
- Verify every bank and analyst figure against its primary source, and remove anything that can't be confirmed (per the content brief).
- Confirm the reviewer byline and the demo account URL.
- Compliance sign-off on the disclaimer and whether the AU version needs a stronger general advice statement.

## Internal links used
- `/en-au/traders/trade/xauusd/`
- `/en-au/traders/insights/blogs/what-drives-the-price-of-gold/`
- `/en-au/traders/insights/blogs/nfps-effect-on-gold-prices/`
- `/en-au/traders/insights/blogs/what-happens-to-the-value-of-gold-during-a-recession/`
- `/en-au/traders/insights/blogs/how-to-trade-gold/`
- `/en-au/traders/knowledge-hub/economic-calendar/`
- `/en-au/traders/knowledge-hub/market-insights/`
- `/en-au/traders/insights/blogs/how-to-manage-risk-while-trading-cfds/`
- `/en-au/traders/insights/blogs/trading-plan-what-you-need-to-know/`
- `/en-au/traders/markets/commodities/`
