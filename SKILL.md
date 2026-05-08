---
name: web-ui-codegen
description: "High-quality Web UI code generator that outputs professional, visually polished HTML/CSS/JS, React, or Vue code. Solves the common problem of AI-generated UI looking ugly — enforces modern diffused gradient design, bento grid layouts, glassmorphism, cinematic typography, and rich visual depth. Outputs both runnable code and a design specification. This skill should be used when the user asks to build, create, design, or implement any web page, web app, landing page, dashboard, admin panel, or UI component, and expects visually beautiful results. Pairs with ui-ux-pro-max for design intelligence lookup."
agent_created: true
---

# Web UI Codegen — Premium UI Code Generator

Generate UI code that looks like a Dribbble top-shot or Behance featured project — NOT generic AI output. The goal is to produce code indistinguishable from a senior product designer's work at top studios.

## Core Problem This Skill Solves

AI-generated UI typically looks "technically correct but soulless":
- Flat, lifeless layouts with no visual emotion
- Mechanical grid without rhythm or breathing room
- Generic colors that don't create atmosphere
- No depth, no light, no dimension
- Text that just "sits there" without commanding attention

This skill transforms output into **design-grade visual experiences**.

## When to Use

This skill MUST be invoked when:
- Building any web page, app, or landing page
- Creating UI components that need polish
- User expects beautiful, modern design output
- Any HTML/CSS/JS, React, or Vue task with visual quality expectations

---

## THE DESIGN SYSTEM

### 1. Background: Diffused Gradient Atmosphere

NEVER use flat solid colors. Backgrounds must create **atmosphere and emotion**.

**Technique — Layered Diffused Gradients:**

```css
/* Background layer 1: base gradient */
body {
  background: #0a0a0f;
  background-image:
    radial-gradient(ellipse 80% 50% at 50% -20%, rgba(120, 119, 198, 0.15) 0%, transparent 60%),
    radial-gradient(ellipse 60% 40% at 80% 50%, rgba(255, 107, 107, 0.08) 0%, transparent 50%),
    radial-gradient(ellipse 50% 50% at 20% 80%, rgba(78, 205, 196, 0.06) 0%, transparent 50%);
}

/* Light theme version: */
body.light {
  background: #f8f6f4;
  background-image:
    radial-gradient(ellipse 80% 60% at 50% 0%, rgba(167, 139, 250, 0.12) 0%, transparent 50%),
    radial-gradient(ellipse 60% 40% at 90% 60%, rgba(251, 191, 146, 0.1) 0%, transparent 40%),
    radial-gradient(ellipse 50% 50% at 10% 90%, rgba(147, 197, 253, 0.08) 0%, transparent 40%);
}
```

**Rules:**
- Use 2-4 `radial-gradient` layers with different positions and colors
- Keep opacity LOW (0.06-0.15 on dark, 0.08-0.15 on light)
- Colors should be complementary or analogous — NOT random
- Position gradients off-center and at edges for natural feel
- Use `ellipse` shape, not `circle` — more organic

**Color mood palettes for backgrounds:**
- **Calm/Tech**: purple-blue + teal (rgba(120,119,198) + rgba(78,205,196))
- **Warm/Creative**: orange-pink + gold (rgba(255,107,107) + rgba(255,193,68))
- **Fresh/Nature**: green + blue (rgba(52,211,153) + rgba(96,165,250))
- **Premium/Luxury**: deep purple + rose (rgba(139,92,246) + rgba(244,114,182))
- **Neutral/Corporate**: slate-blue + silver (rgba(100,116,139) + rgba(148,163,184))

---

### 2. Typography: Cinematic Hierarchy

The #1 difference between amateur and professional UI: **extreme typographic contrast**.

```css
/* Hero heading — commands the screen */
.hero-title {
  font-size: clamp(2.5rem, 6vw, 4.5rem);
  font-weight: 700;
  line-height: 1.05;
  letter-spacing: -0.03em;
  color: var(--text-primary);
}

/* Section heading — anchors content */
.section-title {
  font-size: clamp(1.75rem, 3vw, 2.5rem);
  font-weight: 600;
  line-height: 1.15;
  letter-spacing: -0.02em;
}

/* Subheading / card title */
.card-title {
  font-size: 1.1rem;
  font-weight: 600;
  line-height: 1.3;
  letter-spacing: -0.01em;
}

/* Body text — deliberately light */
.body-text {
  font-size: 1rem;
  font-weight: 400;
  line-height: 1.6;
  color: var(--text-secondary);
  max-width: 540px; /* reading measure */
}

/* Small label / tag */
.label {
  font-size: 0.75rem;
  font-weight: 500;
  letter-spacing: 0.05em;
  text-transform: uppercase;
  color: var(--text-muted);
}
```

