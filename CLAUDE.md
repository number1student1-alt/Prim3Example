# CLAUDE.md - AI Assistant Guide for Prim3Example

## Repository Overview

**Project Type:** Static Marketing Landing Page
**Primary Technology:** HTML5 with embedded CSS and JavaScript
**Purpose:** Marketing website for PRIM3 educational content (AI, Tech, Finance courses and ebooks)
**Deployment:** Static hosting compatible (GitHub Pages, Netlify, Vercel, etc.)

## Repository Structure

```
Prim3Example/
├── index.html                          # Main landing page (single-page application)
├── P3_LOGO.jpg                         # Brand logo (40px height in nav)
├── P3_Intro_Avatar.mp4                 # Avatar video asset
├── The_System_Part_one_4K.mp4         # Hero section background video
├── Prime_Example_Youtube_Thumbnail.jpg # YouTube thumbnail with 3D effects
├── PRIM3_Ultimate_Guide.pdf           # 31-page downloadable ebook
├── course-business.png                 # Business module thumbnail
├── course-community.png                # Community module thumbnail
├── course-wealth.png                   # Wealth module thumbnail
└── CLAUDE.md                          # This file
```

## Technology Stack

### Core Technologies
- **HTML5**: Semantic markup, video elements
- **CSS3**: Custom properties (CSS variables), animations, flexbox, grid
- **Vanilla JavaScript**: DOM manipulation, IntersectionObserver API, scroll events

### Key Features
- Single-page responsive design
- Custom CSS animations (lightning effects, 3D rotations, gradient borders)
- Video background with mute toggle
- Smooth scroll navigation
- Intersection Observer for scroll-triggered animations
- Mobile-responsive breakpoints (768px, 1024px)

### External Dependencies
- **Google Fonts**:
  - `Playfair Display` (serif headings - 400, 500, 600, 700)
  - `Inter` (sans-serif body - 300, 400, 500, 600)
- **Stripe**: Payment processing (links to checkout pages)

## Color Scheme (CSS Variables)

```css
--gold: #c9a227          /* Primary brand color */
--gold-light: #d4af37    /* Accent highlights */
--gold-dark: #a38b1d     /* Darker accents */
--black: #0a0a0a         /* Background */
--black-card: #1a1a1a    /* Card backgrounds */
--gray: #8a8a8a          /* Secondary text */
--white: #fafafa         /* Primary text */
--green: #22c55e         /* Success/verified badges */
```

## Development Workflows

### Making Content Updates

#### Updating Prices
- **Ebook Price**: Lines 109, 202, 206 (`$26.99`)
- **Community Price**: Lines 24, 145, 200, 208 (`$9.99/mo`)
- **Stripe Links**: Lines 24, 200, 202, 206, 207, 208

#### Updating Text Content
- **Hero Section**: Lines 202 (title, subtitle)
- **Value Propositions**: Lines 204 (3 cards)
- **Product Modules**: Lines 207 (3 courses)
- **Community Features**: Lines 208
- **Reviews**: Lines 209 (6 testimonials)

#### Updating Media
- Replace files maintaining exact filenames OR
- Update references in HTML (lines 19, 26, 80, 117, 170, 205, 207)

### Testing Locally

```bash
# Option 1: Python simple HTTP server
python3 -m http.server 8000

# Option 2: PHP built-in server
php -S localhost:8000

# Option 3: Node.js http-server (if installed)
npx http-server -p 8000

# Then visit: http://localhost:8000
```

### Git Workflow

This repository follows a simple workflow:
1. Work on feature branches starting with `claude/`
2. Branch naming convention: `claude/claude-md-<session-id>`
3. Commit with descriptive messages
4. Push to origin with `-u` flag: `git push -u origin <branch-name>`

**Current Branch**: `claude/claude-md-miwglb4jcl48r6e4-01UnzHsUkcmgtedYixRoRRKB`

## Key Conventions

### Code Style

#### HTML/CSS
- **Inline Styles**: All CSS embedded in `<style>` tag (lines 9-198)
- **Minified JavaScript**: All JS embedded in `<script>` tag (line 213)
- **No build process**: Direct HTML editing
- **Responsive Design**: Mobile-first with breakpoints at 768px and 1024px

#### Naming Conventions
- **Classes**: Kebab-case (`.hero-content`, `.email-section`)
- **IDs**: camelCase (`#heroVideo`, `#soundToggle`)
- **CSS Variables**: Kebab-case with `--` prefix (`--gold`, `--black-card`)

### Section Structure Pattern

Each major section follows this pattern:
```html
<section class="[section-name]-section" id="[anchor]">
  <div class="section-container">
    <div class="section-header">
      <p class="section-label">LABEL</p>
      <h2 class="section-title">Title</h2>
    </div>
    <!-- Section content -->
  </div>
</section>
```

