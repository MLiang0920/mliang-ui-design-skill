---
name: web-ui-codegen
description: "High-quality Web UI code generator that outputs professional, visually polished HTML/CSS/JS, React, or Vue code. Solves the common problem of AI-generated UI looking ugly — enforces Apple-style minimalist design by default with proper color harmony, spacing rhythm, typography scale, and modern effects. Outputs both runnable code and a design specification. This skill should be used when the user asks to build, create, design, or implement any web page, web app, landing page, dashboard, admin panel, or UI component, and expects visually beautiful results. Pairs with ui-ux-pro-max for design intelligence lookup."
agent_created: true
---

# Web UI Codegen — Beautiful UI Code Generator

Generate professional, visually polished Web UI code that looks like it was designed by a top-tier product designer at Apple or Vercel — NOT generic AI output.

## Core Problem This Skill Solves

Most AI agents produce UI that suffers from:
- Flat, lifeless gray backgrounds with no depth
- No glassmorphism, no gradients, no modern effects
- Tiny border-radius that looks like 2015 Bootstrap
- Zero micro-interactions or state animations
- No sense of "premium" or "elevated" design

This skill enforces **premium visual quality** inspired by modern iOS/macOS design language, Dribbble-top-shots, and high-end SaaS products.

## When to Use

This skill MUST be invoked when:
- Building any web page or web app from scratch
- Creating UI components that need to look polished
- User says "make it beautiful" or "design-quality UI"
- User complains about AI-generated UI looking bad
- Any task requiring HTML/CSS/JS, React, or Vue output with visual quality expectations

## Default Design Philosophy — Premium Dark Glassmorphism

The DEFAULT style is **dark, premium, glassmorphic** — inspired by modern iOS widgets, Apple Vision Pro UI, and high-end design tools. This creates immediate visual impact.

### Core Visual DNA:

1. **Dark gradient backgrounds** — Never flat gray. Use subtle multi-stop gradients (e.g., `#0a0a0f` → `#1a1a2e` → `#16213e`)
2. **Glassmorphism cards** — `backdrop-filter: blur(20-40px)` + semi-transparent backgrounds + subtle light borders
3. **Extra-large border radius** — 20-28px for cards, 14-18px for buttons, 40-50px for pill/capsule shapes
4. **Subtle inner glow** — Cards have a faint `box-shadow: inset 0 1px 0 rgba(255,255,255,0.05)` top-light effect
5. **Monochrome + one accent** — Neutral grays/whites for structure, ONE vibrant accent for key actions
6. **Smooth, springy animations** — `cubic-bezier(0.34, 1.56, 0.64, 1)` for bouncy interactions
7. **Depth via layering** — Multiple z-levels visible (background → mid-layer → foreground cards)
8. **Premium typography** — Large, bold headings with tight letter-spacing; thin, light body text

## Mandatory Pre-Generation Checklist

Before writing ANY UI code, complete these steps:

### Step 1: Determine Design Tokens

```css
:root {
  /* === Background System (gradient layers) === */
  --bg-base: #0a0a0f;
  --bg-gradient: linear-gradient(135deg, #0a0a0f 0%, #1a1a2e 50%, #16213e 100%);
  --bg-noise: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.65' numOctaves='3' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.03'/%3E%3C/svg%3E");

  /* === Surface System (glassmorphism layers) === */
  --surface-glass: rgba(255, 255, 255, 0.04);
  --surface-glass-hover: rgba(255, 255, 255, 0.08);
  --surface-glass-active: rgba(255, 255, 255, 0.12);
  --surface-elevated: rgba(255, 255, 255, 0.06);
  --surface-border: rgba(255, 255, 255, 0.08);
  --surface-border-hover: rgba(255, 255, 255, 0.15);
  --surface-inner-glow: inset 0 1px 0 rgba(255, 255, 255, 0.05);

  /* === Text System === */
  --text-primary: #F5F5F7;
  --text-secondary: #A1A1A6;
  --text-muted: #636366;
  --text-accent: var(--accent);

  /* === Accent (choose ONE per project) === */
  --accent: #007AFF;           /* iOS blue — default */
  --accent-glow: rgba(0, 122, 255, 0.3);
  --accent-soft: rgba(0, 122, 255, 0.12);
  /* Alternatives: #AF52DE (purple), #30D158 (green), #FF9F0A (orange), #FF375F (pink) */

  /* === Spacing (4px base) === */
  --space-xs: 4px;
  --space-sm: 8px;
  --space-md: 16px;
  --space-lg: 24px;
  --space-xl: 32px;
  --space-2xl: 48px;
  --space-3xl: 64px;
  --space-4xl: 96px;

  /* === Typography === */
  --text-xs: 0.75rem;
  --text-sm: 0.875rem;
  --text-base: 1rem;
  --text-lg: 1.125rem;
  --text-xl: 1.25rem;
  --text-2xl: 1.5rem;
  --text-3xl: 2rem;
  --text-4xl: 2.5rem;
  --text-5xl: 3.5rem;

  --font-sans: -apple-system, BlinkMacSystemFont, 'SF Pro Display', 'PingFang SC', 'Microsoft YaHei', sans-serif;
  --font-mono: 'SF Mono', 'JetBrains Mono', 'Fira Code', monospace;

  /* === Border Radius (LARGE — premium feel) === */
  --radius-sm: 8px;
  --radius-md: 14px;
  --radius-lg: 20px;
  --radius-xl: 28px;
  --radius-2xl: 36px;
  --radius-pill: 50px;
  --radius-full: 9999px;

  /* === Shadows (dark-mode optimized) === */
  --shadow-sm: 0 2px 8px rgba(0, 0, 0, 0.3);
  --shadow-md: 0 4px 16px rgba(0, 0, 0, 0.4);
  --shadow-lg: 0 8px 32px rgba(0, 0, 0, 0.5);
  --shadow-xl: 0 16px 48px rgba(0, 0, 0, 0.6);
  --shadow-glow: 0 0 20px var(--accent-glow);

  /* === Transitions === */
  --ease-out: cubic-bezier(0.16, 1, 0.3, 1);
  --ease-bounce: cubic-bezier(0.34, 1.56, 0.64, 1);
  --ease-spring: cubic-bezier(0.68, -0.55, 0.265, 1.55);
  --duration-fast: 150ms;
  --duration-base: 250ms;
  --duration-slow: 400ms;

  /* === Blur amounts === */
  --blur-sm: 10px;
  --blur-md: 20px;
  --blur-lg: 40px;
  --blur-xl: 60px;
}
```

