# VLA-Pilot Project Website

## Project Summary

This is a static academic research website for **VLA-Pilot**, a plug-and-play inference-time policy steering method for Vision-Language-Action (VLA) models in robotic manipulation.

**Paper:** "Towards Deploying VLA without Fine-Tuning: Plug-and-Play Inference-Time VLA Policy Steering via Embodied Evolutionary Diffusion"
**arXiv:** 2511.14178

**Authors:** Zhuo Li, Junjia Liu, Zhipeng Dong, Tao Teng, Quentin Rouxel, Darwin Caldwell, Fei Chen (corresponding)
**Affiliations:** The Chinese University of Hong Kong (CUHK), Istituto Italiano di Tecnologia (IIT)

**Key contribution:** Enables zero-shot deployment of pre-trained VLA policies (DiVLA, RDT-1B) on new downstream manipulation tasks without fine-tuning or data collection, achieving ~+0.30 MSR improvement on average across 6 real-world tasks and 2 robot embodiments.

## Tech Stack

- **HTML:** Single-page static site (`index.html`)
- **CSS:** Bulma CSS framework + custom `static/css/index.css`
- **JS:** jQuery, custom `static/js/index.js`, Bulma Carousel/Slider
- **Icons:** Font Awesome
- **Fonts:** Inter (Google Fonts)
- **Hosting:** GitHub Pages (`.nojekyll` present)
- **No build system** — edit files directly

## File Structure

```
vla-adapter/
├── index.html                      # Main and only HTML page
├── static/
│   ├── css/
│   │   ├── index.css               # Custom styles and design system
│   │   ├── bulma.min.css           # Bulma CSS framework
│   │   ├── bulma-carousel.min.css
│   │   └── bulma-slider.min.css
│   ├── js/
│   │   ├── index.js                # Dropdown, BibTeX copy, scroll-to-top
│   │   ├── bulma-carousel.js
│   │   └── bulma-slider.js
│   └── images/
│       ├── fig1.png                # VLA-Pilot overview diagram
│       ├── fig2.png                # Method overview (EPS-CoT + Evolutionary Diffusion)
│       ├── fig3.png, fig4.png      # Supporting figures
│       ├── fig5.png                # Qualitative results
│       ├── fig6.png                # Additional comparisons
│       ├── table1.png              # Main quantitative results
│       ├── table2.png              # OOD performance table
│       └── favicon.ico
```

## Page Sections (in order)

1. **Hero** — Title + IEEE RAL 2026 acceptance badge + author list + links
2. **Teaser Video** — YouTube embed (video ID: `iDiDtVhp4tI`)
3. **Abstract** — Research motivation + fig1.png
4. **Motivation** — Why fine-tuning is impractical + fig3.png
5. **Problem Formulation** — Formal inference-time steering problem setup
6. **Method Overview** — Expanded 3-step description (EPS-CoT, Evolutionary Diffusion, Iterative Refinement) + fig2.png
7. **Prompt Design Gallery** — System prompt, task context input, reasoning output cards
8. **Qualitative Results** — fig5.png
9. **Quantitative Results** — table1.png
10. **Video Presentation** — Second YouTube embed (`YOUR_VIDEO_ID` placeholder — replace with actual ID)
11. **Conclusion** — Summary of contributions and future directions
12. **Limitations** — 3-item bulleted list of known limitations
13. **Q&A** — 5-item collapsible accordion (pure CSS `<details>`/`<summary>`)
14. **BibTeX Citation** — Copyable citation block
15. **More Works Dropdown** (fixed top-right) — Related lab papers

## New CSS Classes (added)
- `.venue-badge` — acceptance badge pill under the title
- `.prompt-gallery` / `.prompt-card` / `.prompt-card.system|input|output` — colored prompt cards grid
- `details.qa-item` / `.qa-answer` — CSS-only accordion for Q&A (no JS required)

## Common Tasks

### Replace the Video Presentation YouTube ID
Search for `YOUR_VIDEO_ID` in `index.html` and replace with the actual YouTube video ID.

### Update the GitHub link
Search for `Coming soon` in `index.html` and replace the `href` on the GitHub button.

### Add a paper to "More Works" dropdown
Find the `<div class="works-list">` block (around line 195) and add a new `<a class="work-item">` entry following the existing pattern.

### Replace a figure
Drop the new image into `static/images/` with the same filename, or update the `src` attribute in `index.html`.

### Update the BibTeX citation
Find the `<pre id="bibtex-content">` block in `index.html` and edit the citation text.

### Local preview
```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

## Design System (index.css)

- **Primary color:** `#2563eb` (blue)
- **Accent:** `#0ea5e9` (cyan)
- **Text primary:** `#1e293b`
- **Background:** white / `#f8fafc` / `#f1f5f9`
- **Border radius:** 12px standard, 16px large
- **Transitions:** 0.3s cubic-bezier

## Deployment

Push to the `master` branch on GitHub. GitHub Pages serves from root. The `.nojekyll` file disables Jekyll processing so asset paths work correctly.