---
name: web-ui-codegen
description: "High-quality Web UI code generator that outputs professional, visually polished HTML/CSS/JS, React, or Vue code. Solves the common problem of AI-generated UI looking ugly — enforces Apple-style minimalist design by default with proper color harmony, spacing rhythm, typography scale, and modern effects. Outputs both runnable code and a design specification. This skill should be used when the user asks to build, create, design, or implement any web page, web app, landing page, dashboard, admin panel, or UI component, and expects visually beautiful results. Pairs with ui-ux-pro-max for design intelligence lookup."
agent_created: true
---

# Web UI Codegen — Beautiful UI Code Generator

Generate professional, visually polished Web UI code that looks like it was made by a senior designer, not a generic AI.

## Core Problem This Skill Solves

Most AI agents produce UI that suffers from:
- Ugly, uncoordinated color combinations
- No consistent spacing rhythm
- Generic "bootstrap default" look with no design sense
- Lack of modern visual effects and micro-interactions
- No awareness of typography hierarchy

This skill enforces **strict visual quality rules** to produce UI that is indistinguishable from hand-crafted designer output.

## When to Use

This skill MUST be invoked when:
- Building any web page or web app from scratch
- Creating UI components that need to look polished
- User says "make it beautiful" or "design-quality UI"
- User complains about AI-generated UI looking bad
- Any task requiring HTML/CSS/JS, React, or Vue output with visual quality expectations

## Default Design Philosophy

**Apple-style minimalist** unless user specifies otherwise:
- Generous whitespace (breathing room between elements)
- Subtle shadows and depth (not flat, not heavy)
- Rounded corners (12-16px for cards, 8px for buttons)
- Muted, harmonious color palette with one accent color
- Smooth micro-interactions (150-300ms)
- Typography that breathes (large sizes, clear hierarchy)

## Mandatory Pre-Generation Checklist

Before writing ANY UI code, complete these steps:

### Step 1: Determine Design Tokens

Always establish these tokens FIRST (output as CSS custom properties):

```css
:root {
  /* Color System — MUST be harmonious */
  --color-bg: ;           /* Page background */
  --color-surface: ;      /* Card/panel surface */
  --color-surface-hover: ; /* Hovered surface */
  --color-text-primary: ; /* Main text — contrast >= 7:1 */
  --color-text-secondary: ; /* Supporting text — contrast >= 4.5:1 */
  --color-text-muted: ;   /* Hint/placeholder text */
  --color-accent: ;       /* Primary brand/action color */
  --color-accent-hover: ; /* Accent hover state */
  --color-border: ;       /* Subtle borders */
  --color-shadow: ;       /* Shadow color (use rgba) */

  /* Spacing System — 4px base rhythm */
  --space-xs: 4px;
  --space-sm: 8px;
  --space-md: 16px;
  --space-lg: 24px;
  --space-xl: 32px;
  --space-2xl: 48px;
  --space-3xl: 64px;

  /* Typography Scale — modular (1.25 ratio) */
  --text-xs: 0.75rem;    /* 12px */
  --text-sm: 0.875rem;   /* 14px */
  --text-base: 1rem;     /* 16px */
  --text-lg: 1.125rem;   /* 18px */
  --text-xl: 1.25rem;    /* 20px */
  --text-2xl: 1.5rem;    /* 24px */
  --text-3xl: 1.875rem;  /* 30px */
  --text-4xl: 2.25rem;   /* 36px */
  --text-5xl: 3rem;      /* 48px */

  /* Border Radius */
  --radius-sm: 6px;
  --radius-md: 8px;
  --radius-lg: 12px;
  --radius-xl: 16px;
  --radius-2xl: 24px;
  --radius-full: 9999px;

  /* Shadows — layered for depth */
  --shadow-sm: 0 1px 2px rgba(0,0,0,0.04);
  --shadow-md: 0 4px 6px -1px rgba(0,0,0,0.06), 0 2px 4px -2px rgba(0,0,0,0.04);
  --shadow-lg: 0 10px 15px -3px rgba(0,0,0,0.08), 0 4px 6px -4px rgba(0,0,0,0.04);
  --shadow-xl: 0 20px 25px -5px rgba(0,0,0,0.1), 0 8px 10px -6px rgba(0,0,0,0.04);

  /* Transitions */
  --transition-fast: 150ms cubic-bezier(0.4, 0, 0.2, 1);
  --transition-base: 250ms cubic-bezier(0.4, 0, 0.2, 1);
  --transition-slow: 350ms cubic-bezier(0.4, 0, 0.2, 1);

  /* Font Stack */
  --font-sans: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'PingFang SC', 'Hiragino Sans GB', 'Microsoft YaHei', sans-serif;
  --font-mono: 'SF Mono', 'Fira Code', 'JetBrains Mono', monospace;
}
```

