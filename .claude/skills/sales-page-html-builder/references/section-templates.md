# Section Templates

HTML patterns for each section type. Use these as the structural scaffolding — slot in the actual copy from the input. Background colour (`var(--white)` or `var(--light-grey)`) is assigned dynamically per the alternation rule in SKILL.md.

Where you see `[COPY]`, replace with the matching copy from the input. Never fabricate copy.

---

## HERO

Always teal. First section on every page.

```html
<!-- HERO -->
<section class="hero">
  <div style="max-width: 860px; margin: 0 auto;">
    <span class="section-label">[label line if present, e.g. "Done-For-You SEO"]</span>
    <h1>[Main headline / offer name]</h1>
    <h2>[Subheading / supporting statement]</h2>
    <p>[Subtitle paragraph if present]</p>
    <div style="margin-top: 40px;">
      <a href="https://yourwebtoolkit.com/contact/" class="btn-amber">[CTA text, e.g. "Apply Now" or "Book a Call"]</a>
    </div>
  </div>
</section>
```

Note: Omit the `<span class="section-label">` if no label line is present. Omit `<h2>` or `<p>` if the copy doesn't include them.

---

## PAIN / PROBLEM SECTION

Dynamic background (white or light-grey based on position). Uses a 2-column card grid. Each pain point gets a card with a teal icon circle.

```html
<!-- PAIN SECTION -->
<section style="background: [BG];">
  <div class="container">
    <div class="pain-intro">
      <span class="section-label">[label, e.g. "Sound familiar?"]</span>
      <h2>[Intro heading]</h2>
      <p>[Optional intro paragraph]</p>
    </div>
    <div class="pain-grid">

      <div class="pain-card">
        <div class="pain-card-header">
          <div class="pain-icon">
            <svg viewBox="0 0 24 24"><circle cx="12" cy="12" r="10"/></svg>
          </div>
          <h3>[Pain point heading]</h3>
        </div>
        <p>[Pain point description]</p>
      </div>

      <!-- Repeat .pain-card for each pain point -->

    </div>
  </div>
</section>
```

If the copy has a simple bullet list of pain points rather than named cards, use this simpler variant:

```html
<section style="background: [BG];">
  <div class="container">
    <div class="pain-intro">
      <span class="section-label">[label]</span>
      <h2>[Intro heading]</h2>
    </div>
    <ul style="max-width: 700px; margin: 0 auto; list-style: none;">
      <li style="padding: 14px 0 14px 28px; border-bottom: 1px solid var(--mid-grey); position: relative;">
        <span style="position: absolute; left: 0; color: var(--teal); font-weight: 700;">→</span>
        [Pain point]
      </li>
      <!-- Repeat li for each point -->
    </ul>
  </div>
</section>
```

---

## CTA STRIP

Always teal. Use between sections where the copy has a short punchy bridge statement (1–3 sentences max). Does not count toward background alternation.

```html
<!-- CTA STRIP -->
<section class="cta-strip">
  <div class="dot-grid"></div>
  <p>[Bridge line 1]</p>
  <p>[Bridge line 2 if present]</p>
</section>
```

---

## WHAT IT IS / SOLUTION (Two-column content cards)

Dynamic background. Use two-column card layout with left-border accent. Good for "here's what this includes at a high level" or "here's the approach".

```html
<!-- WHAT IT IS -->
<section style="background: [BG]; position: relative; overflow: hidden;">
  <div class="dot-cluster dot-cluster--tl"></div>
  <div class="dot-cluster dot-cluster--br"></div>
  <div class="container" style="position: relative; z-index: 1;">
    <div style="text-align: center; margin-bottom: 48px;">
      <span class="section-label">[label, e.g. "What it is"]</span>
      <h2>[Section heading]</h2>
      <p>[Optional intro paragraph]</p>
    </div>
    <div class="two-col">
      <div class="content-card">
        <h3>[Card heading]</h3>
        <p>[Card copy]</p>
      </div>
      <div class="content-card">
        <h3>[Card heading]</h3>
        <p>[Card copy]</p>
      </div>
      <!-- Add more cards as needed — they'll wrap in 2-col grid -->
    </div>
  </div>
</section>
```

For 3-column layout (e.g. 3 pillars), use `class="three-col"` instead.

---

## CASE STUDY

Dynamic background. Use the bordered card pattern with a label, heading, and story copy. Add photo only if a real image URL is provided.

```html
<!-- CASE STUDY -->
<section style="background: [BG];">
  <div class="container">
    <span class="section-label">[label, e.g. "In practice"]</span>
    <h2>[Section heading if present]</h2>

    <div class="case-study">
      <span class="case-study-label">Case Study</span>
      <h3><span class="highlight-label">[Client description / win headline]</span></h3>
      <p>[Case study copy]</p>
      <!-- If photo URL available: -->
      <!-- <img src="[URL]" alt="[name]" class="case-photo" style="margin-top: 24px;"> -->
      <!-- If no photo: omit -->
    </div>

    <!-- Add more .case-study divs for additional client stories -->
  </div>
</section>
```

---

## OUTCOMES / WHAT CHANGES

Dynamic background. Use outcome item cards in a 2-column grid. Each item has a teal top border and an SVG icon.