### Step 2: Glass Card Pattern (Core Building Block)

Every card/panel MUST use this pattern:

```css
.glass-card {
  background: var(--surface-glass);
  backdrop-filter: blur(var(--blur-md)) saturate(150%);
  -webkit-backdrop-filter: blur(var(--blur-md)) saturate(150%);
  border: 1px solid var(--surface-border);
  border-radius: var(--radius-xl);
  box-shadow: var(--shadow-md), var(--surface-inner-glow);
  padding: var(--space-lg);
  transition: all var(--duration-base) var(--ease-out);
}

.glass-card:hover {
  background: var(--surface-glass-hover);
  border-color: var(--surface-border-hover);
  box-shadow: var(--shadow-lg), var(--surface-inner-glow);
  transform: translateY(-2px);
}
```

### Step 3: Button Patterns

```css
/* Primary — pill shape with glow */
.btn-primary {
  display: inline-flex;
  align-items: center;
  gap: var(--space-sm);
  padding: 12px 28px;
  font-size: var(--text-sm);
  font-weight: 500;
  color: #FFFFFF;
  background: var(--accent);
  border: none;
  border-radius: var(--radius-pill);
  cursor: pointer;
  transition: all var(--duration-fast) var(--ease-bounce);
  box-shadow: 0 2px 12px var(--accent-glow);
}

.btn-primary:hover {
  transform: translateY(-2px) scale(1.02);
  box-shadow: 0 4px 20px var(--accent-glow);
}

.btn-primary:active {
  transform: translateY(0) scale(0.97);
}

/* Secondary — glass pill */
.btn-secondary {
  display: inline-flex;
  align-items: center;
  gap: var(--space-sm);
  padding: 12px 28px;
  font-size: var(--text-sm);
  font-weight: 500;
  color: var(--text-primary);
  background: var(--surface-glass);
  backdrop-filter: blur(var(--blur-sm));
  border: 1px solid var(--surface-border);
  border-radius: var(--radius-pill);
  cursor: pointer;
  transition: all var(--duration-fast) var(--ease-out);
}

.btn-secondary:hover {
  background: var(--surface-glass-hover);
  border-color: var(--surface-border-hover);
  transform: translateY(-1px);
}
```

### Step 4: Typography Rules