### Step 2: Color Harmony Rules (CRITICAL)

**NEVER randomly pick colors.** Follow these rules:

1. **Monochromatic palette**: Pick ONE hue, create 5-7 shades from light to dark
2. **Accent rule**: Only ONE accent color per page (for CTAs and highlights)
3. **Background hierarchy**: page bg → card bg → elevated bg (3 levels max, each 2-4% different)
4. **Text colors**: Maximum 3 text colors (primary, secondary, muted)
5. **Border color**: Always derived from text color at 10-15% opacity

**Pre-built harmonious palettes (use these, don't invent):**

#### Light Theme — Apple Neutral (DEFAULT)
```css
--color-bg: #FAFAFA;
--color-surface: #FFFFFF;
--color-surface-hover: #F5F5F7;
--color-text-primary: #1D1D1F;
--color-text-secondary: #6E6E73;
--color-text-muted: #AEAEB2;
--color-accent: #007AFF;
--color-accent-hover: #0056CC;
--color-border: rgba(0, 0, 0, 0.06);
--color-shadow: rgba(0, 0, 0, 0.04);
```

#### Dark Theme — Apple Dark
```css
--color-bg: #000000;
--color-surface: #1C1C1E;
--color-surface-hover: #2C2C2E;
--color-text-primary: #F5F5F7;
--color-text-secondary: #A1A1A6;
--color-text-muted: #636366;
--color-accent: #0A84FF;
--color-accent-hover: #409CFF;
--color-border: rgba(255, 255, 255, 0.08);
--color-shadow: rgba(0, 0, 0, 0.3);
```

#### Light Theme — Warm Neutral
```css
--color-bg: #FAF9F7;
--color-surface: #FFFFFF;
--color-surface-hover: #F5F3F0;
--color-text-primary: #1A1816;
--color-text-secondary: #6B6560;
--color-text-muted: #A8A29E;
--color-accent: #D97706;
--color-accent-hover: #B45309;
--color-border: rgba(28, 25, 23, 0.06);
--color-shadow: rgba(28, 25, 23, 0.04);
```

#### Light Theme — Cool Blue
```css
--color-bg: #F8FAFC;
--color-surface: #FFFFFF;
--color-surface-hover: #F1F5F9;
--color-text-primary: #0F172A;
--color-text-secondary: #475569;
--color-text-muted: #94A3B8;
--color-accent: #2563EB;
--color-accent-hover: #1D4ED8;
--color-border: rgba(15, 23, 42, 0.06);
--color-shadow: rgba(15, 23, 42, 0.04);
```

### Step 3: Layout Golden Rules

1. **Max content width**: 1200px for pages, 680px for reading content
2. **Section padding**: 80-120px vertical on desktop, 48-64px on mobile
3. **Card padding**: 24-32px
4. **Component spacing**: Always use the 4px grid (multiples of 4)
5. **Responsive breakpoints**: 640px / 768px / 1024px / 1280px
6. **Container padding**: 16px mobile, 24px tablet, 32px desktop

### Step 4: Typography Rules

1. **Heading sizes**: Hero 48-64px, H1 36-48px, H2 24-30px, H3 20px, Body 16px
2. **Line heights**: Headings 1.2, Body 1.6, Small text 1.5
3. **Font weights**: Only use 400 (body), 500 (labels), 600 (headings) — never 700+ on body
4. **Letter spacing**: -0.02em on large headings, 0 on body, +0.02em on all-caps labels
5. **Max line width**: 65-75 characters for readability

### Step 5: Component Quality Standards

Every component MUST have:
- **Hover state**: Subtle background shift or shadow elevation (not just color change)
- **Focus state**: 2px ring with 2px offset, using accent color
- **Active/pressed state**: Slight scale(0.98) or darker background
- **Transition**: All state changes animated (150-250ms)
- **Border radius**: Consistent across the page (pick ONE radius scale)

## Anti-Patterns to NEVER Do

| Bad Practice | Why It's Ugly | Do Instead |
|---|---|---|
| `background: #f0f0f0` random gray | Looks washed out, no personality | Use semantic token from palette |
| `border: 1px solid #ccc` | Heavy, visible borders look cheap | Use `rgba(0,0,0,0.06)` or no border + shadow |
| `font-size: 14px` for everything | Zero hierarchy, boring | Use modular type scale |
| `padding: 10px` everywhere | Cramped, no breathing room | Use 16-24px minimum, 32px for cards |
| `color: blue` for links | Looks like 1999 web | Use design-system accent color |
| `box-shadow: 0 2px 5px rgba(0,0,0,0.3)` | Too heavy, fake depth | Use layered subtle shadows |
| Random `margin-top: 37px` | No rhythm, messy | Stick to spacing scale |
| Multiple accent colors | Circus effect | ONE accent, use shades for variants |
| `font-family: Arial` | Generic, no personality | Use system font stack |
| Centered text everywhere | Hard to read, amateur | Left-align body, center only heroes |

## Output Format

When generating UI code, ALWAYS output in this structure:

### 1. Design Specification (brief)
```
Theme: [Light Apple / Dark Apple / Warm / Cool / Custom]
Accent: [color name + hex]
Layout: [single page / multi-section / dashboard / ...]
Framework: [HTML/CSS | React | Vue]
```

### 2. Full Working Code
- Self-contained, runnable file(s)
- CSS custom properties at the top
- Mobile-first responsive
- All states (hover, focus, active) included
- Smooth transitions on all interactive elements
- Proper semantic HTML

### 3. Quality Checklist (self-verify)
Before delivering, verify:
- [ ] Color contrast >= 4.5:1 for all text
- [ ] Consistent border-radius across all components
- [ ] Spacing follows 4px grid
- [ ] Only ONE accent color used
- [ ] All interactive elements have hover + focus states
- [ ] Typography has clear hierarchy (3+ sizes)
- [ ] Shadows are layered and subtle
- [ ] Mobile viewport tested (375px width)

## Framework-Specific Templates

### HTML/CSS/JS (Default)
Read `references/template-html.md` for the starter template.

### React (with CSS Modules or styled-components)
Read `references/template-react.md` for the starter template.

### Vue 3 (with scoped styles)
Read `references/template-vue.md` for the starter template.

## Integration with ui-ux-pro-max

When a product-type-specific palette or style is needed:
1. Use `ui-ux-pro-max` `--design-system` to get recommendations
2. Map the recommended colors into this skill's token structure
3. Apply the code generation rules from this skill

This ensures both **correct design decisions** (from ui-ux-pro-max) AND **beautiful code output** (from this skill).

## Quick Invocation Examples

User says: "帮我做一个登录页面"
→ Use Light Apple palette, centered card layout, glass-effect card, smooth focus transitions

User says: "做一个深色风格的仪表盘"
→ Use Dark Apple palette, sidebar + main grid layout, subtle glow accents

User says: "做一个产品展示落地页"
→ Use Cool Blue palette, hero + features + CTA sections, large typography, scroll animations

User says: "给我写一个暖色调的后台管理"
→ Use Warm Neutral palette, sidebar navigation, data table with subtle hover states
