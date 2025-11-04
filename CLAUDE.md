# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static, single-page personal portfolio website for a Mobile App Developer / Electrical Engineer specializing in IoT integration. The site showcases projects from Domethics (smart home, health monitoring, and pet health IoT products) and demonstrates Flutter development expertise.

**Tech Stack:** Vanilla HTML5, CSS3, JavaScript (no frameworks, no build process)

**Architecture:** Single-page application with smooth scrolling navigation between sections.

## Development Commands

### Local Development Server

```bash
# Using Python 3
python -m http.server 8000

# Using Node.js
npx http-server
```

Then open `http://localhost:8000` in your browser.

### Testing Changes

Simply open [index.html](index.html) directly in a browser, or use a local server for a more production-like environment.

## File Structure

- **[index.html](index.html)** - Main HTML structure with all content sections
- **[styles.css](styles.css)** - Modern ultra design with neon gradients, glass morphism, and animations
- **[script.js](script.js)** - Interactive functionality: navigation, scroll effects, animations, and mobile menu

## Key Architecture Patterns

### 1. Section-Based Navigation System

The site uses hash-based navigation with smooth scrolling. The active navigation link is automatically highlighted based on scroll position:

- **Active section detection** ([script.js:45-76](script.js#L45-L76)): Special handling for bottom-of-page detection (activates last section when user scrolls to page bottom)
- **Scroll offset** ([script.js:61](script.js#L61)): Uses `offsetTop - 150` to account for fixed navbar
- **Navigation offset** ([script.js:92](script.js#L92)): Uses `offsetTop - 70` for smooth scroll target

### 2. Animation System

Two-layer animation approach:

- **Intersection Observer** ([script.js:104-123](script.js#L104-L123)): Triggers fade-in animations when elements enter viewport (threshold: 0.1)
- **Dynamic CSS injection** ([script.js:126-147](script.js#L126-L147)): Adds animation styles directly to DOM for fade-in effects on cards
- **3D parallax effects** ([script.js:299-318](script.js#L299-L318)): Mouse-tracking transforms on cards using `perspective` and `rotateX/Y`

### 3. Performance Optimizations

- **Throttled scroll events** ([script.js:257-285](script.js#L257-L285)): 16ms throttle (60fps target) on navbar scroll and navigation highlighting
- **Body scroll lock** ([script.js:13](script.js#L13)): Prevents background scrolling when mobile menu is open
- **Lazy animation**: Elements animate only once when first entering viewport

### 4. Responsive Mobile Menu

- **Hamburger toggle** ([script.js:8-14](script.js#L8-L14)): Three-bar icon with active state
- **Outside click detection** ([script.js:26-32](script.js#L26-L32)): Closes menu when clicking outside
- **Escape key support** ([script.js:229-236](script.js#L229-L236)): Keyboard accessibility

### 5. Design System (CSS Variables)

The design uses neon/cyberpunk aesthetics defined in [styles.css:2-14](styles.css#L2-L14):

- **Color palette**: Neon blue (#00f0ff), purple (#b74dff), pink (#ff006e)
- **Glass morphism**: `backdrop-filter: blur()` with semi-transparent backgrounds
- **Animated background** ([styles.css:36-59](styles.css#L36-L59)): Radial gradients with pulsing animation

## Content Customization

### Personal Information

Edit in [index.html](index.html):
- Name/title: Lines 15, 48-49
- Contact links: Lines 357-380
- Social profiles: GitHub (line 365), LinkedIn (line 373)

### Projects Section

Three featured projects from Domethics ([index.html:128-206](index.html#L128-L206)):
- Adriano (smart home gateway)
- S1MPL0 (health monitoring smartwatch)
- Carəpet (pet health monitoring)

Each project card includes: icon, title, description, tech tags, and external link.

### Skills Section

Six skill cards ([index.html:214-257](index.html#L214-L257)) with Font Awesome icons. To add/remove skills, maintain the grid structure and ensure each card has `skill-card` class for animations.

## Styling Guidelines

### Color Changes

Modify CSS variables in [styles.css:2-14](styles.css#L2-L14) to change the entire color scheme. Key variables:
- `--neon-blue`, `--neon-purple`, `--neon-pink`: Primary accent colors
- `--dark-bg`, `--darker-bg`: Background layers
- `--glass-bg`: Semi-transparent card backgrounds

### Adding New Sections

1. Add section HTML with `id` and `class="section"` (or `section section-alt` for alternating backgrounds)
2. Add corresponding navigation link in navbar ([index.html:16-35](index.html#L16-L35))
3. Ensure new cards/content include appropriate classes for Intersection Observer animations

### Typography

Uses Inter font family from Google Fonts. Font weights available: 300, 400, 500, 600, 700.

## External Dependencies

1. **Google Fonts**: Inter font family ([index.html:8](index.html#L8))
2. **Font Awesome 6.5.1**: Icons for skills, projects, and contact ([index.html:9](index.html#L9))

Both loaded via CDN - no npm packages or build tools required.

## Deployment

This is a static site with zero build process. Deploy by uploading all files to any static hosting:

- **GitHub Pages**: Push to `gh-pages` branch or configure in repo settings
- **Netlify/Vercel**: Connect repo and deploy (auto-detects static site)
- **Any web host**: Upload files to public directory (e.g., `public_html`)

Ensure all three files ([index.html](index.html), [styles.css](styles.css), [script.js](script.js)) are in the same directory.

## Browser Compatibility

Supports all modern browsers (Chrome, Firefox, Safari, Edge - latest versions). Uses:
- CSS Grid and Flexbox
- Intersection Observer API
- CSS custom properties (variables)
- Smooth scroll behavior

No polyfills included - designed for modern browser environments.

## Improvement Roadmap

This section tracks planned improvements and completed work. See [SESSION.md](SESSION.md) for detailed session notes and progress.

### Completed ✅

- **Content Quality Fixes** (Session 1 - 2025-11-04)
  - Fixed education section placeholder text (University of Jordan, 2016)
  - Fixed footer placeholder text (Mohamad Harba)
  - Created CLAUDE.md and SESSION.md for documentation
  - Added SVG favicon with "MH" initials in neon gradient style
  - Updated page title: "Mohamad Harba - Flutter Developer & IoT Specialist"
  - Added meta description for SEO

### Critical Priority 🔴

1. **Add meta tags for social sharing**
   - Open Graph tags for LinkedIn/Facebook previews
   - Twitter Card tags
   - Impact: Make portfolio link shareable with rich previews

### High Priority 🟡

2. **Add Work Experience section**
   - Dedicated section for Domethics employment
   - Should appear between Projects and About sections
   - Highlight IoT development work

3. **Mobile optimization**
   - Test and optimize terminal animation performance on mobile
   - Verify 3D parallax card effects work on touch devices
   - May need to disable certain effects on small screens

4. **Add structured data (JSON-LD)**
   - Professional/person schema for better SEO
   - Helps search engines understand the portfolio

### Nice-to-Have 🟢

5. **Add analytics tracking**
   - Google Analytics or Plausible Analytics
   - Track visitor engagement

6. **Add resume/CV download button**
   - PDF download in hero or contact section
   - Makes it easier for recruiters

7. **Dark/light mode toggle** (optional)
   - Currently dark-only design
   - Some users may prefer light mode

8. **Blog/articles section** (optional)
   - Showcase technical writing
   - Demonstrates expertise beyond code

9. **Image optimization**
   - Add `loading="lazy"` attribute for future images
   - Consider WebP format for better compression

10. **Multi-language support (English/Italian)**
    - Auto-detect browser language and set accordingly
    - Default to English for other languages
    - Add manual language toggle in UI
    - Store language preference in localStorage
    - Implementation approach: JSON language files or inline data attributes
    - Note: Keep vanilla JS, no i18n frameworks needed

### Design Philosophy

- **Keep vanilla JavaScript**: No React/framework needed for this static portfolio
- **Performance first**: Fast loading, minimal dependencies, throttled animations
- **Mobile-responsive**: Works great on all devices
- **SEO-friendly**: Discoverable and shareable on social platforms
