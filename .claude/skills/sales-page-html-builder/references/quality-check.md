# Quality Check

Run through this checklist before confirming delivery. Fix any issues found before saving the file.

---

## Structure

- [ ] Page opens with `<!DOCTYPE html>` and a valid `<html lang="en">` tag
- [ ] `<head>` contains the Google Fonts link and all CSS inside a `<style>` block
- [ ] No `<header>` or `<footer>` tags — pages are pasted into Divi and must not include site-level chrome
- [ ] All sections are inside `<body>`, in logical reading order
- [ ] Page title is set: `<title>[Offer Name] | Your Web Toolkit</title>`

## Design system

- [ ] All colours reference CSS variables (e.g. `var(--teal)`) — no hardcoded hex values except in the `:root` block
- [ ] Google Fonts import is present and includes Josefin Sans, Playfair Display, and Lato
- [ ] Hero section has teal background and white text
- [ ] Footer CTA section has teal background and white text
- [ ] CTA strip sections have teal background with dot-grid overlay
- [ ] Section labels have the amber highlight gradient applied (the `section-label` class)

## Background alternation

- [ ] No two adjacent non-teal sections share the same background colour
- [ ] Hero, CTA strips, and footer CTA are teal — this is correct and expected
- [ ] All other sections alternate between `var(--white)` and `var(--light-grey)` in sequence

## Copy accuracy

- [ ] All copy is taken verbatim from the input — nothing rewritten, summarised, or invented
- [ ] Any placeholder text from the input (e.g. `[client name]`, `[price TBC]`) is preserved and wrapped in: `<!-- PLACEHOLDER: replace before publishing -->`
- [ ] No copy has been left out — all sections from the input are represented in the HTML

## CTAs and links

- [ ] All CTA buttons point to `https://yourwebtoolkit.com/contact/` (unless a specific checkout URL was provided in the copy)
- [ ] All `<a>` tags have valid `href` values — no `#`, `javascript:void(0)`, or empty hrefs

## Responsive

- [ ] 2-column grids collapse to 1 column at 768px (via `.two-col`, `.three-col` media queries)
- [ ] Pain grid collapses at 700px
- [ ] FAQ grid collapses at 768px
- [ ] `btn-amber` and `btn-teal` go full-width at 600px

## Final check

- [ ] File is self-contained — no external CSS file references, all styles inline in `<style>` block
- [ ] No broken or mismatched HTML tags (every `<div>` has a closing `</div>`)
- [ ] No placeholder images left without a comment indicating they need replacing