### Animation Conventions

1. **Scroll Animations**: Sections fade in via IntersectionObserver
2. **Hover Effects**: Transform translateY(-3px to -8px)
3. **Transitions**: Default 0.3s-0.4s ease
4. **Custom Animations**:
   - `@keyframes lightning1-4`: Lightning effects (3.5s-5s)
   - `@keyframes spin3d`: 360° rotation (20s)
   - `@keyframes electric-border`: Gradient movement (3s)
   - `@keyframes spark`: Particle effects (1.8s-2.5s)

## Important Links & Integrations

### External Services
- **Stripe Payments**:
  - Ebook: `buy.stripe.com/14A4gBfFU9Qf3N589sfQI05`
  - Community: `buy.stripe.com/cNifZjdxM9QffvNblEfQI04`
- **Social Media**:
  - Telegram: `t.me/+QsBjR178jSM1Yzkx`
  - TikTok: `@prim3example`
  - YouTube: `@Prim3Example`

### Navigation Anchors
- `#about` → Value Section
- `#ebook` → Ebook Section
- `#courses` → Products Section
- `#community` → Community Section

## Common Tasks for AI Assistants

### Task 1: Update Product Pricing
```bash
# 1. Read current pricing from index.html
# 2. Update all instances (search for $26.99 or $9.99)
# 3. Verify Stripe links match new pricing structure
# 4. Test locally before committing
```

### Task 2: Add New Course Module
```html
<!-- Copy product-showcase structure (lines 207) -->
<div class="product-showcase">
  <div class="product-visual">
    <img src="course-new.png" alt="New Course">
  </div>
  <div class="product-content">
    <p class="product-label">Module 04</p>
    <h3 class="product-title">New Course Title</h3>
    <p class="product-desc">Description...</p>
    <div class="product-modules">
      <p class="modules-title">What's Inside</p>
      <ul>
        <li>Bullet point 1</li>
      </ul>
    </div>
    <a href="[stripe-link]" class="product-cta">CTA Text →</a>
  </div>
</div>
```

### Task 3: Add New Testimonial
```html
<!-- Add to reviews-grid (line 209) -->
<div class="review-card">
  <div class="review-stars">
    <!-- 5 star SVGs -->
  </div>
  <p class="review-text">"Testimonial quote"</p>
  <div class="review-author">
    <div class="review-avatar">I</div>
    <div class="review-info">
      <h5>Name</h5>
      <span>Title</span>
      <div class="review-verified">
        <svg viewBox="0 0 24 24"><path d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"/></svg>
        Verified
      </div>
    </div>
  </div>
</div>
```

### Task 4: Optimize Images
```bash
# Before adding new images:
# - Compress images (use imagemin, tinypng, squoosh)
# - Target sizes:
#   - Logo: ~60KB (current size)
#   - Course thumbnails: ~140-160KB
#   - YouTube thumbnail: ~90KB
#   - Videos: Keep under 25MB for GitHub
```

## Performance Considerations

### Current Asset Sizes
- **Critical**:
  - `index.html`: ~24KB (embedded CSS/JS)
  - `P3_LOGO.jpg`: 60KB
  - Total fonts loaded: ~50KB (Google Fonts)

- **Above-fold**:
  - `The_System_Part_one_4K.mp4`: 24.8MB (hero background)

- **Below-fold**:
  - Other images: ~500KB total
  - Other videos: 3.4MB

### Optimization Opportunities
1. **Split CSS/JS**: Move to external files for caching
2. **Lazy Load Videos**: Add `loading="lazy"` to videos
3. **Image Optimization**: Use WebP format with JPG fallbacks
4. **Video Streaming**: Host videos on CDN/YouTube embed
5. **Minification**: CSS/JS are already minified inline

## Accessibility Notes

