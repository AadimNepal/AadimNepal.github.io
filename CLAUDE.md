# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

Static academic personal website for Aadim Nepal, forked from [Jon Barron's template](https://github.com/jonbarron/jonbarron.github.io). Deployed via GitHub Pages at AadimNepal.github.io. No build system — pure HTML/CSS with minimal vanilla JS.

## Development

Preview locally by opening any HTML file directly in a browser, or serve with:
```
python3 -m http.server 8000
```

There is no build step, no linting, no test suite, and no package manager.

## Architecture

### Pages
- `index.html` — homepage: bio, links, and research papers list
- `blog.html` — blog with JS-toggled show/hide posts (inline `<style>` + vanilla JS)
- `miscellaneous.html` — curated links to notes/transcripts
- `mipnerf/`, `mipnerf360/`, `zipnerf/` — self-contained project pages, each with their own `css/` and `js/` subdirectories; these are leftover from the Jon Barron template and not Aadim's papers

### Shared assets
- `stylesheet.css` — shared across all top-level pages (Lato font, paper/name/papertitle classes)
- `images/` — profile photo (`aadim.jpg`) and paper thumbnails
- `data/` — CV PDF (`AadimNepal-CV.pdf`), bio text (`AadimNepal-bio.txt`); the remaining `.bib` files and `JonBarron-*` files are leftover from the original template and unused

### Paper entry pattern in `index.html`
Each paper is a `<tr>` inside the papers `<table>`. Highlighted (representative) papers use `bgcolor="#ffffd0"` on the `<tr>`. Layout: image on the left (`width:25%`), details on the right (`width:75%`). Structure:
```html
<tr>  <!-- or <tr bgcolor="#ffffd0"> for highlighted -->
  <td style="padding:20px;width:25%;vertical-align:middle">
    <img src="images/FILENAME.png" width="160">
  </td>
  <td style="padding:20px;width:75%;vertical-align:middle">
    <a href="PAPER_URL"><span class="papertitle">TITLE</span></a>
    <br>
    AUTHORS (bold <strong> for Aadim Nepal)
    <br>
    <em>VENUE</em>, YEAR
    <br>
    <a href="...">arXiv</a> / <a href="...">code</a> ...
    <p>One-sentence summary.</p>
  </td>
</tr>
```