1. **Hero headings**: 48-64px, font-weight 700, letter-spacing -0.03em, line-height 1.05
2. **Section headings**: 28-36px, font-weight 600, letter-spacing -0.02em
3. **Body text**: 15-16px, font-weight 400, color: secondary text, line-height 1.6
4. **Labels/tags**: 12-13px, font-weight 500, letter-spacing +0.03em, uppercase optional
5. **Contrast**: Primary text = near-white (#F5F5F7), never pure white (#FFF) on dark bg

### Step 5: Layout Rules

1. **Background**: ALWAYS a gradient, never flat solid color
2. **Content width**: Max 1120px, centered with generous side padding (32-48px)
3. **Section spacing**: 80-120px vertical between major sections
4. **Card grid gap**: 16-20px between cards
5. **Responsive**: grid cols collapse 4→2→1 at 1024/640px breakpoints
6. **Depth illusion**: Use 2-3 visual layers (bg gradient → floating blur shapes → glass cards)

### Step 6: Elevation & Depth Effects

Add floating gradient orbs/blobs behind content for depth:

```css
.bg-blob {
  position: absolute;
  border-radius: 50%;
  filter: blur(80px);
  opacity: 0.15;
  pointer-events: none;
}

.bg-blob-1 {
  width: 400px; height: 400px;
  background: #007AFF;
  top: -100px; left: -100px;
}

.bg-blob-2 {
  width: 300px; height: 300px;
  background: #AF52DE;
  bottom: -50px; right: -50px;
}
```

## Anti-Patterns to NEVER Do

| Bad Practice | Why It Looks Cheap | Do Instead |
|---|---|---|
| `background: #f0f0f0` flat gray | Lifeless, no depth | Dark gradient with multiple stops |
| `border-radius: 5px` | Dated, generic | 20-28px for cards, pill for buttons |
| `border: 1px solid #ccc` | Harsh, visible line | `rgba(255,255,255,0.08)` subtle glass border |
| `box-shadow: 0 2px 5px rgba(0,0,0,0.1)` | Weak, no depth | Layered dark shadows + inner glow |
| No backdrop-filter | Flat, no glass effect | Always use blur(20px)+saturate for panels |
| `font-family: Arial` | Generic, boring | System font stack with SF Pro |
| Equal padding everywhere | No rhythm | Generous varied spacing (24-48px) |
| No hover animations | Static, dead | translateY + scale + glow on hover |
| Pure white text on dark | Harsh, eye strain | Use #F5F5F7 or #E5E5EA instead |
| `transition: all 0.3s ease` | Sluggish, default | Use custom bezier curves, 150-250ms |
| Icons as emoji | Amateur | Use SVG icons (Lucide/Heroicons) or styled divs |

## Output Format

When generating UI code, ALWAYS output in this structure:

### 1. Design Specification (brief)
```
Theme: [Dark Glass / Light Glass / Dark Solid / Custom]
Accent: [color name + hex]
Layout: [single page / multi-section / dashboard / ...]
Framework: [HTML/CSS | React | Vue]
Special Effects: [gradient blobs / noise texture / animated borders / ...]
```

### 2. Full Working Code
- Self-contained, runnable
- CSS variables at top (full token set)
- Dark gradient background with depth layers (blobs)
- All cards use glassmorphism
- Buttons are pill-shaped with glow
- Smooth bouncy transitions on interactions
- Mobile-first responsive
- Proper semantic HTML + accessibility

### 3. Quality Checklist (self-verify)
- [ ] Background is a gradient, not flat solid
- [ ] Cards have backdrop-filter blur
- [ ] Border-radius >= 20px on major cards
- [ ] Buttons are pill-shaped (border-radius: 50px)
- [ ] At least one accent glow effect present
- [ ] Typography has 3+ distinct size levels
- [ ] Hover states include transform (translateY/scale)
- [ ] Inner glow (inset shadow) on glass surfaces
- [ ] No harsh borders (all rgba with low opacity)
- [ ] Text uses off-white (#F5F5F7), not pure white
- [ ] Mobile responsive (375px tested)
- [ ] At least one floating blob/gradient for depth

## Light Theme Alternative

If user explicitly asks for light theme, use this adjusted approach:

```css
:root {
  --bg-base: #F2F2F7;
  --bg-gradient: linear-gradient(135deg, #F2F2F7 0%, #E5E5EA 50%, #F2F2F7 100%);
  --surface-glass: rgba(255, 255, 255, 0.72);
  --surface-glass-hover: rgba(255, 255, 255, 0.85);
  --surface-border: rgba(0, 0, 0, 0.04);
  --surface-border-hover: rgba(0, 0, 0, 0.08);
  --surface-inner-glow: inset 0 1px 0 rgba(255, 255, 255, 0.8);
  --text-primary: #1D1D1F;
  --text-secondary: #6E6E73;
  --text-muted: #AEAEB2;
  --shadow-md: 0 4px 16px rgba(0, 0, 0, 0.06);
  --shadow-lg: 0 8px 32px rgba(0, 0, 0, 0.08);
}
```

Light theme blobs use pastel colors at 0.3-0.4 opacity.

## Framework-Specific Templates

### HTML/CSS/JS (Default)
Read `references/template-html.md` for the starter template.

### React (with CSS Modules or styled-components)
Read `references/template-react.md` for the starter template.

### Vue 3 (with scoped styles)
Read `references/template-vue.md` for the starter template.

## Quick Invocation Examples

User says: "帮我做一个登录页面"
→ Dark Glass theme, centered floating glass card, gradient blobs behind, input fields with glass bg, pill-shaped submit button with glow

User says: "做一个深色风格的仪表盘"
→ Dark Glass theme, glass sidebar + main grid, data cards with subtle inner glow, accent colored chart elements

User says: "做一个产品展示落地页"
→ Dark Glass theme, hero with large text + floating device mockup, feature cards in glass grid, gradient CTA section

User says: "做一个卡片选择页面"
→ Dark Glass theme, glass cards with hover lift + glow border, selected state with accent border glow, pill-shaped confirm button
