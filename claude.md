# Jaewook Lee Academic Website - Structure Map

## Overview
This is a Jekyll-based academic website for Jaewook Lee, a Post-Doctoral Researcher in Political Science. The site showcases his research, publications, teaching, and translations. Built using the [academic-homepage](https://github.com/luost26/academic-homepage) template.

## Site Architecture

### Root Structure
```
jwklee.github.io/
├── _config.yml              # Jekyll configuration
├── _data/                   # Data files (YAML)
├── _includes/               # Reusable components
├── _layouts/                # Page layouts
├── _publications/           # Publication markdown files (by year)
├── _news/                   # News items
├── _showcase/               # Showcase items (currently not used)
├── assets/                  # Static assets (CSS, JS, images)
├── index.html              # Homepage
├── publications.html       # Publications page
├── research.html           # Research page
├── teaching.html           # Teaching page
├── translations.html       # Translations page
└── showcase.html           # Showcase page (commented out in navigation)
```

## Configuration Files

### `_config.yml`
Main Jekyll configuration file defining:
- Markdown processor: kramdown
- Plugins: jekyll-email-protect
- Collections: publications, news, showcase, teaching
- Base URL settings

### `_data/` Directory
Data files that control site content and behavior:

#### `profile.yml`
Personal information and professional details:
- **Identity**: Primary/secondary name, navbar name
- **Positions**: Current position at Leiden University
- **Contact**: Email, CV link, social media handles (Google Scholar, GitHub, Twitter, ORCID)
- **Bio**: Short biography with research interests
- **Portrait**: Photo and caption
- **Education**: 3 degrees (Boston University PhD, Seoul National University MA & BA)
- **Experience**: Post-doc positions at Leiden, Milan, McGill
- **Awards**: 9 awards and fellowships (2015-2025)

#### `navigation.yml`
Defines main navigation menu:
- Home (`/index`)
- Publications (`/publications`)
- Research (`/research.html`)
- Translations (`/translations.html`)
- Teaching (`/teaching.html`)
- Showcase (commented out)

#### `display.yml`
Controls what appears on homepage:
- `show_experience: true`
- `show_news: true`
- `show_selected_publications: true`
- `num_news: 10`
- Footer text with template attribution

## Layouts

### `_layouts/default.html`
Base template for all pages:
- Bootstrap 4.6.0 framework
- Font Awesome 6.5.1 icons
- Academicons 1.9.1 (academic icons)
- Google Fonts: Lato, Fira Sans, Source Code Pro
- KaTeX for mathematical formulas
- jQuery, Popper.js, Masonry layout
- Custom scripts for visual hash, citation counts

### `_layouts/prompt.html`
Alternative layout (usage not immediately clear from inspection)

## Pages

### `index.html` (Homepage)
- Layout: default
- Components:
  - Profile card widget
  - Experience card (conditional)
  - News card (conditional, limited to 10)
  - Selected publications (where `selected: true` in publication frontmatter)

### `publications.html`
- Groups publications by year (descending order)
- Sidebar navigation with year anchors
- Uses `publication_item.html` widget for each entry
- Responsive 2-column layout (10-col content + 2-col year nav)

### `research.html`
- Custom layout with extensive inline CSS
- **Sections**:
  - Research intro with AI-generated image
  - Working Papers (4 papers with abstracts in `<details>` tags):
    1. "Saving His Job, Not Hers" (with Soohyun Cho) - SASE 2025 Award
    2. "Green Backlash or Distributive Discontent?" (with Marcello Natili)
    3. "Teaching Machines to Read Occupations" (with Scott Patterson & Krzysztof Pelc)
    4. "Managing Foreign Workers and Machines" (solo)
  - Work-in-Progress (5 projects):
    1. Climate Costs of Computing - APSA 2025 Grant
    2. Uncertain Returns (with Jiyeong Jeon)
    3. European Competitiveness (with van Doorn, Fernandes, van Vliet)
    4. Macroeconomic Contexts (with van Doorn, Fernandes, van Vliet)
    5. Occupational Asymmetry (with Scott Patterson)
- Responsive image layout with captions

### `teaching.html`
- **Sections**:
  - Teaching philosophy: "guided discovery" and "learning by doing"
  - Methods and applications
  - Course portfolio (5 courses listed)
  - Student feedback (selected quotes from evaluations)
- Image on right side (education-themed)

### `translations.html`
- Lists academic translations (English → Korean)
- **Articles**: 1 Catalyst journal article
- **Books**: 2 translations
  - "Conservatives Against Capitalism" by Kolozi
  - "The Weimar Century" by Greenberg
- Links to both original works and Korean translations

### `showcase.html`
- Currently commented out in navigation
- Demo page from template (not customized)

## Collections

### `_publications/`
Organized by year subdirectories:
- `2025/` - 2 publications
- `2024/` - 2 publications
- `2016/` - 1 publication

**Example publication frontmatter** (`2025-pub-eup.md`):
```yaml
---
title: "Pushed by Markets, Pulled by Machines..."
date: 2025-11-24 00:01:00 +0100
selected: true
pub: "European Union Politics"
pub_date: ""
pub_last: '<span class="badge...">Online First</span>'
semantic_scholar_id:
abstract: >-
  [Full abstract text]
cover:
authors:
  - Jaewook Lee
links:
  Article: https://doi.org/10.1177/...
---
```

### `_news/`
News items (5 files):
- `2025-news1.md` through `2025-news5.md`
- Displayed on homepage in reverse chronological order

### `_showcase/`
Template demonstration content (2 subdirectories):
- `default/` - 9 demo markdown files
- `cats/` - 5 cat-themed demo files
- Not actively used in current site

## Widgets (`_includes/widgets/`)

Reusable components included in pages:
- `profile_card.html` - Main profile display on homepage
- `profile_card_mini.html` - Compact version
- `profile_card_bio_only.html` - Biography only
- `experience_card.html` - Professional experience timeline
- `news_card.html` - News items display
- `publication_card.html` - Publication list display
- `publication_item.html` - Individual publication entry
- `author_list.html` - Format author names
- `carousel.html` - Image carousel
- `debug_url.html` / `debug_repo_name.html` - Debug utilities

## Navigation Components (`_includes/`)
- `navbar.html` - Top navigation bar
- `footer.html` - Site footer

## Assets

### `/assets/css/`
- `global.css` - Custom site styles
- `images/` - CSS-related images

### `/assets/js/`
- `common.js` - General JavaScript utilities
- `bubble_visual_hash.js` - Visual hash generation
- `semantic_scholar_citation_count.js` - Fetch citation counts from Semantic Scholar

### `/assets/images/`
Organized by purpose:
- `badges/` - University/institution logos (Boston U, Leiden, McGill, Milan, SNU)
- `covers/` - Publication cover images
- `photos/` - Photo collections
- `etc/` - Miscellaneous images
  - `jaewook_lee_photo_21.jpeg` - Portrait
  - `research_image-min.png` - Research page illustration
  - `image_learning.jpg` - Teaching page image
  - `translation_image.jpg` - Translation page image

## PDF Assets
- `Jaewook Lee CV (2025_11_24).pdf` - Curriculum Vitae (linked from profile)

## Key Features

### Responsive Design
- Bootstrap 4.6.0 grid system
- Mobile-first approach
- Breakpoints defined in custom CSS
- Collapsible navigation on mobile

### Academic Features
- Google Scholar integration (profile ID: 0e9uxO0AAAAJ)
- ORCID integration (0000-0001-8405-8469)
- Semantic Scholar citation counts (automatic fetching)
- Email protection via Jekyll plugin
- LaTeX/KaTeX math rendering support

### Publication Management
- YAML frontmatter for metadata
- Support for selected/featured publications
- Abstract collapsible sections (`<details>` tags)
- External links (DOI, PDF, etc.)
- Author lists with automatic formatting
- Optional cover images

### Content Organization
- Collections for different content types
- Year-based organization for publications
- Tag-based filtering potential (not currently implemented)
- News items with date stamps

## Development & Deployment

### Build System
- Jekyll static site generator
- Kramdown markdown processor
- Gemfile for Ruby dependencies

### Plugins
- jekyll-email-protect (obfuscate email addresses)

### Git Repository
- GitHub Pages compatible
- `.github/` directory with issue templates
- Main branch for deployment
- Clean working tree (as of last commit)

## Recent Commit History
```
b28ecfc - Update 2025-pub-eup.md
85730e4 - pub update
69c7c0d - commit
d239938 - Merge branch 'main'
302b1c0 - Create Jaewook Lee CV (2025_11_24).pdf
```

## Content Management Workflow

### Adding a Publication
1. Create new `.md` file in `_publications/YYYY/`
2. Add frontmatter with metadata
3. Optionally set `selected: true` for homepage display
4. Add abstract and links
5. Site rebuilds automatically

### Adding News
1. Create new `.md` file in `_news/`
2. Add date and content
3. Appears automatically on homepage

### Updating Profile
1. Edit `_data/profile.yml`
2. Update biography, positions, or social links
3. Replace CV PDF in `/assets/`

### Modifying Pages
- Direct editing of HTML files in root
- Custom CSS embedded in page headers
- Widgets can be included/excluded conditionally

## Template Attribution
Based on [academic-homepage](https://github.com/luost26/academic-homepage) by luost26

---

## Notes for Future Development

### Current State
- Clean, professional academic website
- Fully functional navigation
- Responsive design working well
- Rich publication metadata
- Social media integration

### Potential Enhancements
- Enable showcase section with custom content
- Add blog functionality
- Implement publication filtering/search
- Add teaching materials section
- Create project pages with detailed descriptions
- Integrate with citation APIs for auto-updates
- Add dark mode toggle
- Implement multilingual support (English/Korean)

### Maintenance
- Regular CV updates
- Publication additions as research progresses
- News updates for awards, talks, conferences
- Image optimization for faster loading
- Dependency updates (Bootstrap, jQuery, etc.)