**Rules:**
- Title-to-body size ratio: minimum 3:1 (e.g., 48px title / 16px body)
- Hero text: ALWAYS use `clamp()` for fluid scaling
- Letter-spacing: NEGATIVE on headings (-0.02 to -0.04em), POSITIVE on labels (+0.03 to +0.06em)
- Line-height: 1.0-1.1 for headings, 1.5-1.6 for body
- Max one screen should have 2-3 font sizes, not more
- Weight contrast: 700 headings / 400 body — never use 500 for everything

---

### 3. Layout: Breathe & Bento

**The Breathing Rule**: 60% of the screen should be EMPTY SPACE. Content is precious — surround it with air.

**Spacing scale:**
```css
:root {
  --space-xs: 4px;
  --space-sm: 8px;
  --space-md: 16px;
  --space-lg: 24px;
  --space-xl: 40px;
  --space-2xl: 64px;
  --space-3xl: 96px;
  --space-4xl: 128px;
  --space-section: clamp(80px, 12vw, 160px);
}
```

**Bento Grid (for feature sections, dashboards):**
```css
.bento-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-auto-rows: minmax(200px, auto);
  gap: 16px;
}

/* Feature card spans 2 cols */
.bento-item-wide { grid-column: span 2; }
/* Hero card spans 2 cols + 2 rows */
.bento-item-hero { grid-column: span 2; grid-row: span 2; }
/* Tall card */
.bento-item-tall { grid-row: span 2; }
```

**Rules:**
- Section vertical padding: 80-160px (use `--space-section`)
- Content max-width: 1120px (not 1200 — slightly tighter feels more designed)
- Page side padding: 48-80px desktop, 20-24px mobile
- Card padding: 32-48px (generous, not cramped)
- Between heading and body text: 16-24px
- Between sections of cards: 16-20px gap
- Hero section: content vertically centered, minimum 80vh height
- NEVER fill the entire width — leave generous margins

---

### 4. Cards & Surfaces: Glass with Soul

```css
/* === Dark theme glass card === */
.card {
  background: rgba(255, 255, 255, 0.03);
  backdrop-filter: blur(24px) saturate(130%);
  -webkit-backdrop-filter: blur(24px) saturate(130%);
  border: 1px solid rgba(255, 255, 255, 0.06);
  border-radius: 24px;
  padding: 32px;
  position: relative;
  overflow: hidden;
  transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1);
}

/* Top-edge light reflection */
.card::before {
  content: '';
  position: absolute;
  top: 0; left: 10%; right: 10%;
  height: 1px;
  background: linear-gradient(90deg, transparent, rgba(255,255,255,0.1) 50%, transparent);
}

/* Hover: lift + glow */
.card:hover {
  transform: translateY(-4px);
  border-color: rgba(255, 255, 255, 0.12);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
}

/* === Light theme glass card === */
.card-light {
  background: rgba(255, 255, 255, 0.6);
  backdrop-filter: blur(20px) saturate(150%);
  border: 1px solid rgba(255, 255, 255, 0.7);
  border-radius: 24px;
  padding: 32px;
  box-shadow: 
    0 4px 24px rgba(0, 0, 0, 0.04),
    inset 0 1px 0 rgba(255, 255, 255, 0.6);
}

.card-light:hover {
  transform: translateY(-4px);
  box-shadow: 
    0 12px 40px rgba(0, 0, 0, 0.08),
    inset 0 1px 0 rgba(255, 255, 255, 0.8);
}
```

**Rules:**
- Border-radius: 20-32px for cards (LARGE — this is the modern look)
- Border: always rgba, never solid colors — max 0.06-0.1 opacity
- Always add top-edge highlight (`::before` linear-gradient trick)
- Hover must include `translateY` (lift) AND enhanced shadow
- Light cards use `inset` shadow for inner glow
- Card padding: minimum 32px, never less

---

### 5. Buttons: Pill + Emotion