```html
<!-- OUTCOMES -->
<section style="background: [BG]; text-align: center;">
  <div class="container">
    <span class="section-label">[label, e.g. "What becomes possible"]</span>
    <h2>[Section heading]</h2>
    <p>[Optional intro]</p>
    <div class="outcomes-grid">

      <div class="outcome-item">
        <div class="outcome-icon">
          <svg viewBox="0 0 24 24" width="32" height="32" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"/></svg>
        </div>
        <h3>[Outcome heading]</h3>
        <p>[Outcome description]</p>
      </div>

      <!-- Repeat .outcome-item for each outcome -->

    </div>
  </div>
</section>
```

---

## WHAT'S INCLUDED / DELIVERABLES

Dynamic background. Use numbered deliverable items. Each item has a large serif number in teal.

```html
<!-- DELIVERABLES -->
<section style="background: [BG];">
  <div class="container">
    <div style="text-align: center; margin-bottom: 48px;">
      <span class="section-label">[label, e.g. "What's included"]</span>
      <h2>[Section heading]</h2>
    </div>

    <div class="deliverable-item">
      <div class="deliverable-num">01</div>
      <div class="deliverable-content">
        <h3>[Deliverable name]</h3>
        <p>[Deliverable description]</p>
      </div>
    </div>

    <!-- Repeat .deliverable-item, incrementing number: 02, 03, etc. -->

  </div>
</section>
```

If the copy is a bullet list rather than named deliverables, use a styled checklist instead:

```html
<ul class="includes-list" style="max-width: 700px; margin: 32px auto 0;">
  <li>[Item]</li>
  <!-- Repeat -->
</ul>
```

---

## HOW IT WORKS / PROCESS

Dynamic background. Use phase cards — white cards on a light-grey background, or vice versa.

```html
<!-- HOW IT WORKS -->
<section style="background: [BG];">
  <div class="container">
    <div style="text-align: center; margin-bottom: 8px;">
      <span class="section-label">[label, e.g. "How it works"]</span>
      <h2>[Section heading]</h2>
    </div>

    <div class="phase-card">
      <div class="phase-num">1</div>
      <div>
        <h3>[Phase name]</h3>
        <p>[Phase description]</p>
      </div>
    </div>

    <!-- Repeat .phase-card for each step -->

  </div>
</section>
```

---

## IS THIS FOR YOU?

Dynamic background. Two-column layout: "This is for you if…" and "This is NOT for you if…". Use only the columns present in the copy.

```html
<!-- IS THIS FOR YOU -->
<section style="background: [BG];">
  <div class="container">
    <div style="text-align: center; margin-bottom: 48px;">
      <span class="section-label">[label, e.g. "Who this is for"]</span>
      <h2>[Section heading]</h2>
    </div>
    <div class="fit-grid">
      <div class="fit-column">
        <h3 style="color: var(--teal);">This is for you if…</h3>
        <ul class="fit-list fit-list--yes">
          <li>[Fit criterion]</li>
          <!-- Repeat -->
        </ul>
      </div>
      <div class="fit-column">
        <h3 style="color: #999;">This is NOT for you if…</h3>
        <ul class="fit-list fit-list--no">
          <li>[Not-a-fit criterion]</li>
          <!-- Repeat -->
        </ul>
      </div>
    </div>
  </div>
</section>
```

If only one column is present in the copy, render a single column at `max-width: 600px; margin: 0 auto;` instead of the two-column grid.

---

## INVESTMENT / PRICING

Dynamic background. Centred price box.

```html
<!-- INVESTMENT -->
<section style="background: [BG]; text-align: center;">
  <div class="container">
    <span class="section-label">[label, e.g. "Investment"]</span>
    <h2>[Section heading]</h2>
    <p>[Optional intro copy]</p>

    <div class="price-box">
      <div class="price">[Price, e.g. £1,000]</div>
      <p class="price-sub">[Payment terms, e.g. "or 3 payments of £367"]</p>
      <ul class="includes-list">
        <li>[Included item]</li>
        <!-- Repeat -->
      </ul>
      <a href="https://yourwebtoolkit.com/contact/" class="btn-amber">[CTA text]</a>
    </div>
  </div>
</section>
```

If a checkout URL is specified in the copy, use that URL for the CTA button instead of the contact page.

---

## TESTIMONIAL / SOCIAL PROOF (standalone block)

Dynamic background. Use when a testimonial appears on its own (not embedded in a case study).

```html
<!-- TESTIMONIAL -->
<div class="testimonial-block" style="background: [BG];">
  <div class="teal-line"></div>
  <blockquote>[Testimonial quote]</blockquote>
  <cite>— [Name, title/context if provided]</cite>
</div>
```

---

## FAQ

Dynamic background. Two-column grid.

```html
<!-- FAQ -->
<section style="background: [BG];">
  <div class="container">
    <div style="text-align: center; margin-bottom: 8px;">
      <span class="section-label">FAQs</span>
      <h2>[Section heading if present, otherwise omit]</h2>
    </div>
    <div class="faq-grid">

      <div class="faq-item">
        <h4>[Question]</h4>
        <p>[Answer]</p>
      </div>

      <!-- Repeat .faq-item for each Q&A pair -->

    </div>
  </div>
</section>
```

---

## FOOTER CTA

Always teal. Final section on every page.

```html
<!-- FOOTER CTA -->
<section class="footer-cta">
  <div style="max-width: 720px; margin: 0 auto;">
    <h2>[Closing headline]</h2>
    <p>[Closing copy if present]</p>
    <a href="https://yourwebtoolkit.com/contact/" class="btn-amber">[CTA text]</a>
  </div>
</section>
```

---

## Background values to use

When the alternation logic assigns a background to a section, use exactly one of these:

- White: `background: var(--white);`
- Light grey: `background: var(--light-grey);`