### Current State
- ✅ Semantic HTML5 elements (`<nav>`, `<section>`, `<footer>`)
- ✅ Alt text on images
- ✅ Responsive viewport meta tag
- ⚠️ Color contrast meets WCAG AA (gold #c9a227 on black)
- ❌ Missing ARIA labels on interactive elements
- ❌ No skip navigation links
- ❌ Form lacks proper labels (email input)

### Improvements Needed
```html
<!-- Add to email form -->
<label for="emailInput" class="sr-only">Email Address</label>
<input id="emailInput" type="email" class="email-input"
       placeholder="Enter your email"
       aria-label="Email address for newsletter"
       required>

<!-- Add screen reader only class -->
<style>
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0,0,0,0);
  border: 0;
}
</style>
```

## SEO Considerations

### Current Implementation
- ✅ Title tag: "PRIM3 — Unlock Your Potential"
- ✅ Viewport meta tag
- ✅ Favicon
- ❌ Missing meta description
- ❌ Missing Open Graph tags
- ❌ Missing Twitter Card tags
- ❌ Missing schema.org markup

### Recommended Additions
```html
<head>
  <!-- Existing tags... -->
  <meta name="description" content="Master AI content creation, discover underground wealth strategies, and build multiple income streams with PRIM3 courses and community.">

  <!-- Open Graph -->
  <meta property="og:title" content="PRIM3 — Unlock Your Potential">
  <meta property="og:description" content="Master AI, Tech & Finance with PRIM3">
  <meta property="og:image" content="https://[domain]/P3_LOGO.jpg">
  <meta property="og:type" content="website">

  <!-- Twitter Card -->
  <meta name="twitter:card" content="summary_large_image">
  <meta name="twitter:title" content="PRIM3 — Unlock Your Potential">
  <meta name="twitter:description" content="Master AI, Tech & Finance">
  <meta name="twitter:image" content="https://[domain]/Prime_Example_Youtube_Thumbnail.jpg">
</head>
```

## Security Considerations

### Current State
- ✅ External links use `target="_blank"` for Stripe/social
- ⚠️ Missing `rel="noopener noreferrer"` on external links
- ✅ No sensitive data in frontend
- ✅ Payment handled by Stripe (PCI compliant)

### Recommended Fix
```html
<!-- Update all external links -->
<a href="https://example.com"
   target="_blank"
   rel="noopener noreferrer">
   Link Text
</a>
```

## Browser Compatibility

### Supported Features
- CSS Grid (95%+ support)
- CSS Custom Properties (94%+ support)
- IntersectionObserver (94%+ support)
- Flexbox (99%+ support)
- HTML5 Video (98%+ support)

### Minimum Browser Versions
- Chrome 61+
- Firefox 55+
- Safari 12.1+
- Edge 79+

## Deployment Checklist

Before deploying changes:

- [ ] Test on mobile viewport (375px, 768px, 1024px)
- [ ] Verify all Stripe links work
- [ ] Check video autoplay/mute on mobile
- [ ] Test smooth scroll navigation
- [ ] Verify email form submission
- [ ] Check all external links open in new tab
- [ ] Run Lighthouse audit (target: 90+ performance)
- [ ] Validate HTML (validator.w3.org)
- [ ] Test on iOS Safari and Android Chrome
- [ ] Verify animations don't cause motion sickness (reduce motion query)

## Troubleshooting

### Video Not Playing
```javascript
// Check browser autoplay policy
// Muted videos can autoplay, unmuted require user interaction
heroVideo.muted = true;
heroVideo.play().catch(e => console.log("Autoplay prevented:", e));
```

### Animations Not Triggering
```javascript
// Verify IntersectionObserver support
if ('IntersectionObserver' in window) {
  // Observer code...
} else {
  // Fallback: add 'visible' class immediately
  sections.forEach(s => s.classList.add('visible'));
}
```

### Smooth Scroll Not Working
```css
/* iOS Safari requires -webkit- prefix */
html {
  scroll-behavior: smooth;
  -webkit-scroll-behavior: smooth;
}
```

## Git Best Practices for This Repo

### Commit Message Format
```
<type>: <description>

Types:
- content: Update copy, prices, or testimonials
- asset: Add/update images or videos
- style: CSS changes (colors, layout, animations)
- fix: Bug fixes
- perf: Performance improvements
- a11y: Accessibility improvements
```

### Example Commits
```bash
git commit -m "content: Update ebook pricing from $97 to $79"
git commit -m "asset: Optimize course thumbnails (160KB → 80KB)"
git commit -m "style: Improve mobile responsive layout for reviews"
git commit -m "fix: Resolve video autoplay issue on iOS Safari"
```

## File Size Guidelines

### Images
- Logos: < 100KB
- Thumbnails: < 150KB
- Hero images: < 300KB
- Use JPG (photos) or PNG (graphics/logos)

### Videos
- Keep under 10MB for web delivery
- Consider YouTube embeds for longer content
- Use MP4 with H.264 codec for compatibility
- Provide poster images for fallback

## Contact & Support Information

- **YouTube**: @Prim3Example
- **Telegram**: t.me/+QsBjR178jSM1Yzkx
- **TikTok**: @prim3example

---

## Quick Reference Commands

```bash
# Start local server
python3 -m http.server 8000

# Check git status
git status

# Create new feature branch
git checkout -b claude/feature-name-<session-id>

# Stage and commit changes
git add index.html
git commit -m "type: description"

# Push to remote
git push -u origin claude/feature-name-<session-id>

# View recent commits
git log --oneline -10

# Check file sizes
du -h *.{jpg,png,mp4,pdf}
```

---

**Last Updated**: 2025-12-08
**Maintained For**: AI assistants working with the Prim3Example repository
**Version**: 1.0