```css
/* Primary CTA — pill with presence */
.btn-primary {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 14px 32px;
  font-size: 0.9rem;
  font-weight: 500;
  color: #fff;
  background: var(--accent);
  border: none;
  border-radius: 50px;
  cursor: pointer;
  transition: all 0.25s cubic-bezier(0.34, 1.56, 0.64, 1);
  box-shadow: 0 4px 16px rgba(var(--accent-rgb), 0.3);
}

.btn-primary:hover {
  transform: translateY(-2px) scale(1.03);
  box-shadow: 0 8px 24px rgba(var(--accent-rgb), 0.4);
}

.btn-primary:active {
  transform: scale(0.97);
  transition-duration: 0.1s;
}

/* Ghost / secondary — subtle outline pill */
.btn-ghost {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 14px 32px;
  font-size: 0.9rem;
  font-weight: 500;
  color: var(--text-primary);
  background: transparent;
  border: 1px solid rgba(var(--text-rgb), 0.15);
  border-radius: 50px;
  cursor: pointer;
  transition: all 0.2s ease;
}

.btn-ghost:hover {
  background: rgba(var(--text-rgb), 0.05);
  border-color: rgba(var(--text-rgb), 0.3);
}
```

**Rules:**
- ALL buttons use `border-radius: 50px` (pill shape)
- Primary button: solid fill + matching color shadow glow
- Secondary button: transparent/ghost with thin border
- Padding: 14-16px vertical, 28-36px horizontal (generous)
- Hover: ALWAYS translateY + scale boost + glow increase
- Active: scale(0.97) with fast transition (100ms)
- Never use square/slightly-rounded buttons — always full pill

---

### 6. Color Tokens

```css
:root {
  /* Dark theme (default) */
  --bg: #0a0a0f;
  --text-primary: #f0f0f3;
  --text-secondary: #8b8b99;
  --text-muted: #4a4a58;
  --accent: #6366f1;        /* indigo — change per project */
  --accent-rgb: 99, 102, 241;
  --accent-glow: rgba(99, 102, 241, 0.3);
  --surface: rgba(255, 255, 255, 0.03);
  --surface-border: rgba(255, 255, 255, 0.06);
  --text-rgb: 240, 240, 243;
}

/* Light theme */
:root.light {
  --bg: #f8f6f4;
  --text-primary: #1a1a2e;
  --text-secondary: #6b6b80;
  --text-muted: #a0a0b0;
  --accent: #6366f1;
  --accent-rgb: 99, 102, 241;
  --surface: rgba(255, 255, 255, 0.6);
  --surface-border: rgba(255, 255, 255, 0.7);
  --text-rgb: 26, 26, 46;
}
```

**Accent color options (pick ONE per project):**
- Indigo: `#6366f1` — tech, AI, SaaS
- Blue: `#3b82f6` — trust, corporate, finance
- Violet: `#8b5cf6` — creative, premium
- Rose: `#f43f5e` — bold, energy, social
- Amber: `#f59e0b` — warm, crypto, fintech
- Emerald: `#10b981` — health, nature, growth
- Cyan: `#06b6d4` — fresh, modern, travel

---

### 7. Micro-interactions & Motion

```css
/* Transition presets */
--ease-out-expo: cubic-bezier(0.16, 1, 0.3, 1);
--ease-bounce: cubic-bezier(0.34, 1.56, 0.64, 1);
--ease-smooth: cubic-bezier(0.4, 0, 0.2, 1);

/* Card hover — float up */
.card { transition: all 0.4s var(--ease-out-expo); }
.card:hover { transform: translateY(-4px); }

/* Button hover — bounce scale */
.btn { transition: all 0.25s var(--ease-bounce); }
.btn:hover { transform: translateY(-2px) scale(1.03); }

/* Subtle entrance animation */
@keyframes fadeUp {
  from { opacity: 0; transform: translateY(20px); }
  to { opacity: 1; transform: translateY(0); }
}
.animate-in {
  animation: fadeUp 0.6s var(--ease-out-expo) forwards;
}
```

**Rules:**
- Cards: 0.4s ease-out-expo, translateY(-4px) on hover
- Buttons: 0.25s bounce, translateY(-2px) + scale(1.03)
- Inputs: 0.2s smooth, border-color change + subtle glow
- NEVER use `transition: all 0.3s ease` — this is the AI tell
- Active/pressed: scale(0.97), duration 0.1s
- Page load: stagger fadeUp animation (0.1s delay per element)

---

### 8. Visual Depth Elements

Add these to create the "designed" feel:

```css
/* Floating gradient orb (decorative) */
.orb {
  position: absolute;
  width: 400px;
  height: 400px;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(99,102,241,0.2) 0%, transparent 70%);
  filter: blur(60px);
  pointer-events: none;
  z-index: 0;
}

/* Noise texture overlay (subtle) */
.noise-overlay::after {
  content: '';
  position: fixed;
  inset: 0;
  opacity: 0.015;
  pointer-events: none;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.75' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)'/%3E%3C/svg%3E");
}

/* Grid lines (optional, for tech/SaaS) */
.grid-bg {
  background-image: 
    linear-gradient(rgba(255,255,255,0.02) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255,255,255,0.02) 1px, transparent 1px);
  background-size: 60px 60px;
}
```

**Rules:**
- ALWAYS add at least 1 decorative gradient orb
- Noise overlay: optional but adds texture (keep opacity 0.01-0.02)
- Grid bg: great for tech/dashboard products
- Orbs should be positioned at corners/edges, not center
- Use `filter: blur(60-100px)` — must be very soft

---

### 9. Responsive Rules

```css
/* Breakpoints */
@media (max-width: 1024px) {
  .bento-grid { grid-template-columns: repeat(2, 1fr); }
  .bento-item-hero { grid-column: span 2; grid-row: span 1; }
}

@media (max-width: 640px) {
  .bento-grid { grid-template-columns: 1fr; }
  .bento-item-wide, .bento-item-hero { grid-column: span 1; }
  .card { padding: 24px; border-radius: 20px; }
  .hero-title { font-size: 2.2rem; }
  body { padding: 0 20px; }
}
```

---

## ANTI-PATTERNS — NEVER DO THESE

| Doing This | Makes It Look Like | Do This Instead |
|---|---|---|
| `background: #1a1a1a` flat | 2019 dark mode | Layered radial-gradients |
| `border-radius: 8px` on cards | Bootstrap template | 24-32px for cards |
| `border: 1px solid #333` | Cheap, harsh lines | rgba(255,255,255, 0.06) |
| Same font-size everywhere | No hierarchy, boring | 3:1 ratio heading:body |
| `margin: 20px` everywhere | No rhythm | Use spacing scale tokens |
| No hover animation | Static, dead | translateY + enhanced shadow |
| Content touching edges | Cramped, amateur | 48-80px page padding |
| `box-shadow: 0 2px 4px` | Weak, flat | Deep layered shadows |
| Text max-width: 100% | Unreadable lines | max-width: 540-600px |
| `transition: 0.3s ease` | AI-generated tell | Custom bezier curves |
| Emoji as icons 🎯 | Unprofessional | CSS shapes or SVG |
| `color: #fff` on dark bg | Harsh, eye strain | Use #f0f0f3 or #e8e8ec |

---

## OUTPUT FORMAT

When generating UI code, ALWAYS output:

### 1. Design Brief
```
Mood: [Calm Tech / Warm Creative / Fresh / Premium / Neutral]
Theme: [Dark / Light / Mixed]
Accent: [color name + hex]
Layout: [Hero full / Bento grid / Split / Cards]
Special: [orbs / noise / grid-bg / animated borders]
```

### 2. Full Working Code
- Self-contained HTML file (or React/Vue components)
- CSS variables at top
- Diffused gradient background (2-4 layers)
- At least 1 decorative orb/gradient element
- Glass cards with top-edge highlight
- Pill buttons with glow shadows
- Cinematic typography (large headings, light body)
- Hover animations on all interactive elements
- Mobile responsive
- Semantic HTML

### 3. Self-Verification
- [ ] Background uses layered gradients (not flat solid)
- [ ] At least 1 floating orb/gradient decoration
- [ ] Typography ratio >= 3:1 (heading vs body)
- [ ] Card border-radius >= 20px
- [ ] Buttons are pill-shaped (border-radius: 50px)
- [ ] Hover states include transform (translateY or scale)
- [ ] Page has generous whitespace (60%+ empty)
- [ ] Text uses off-white (not pure #fff on dark)
- [ ] Custom easing curves (not default ease)
- [ ] Cards have top-edge highlight effect
- [ ] Mobile breakpoint handled
- [ ] Content doesn't touch screen edges

---

## QUICK REFERENCE: WHEN USER ASKS FOR...

| Request | Approach |
|---|---|
| Landing page | Hero (80vh, huge text) + Bento features + CTA section |
| Dashboard | Dark bento grid, stat cards with subtle glow, sidebar |
| Login/signup | Centered glass card on gradient bg, pill inputs + CTA |
| Card selection | Grid of glass cards, selected state = accent border glow |
| Product page | Split layout (text left, visual right), flowing sections |
| Settings/form | Clean light theme, subtle cards, grouped inputs |
| Portfolio | Full-bleed images + overlaid text, minimal chrome |
