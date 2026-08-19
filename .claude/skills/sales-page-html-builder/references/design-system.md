# Design System — Brand CSS

Embed this CSS verbatim inside a `<style>` block in the `<head>` of every generated page.

---

## Google Fonts Import

```html
<link href="https://fonts.googleapis.com/css2?family=Josefin+Sans:wght@300;400;600;700&family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=Lato:wght@300;400;700&display=swap" rel="stylesheet">
```

---

## Full CSS

```css
html { font-size: 18px; }

:root {
  --teal: #1D9ABC;
  --teal-dark: #157d8a;
  --amber: #ffbd4a;
  --amber-dark: #d9a030;
  --charcoal: #2d2d2d;
  --body-text: #444;
  --light-grey: #f4f4f2;
  --mid-grey: #e8e8e4;
  --white: #ffffff;
  --serif: 'Playfair Display', Georgia, serif;
  --sans: 'Lato', sans-serif;
  --heading: 'Josefin Sans', sans-serif;
}

* { margin: 0; padding: 0; box-sizing: border-box; }

body {
  font-family: var(--sans);
  color: var(--body-text);
  line-height: 1.7;
  font-size: 18px;
}

/* ── TYPOGRAPHY ── */
h1 {
  font-family: var(--heading);
  font-size: 54px;
  font-weight: 700;
  line-height: 1.15;
  margin-bottom: 20px;
}
h2 {
  font-family: var(--serif);
  font-size: 44px;
  font-weight: 400;
  color: var(--charcoal);
  line-height: 1.25;
  margin-bottom: 20px;
}
h3 {
  font-family: var(--serif);
  font-size: 1.35rem;
  font-weight: 400;
  color: var(--charcoal);
  margin-bottom: 10px;
}
h4 {
  font-family: var(--sans);
  font-size: 1rem;
  font-weight: 700;
  color: var(--charcoal);
  margin-bottom: 8px;
}
p { margin-bottom: 16px; }
p:last-child { margin-bottom: 0; }

/* ── SECTION LABEL ── */
.section-label {
  font-size: 14px;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  color: var(--charcoal);
  margin-bottom: 16px;
  display: inline-block;
  background: linear-gradient(transparent 40%, rgba(255, 189, 74, 0.7) 40%);
  padding: 0 6px 5px 6px;
}

/* ── LAYOUT ── */
section { padding: 80px 40px; }
.container { max-width: 900px; margin: 0 auto; }
.container-wide { max-width: 1100px; margin: 0 auto; }
.center { text-align: center; }
.mt-8 { margin-top: 32px; }
.mt-12 { margin-top: 48px; }

/* ── BUTTONS ── */
.btn-amber {
  display: inline-block;
  background: var(--amber);
  color: white;
  font-family: var(--sans);
  font-size: 12px;
  font-weight: 700;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  padding: 16px 40px;
  text-decoration: none;
  box-shadow: 0 2px 0 rgba(0,0,0,0.15);
}
.btn-amber:hover { background: var(--amber-dark); }

.btn-teal {
  display: inline-block;
  background: var(--teal);
  color: white;
  font-family: var(--sans);
  font-size: 12px;
  font-weight: 700;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  padding: 16px 40px;
  text-decoration: none;
}
.btn-teal:hover { background: var(--teal-dark); }

/* ── GRIDS ── */
.two-col {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 40px;
  margin-top: 20px;
}
.three-col {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 40px;
  margin-top: 48px;
}
@media (max-width: 768px) {
  .two-col { grid-template-columns: 1fr !important; }
  .three-col { grid-template-columns: 1fr; }
}

/* ── HERO ── */
.hero {
  background: var(--teal);
  color: white;
  text-align: center;
  padding: 80px 40px 100px;
  position: relative;
}
.hero h1 {
  font-family: var(--heading);
  font-size: clamp(2.2rem, 5vw, 3.4rem);
  font-weight: 700;
  color: white;
  line-height: 1.2;
  margin-bottom: 24px;
}
.hero h2 {
  font-family: var(--serif);
  font-size: clamp(1.4rem, 3vw, 2rem);
  font-weight: 400;
  color: white;
  max-width: 800px;
  margin: 0 auto 24px;
  line-height: 1.35;
}
.hero p {
  font-size: 1.1rem;
  opacity: 0.85;
  max-width: 620px;
  margin: 20px auto 0;
  font-weight: 300;
}
.hero .section-label {
  color: white;
  background: linear-gradient(transparent 40%, rgba(255, 189, 74, 0.7) 40%);
}

/* ── CTA STRIP ── */
.cta-strip {
  background: var(--teal);
  padding: 60px 40px;
  text-align: center;
  position: relative;
  overflow: hidden;
}
.cta-strip::before {
  content: '';
  position: absolute;
  top: -80px; right: -80px;
  width: 320px; height: 320px;
  border-radius: 50%;
  background: rgba(255,255,255,0.06);
  pointer-events: none;
}
.cta-strip::after {
  content: '';
  position: absolute;
  bottom: -100px; left: -60px;
  width: 280px; height: 280px;
  border-radius: 50%;
  background: rgba(255,255,255,0.05);
  pointer-events: none;
}
.cta-strip .dot-grid {
  position: absolute;
  inset: 0;
  background-image: radial-gradient(rgba(255,255,255,0.12) 1px, transparent 1px);
  background-size: 28px 28px;
  pointer-events: none;
}
.cta-strip p {
  font-family: var(--sans);
  font-size: clamp(1.15rem, 2.5vw, 1.5rem);
  color: white;
  max-width: 720px;
  margin: 0 auto;
  line-height: 1.7;
  position: relative;
}
.cta-strip p + p { margin-top: 20px; }

/* ── DOT CLUSTERS ── */
.dot-cluster {
  position: absolute;
  width: 90px;
  height: 110px;
  background-image: radial-gradient(circle, #1E9ABC 2.5px, transparent 2.5px);
  background-size: 20px 20px;
  opacity: 0.13;
  pointer-events: none;
  z-index: 0;
}
.dot-cluster--tl { top: 24px; left: 24px; }
.dot-cluster--tr { top: 24px; right: 24px; }
.dot-cluster--bl { bottom: 24px; left: 24px; }
.dot-cluster--br { bottom: 24px; right: 24px; }

/* ── PAIN SECTION ── */
.pain-intro { max-width: 700px; margin: 0 auto 48px; text-align: center; }
.pain-intro h2 { font-size: 1.6rem; }
.pain-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 40px;
}
.pain-card { display: flex; flex-direction: column; gap: 12px; }
.pain-card-header { display: flex; align-items: center; gap: 12px; }
.pain-icon {
  width: 44px; height: 44px;
  background: var(--teal);
  border-radius: 50%;
  display: flex; align-items: center; justify-content: center;
  flex-shrink: 0;
}
.pain-icon svg { width: 22px; height: 22px; fill: white; }
.pain-card h3 {
  font-family: var(--serif);
  font-size: 1.1rem;
  font-weight: 400;
  color: var(--charcoal);
  margin: 0;
}
.pain-card p { color: var(--body-text); margin: 0; }
@media (max-width: 700px) { .pain-grid { grid-template-columns: 1fr; } }

/* ── CONTENT CARDS (What it is / Solution) ── */
.content-card {
  background: var(--white);
  border-left: 4px solid var(--teal);
  padding: 32px 36px;
}
.content-card--amber { border-left-color: var(--amber); }
.content-card h3 {
  font-family: var(--heading);
  font-size: 0.75rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.15em;
  color: var(--teal);
  margin-bottom: 12px;
}
.content-card--amber h3 { color: var(--amber); }

/* ── CASE STUDY ── */
.case-study {
  border-left: 4px solid var(--teal);
  padding: 32px 36px;
  margin-top: 48px;
  border-radius: 0 4px 4px 0;
}
.case-study-label {
  font-size: 12px;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  color: var(--teal);
  font-weight: 700;
  margin-bottom: 12px;
  display: block;
}
.case-study h3 { font-size: 1.3rem; margin-bottom: 16px; }
.highlight-label {
  background: linear-gradient(transparent 40%, rgba(255, 189, 74, 0.7) 40%);
  padding: 0 4px 5px 4px;
  display: inline;
}
.case-photo {
  width: 180px; height: 180px;
  border-radius: 50%;
  filter: grayscale(100%);
  border: 4px solid var(--light-grey);
  object-fit: cover;
}

/* ── OUTCOMES GRID ── */
.outcomes-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 30px;
  margin-top: 48px;
}
.outcome-item {
  padding: 28px;
  background: var(--white);
  border-top: 3px solid var(--teal);
}
.outcome-icon { margin-bottom: 16px; color: var(--teal); }
.outcome-icon svg { width: 32px; height: 32px; display: block; }
@media (max-width: 768px) { .outcomes-grid { grid-template-columns: 1fr; } }

/* ── DELIVERABLES / NUMBERED ITEMS ── */
.deliverable-item {
  display: flex;
  gap: 28px;
  align-items: flex-start;
  padding: 32px 0;
  border-bottom: 1px solid var(--mid-grey);
}
.deliverable-num {
  font-family: var(--serif);
  font-size: 3.5rem;
  color: var(--teal);
  line-height: 1;
  flex-shrink: 0;
  font-weight: 700;
  min-width: 48px;
}
.deliverable-content h3 { font-size: 1.1rem; margin-bottom: 8px; }

/* ── PROCESS / PHASES ── */
.phase-card {
  display: flex;
  gap: 28px;
  align-items: flex-start;
  background: var(--white);
  padding: 32px 36px;
  border-radius: 4px;
  margin-bottom: 20px;
}
.phase-num {
  font-family: var(--serif);
  font-size: 3rem;
  color: var(--teal);
  line-height: 1;
  flex-shrink: 0;
  font-weight: 700;
}
.phase-card h3 { font-size: 1.1rem; margin-bottom: 12px; }
.phase-card ul { list-style: none; margin-top: 10px; }
.phase-card ul li { padding: 4px 0 4px 20px; position: relative; }
.phase-card ul li::before { content: '→'; position: absolute; left: 0; top: 4px; color: var(--teal); }

/* ── IS THIS FOR YOU ── */
.fit-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 40px;
  margin-top: 48px;
}
.fit-column h3 {
  font-family: var(--heading);
  font-size: 0.85rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.15em;
  margin-bottom: 20px;
}
.fit-list { list-style: none; }
.fit-list li {
  padding: 10px 0 10px 28px;
  position: relative;
  border-bottom: 1px solid var(--mid-grey);
}
.fit-list--yes li::before { content: '✓'; position: absolute; left: 0; color: var(--teal); font-weight: 700; }
.fit-list--no li::before { content: '✗'; position: absolute; left: 0; color: #999; font-weight: 700; }
@media (max-width: 768px) { .fit-grid { grid-template-columns: 1fr; } }

/* ── INVESTMENT / PRICING ── */
.price-box {
  background: var(--white);
  border: 1px solid var(--mid-grey);
  padding: 48px;
  max-width: 620px;
  margin: 48px auto;
}
.price {
  font-family: var(--serif);
  font-size: 3rem;
  margin-bottom: 8px;
  color: var(--charcoal);
}
.price-sub { opacity: 0.8; margin-bottom: 32px; }
.includes-list { list-style: none; text-align: left; margin-bottom: 36px; }
.includes-list li {
  list-style: none;
  padding: 10px 0 10px 28px;
  border-bottom: 1px solid var(--mid-grey);
  position: relative;
}
.includes-list li::before { content: '✅'; position: absolute; left: 0; }

/* ── TESTIMONIAL ── */
.testimonial-block {
  padding: 48px 40px;
  text-align: center;
}
.testimonial-block blockquote {
  font-family: var(--sans);
  font-size: clamp(0.95rem, 2vw, 1.2rem);
  color: var(--charcoal);
  max-width: 700px;
  margin: 0 auto 20px;
  line-height: 1.7;
}
.testimonial-block cite {
  font-size: 0.85rem;
  color: #777;
  font-style: normal;
  letter-spacing: 0.05em;
}
.teal-line {
  width: 40px;
  height: 2px;
  background: var(--amber);
  margin: 0 auto 24px;
}

/* ── FAQ ── */
.faq-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 40px;
  margin-top: 48px;
}
.faq-item { padding-bottom: 24px; border-bottom: 1px solid var(--mid-grey); }
.faq-item h4 { font-family: var(--sans); font-weight: 700; color: var(--charcoal); margin-bottom: 8px; }
.faq-item p { color: #666; margin-bottom: 0; }
@media (max-width: 768px) { .faq-grid { grid-template-columns: 1fr; } }

/* ── FOOTER CTA ── */
.footer-cta {
  background: var(--teal);
  text-align: center;
  padding: 80px 40px;
  color: white;
}
.footer-cta h2 { color: white; font-size: clamp(1.5rem, 3.5vw, 2.4rem); margin-bottom: 16px; }
.footer-cta p { opacity: 0.85; margin-bottom: 36px; max-width: 620px; margin-left: auto; margin-right: auto; }

/* ── RESPONSIVE ── */
@media (max-width: 700px) {
  section { padding: 60px 24px; }
  .cta-strip { padding: 48px 24px; }
}
@media (max-width: 600px) {
  .hero h1 { font-size: 2rem; }
  .btn-amber, .btn-teal { display: block; text-align: center; }
}
```
