# HTML/CSS/JS Starter Template

Use this as the base when generating pure HTML pages. Every generated page MUST start from this structure.

## Base Template

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>{{PAGE_TITLE}}</title>
    <style>
        /* ===== Design Tokens ===== */
        :root {
            /* Colors — replace with chosen palette */
            --color-bg: #FAFAFA;
            --color-surface: #FFFFFF;
            --color-surface-hover: #F5F5F7;
            --color-text-primary: #1D1D1F;
            --color-text-secondary: #6E6E73;
            --color-text-muted: #AEAEB2;
            --color-accent: #007AFF;
            --color-accent-hover: #0056CC;
            --color-accent-light: rgba(0, 122, 255, 0.08);
            --color-border: rgba(0, 0, 0, 0.06);
            --color-shadow: rgba(0, 0, 0, 0.04);
            --color-success: #34C759;
            --color-warning: #FF9500;
            --color-danger: #FF3B30;

            /* Spacing */
            --space-xs: 4px;
            --space-sm: 8px;
            --space-md: 16px;
            --space-lg: 24px;
            --space-xl: 32px;
            --space-2xl: 48px;
            --space-3xl: 64px;
            --space-4xl: 96px;

            /* Typography */
            --text-xs: 0.75rem;
            --text-sm: 0.875rem;
            --text-base: 1rem;
            --text-lg: 1.125rem;
            --text-xl: 1.25rem;
            --text-2xl: 1.5rem;
            --text-3xl: 1.875rem;
            --text-4xl: 2.25rem;
            --text-5xl: 3rem;
            --text-6xl: 3.75rem;

            /* Font */
            --font-sans: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'PingFang SC', 'Hiragino Sans GB', 'Microsoft YaHei', sans-serif;
            --font-mono: 'SF Mono', 'Fira Code', 'JetBrains Mono', 'Consolas', monospace;

            /* Radius */
            --radius-sm: 6px;
            --radius-md: 8px;
            --radius-lg: 12px;
            --radius-xl: 16px;
            --radius-2xl: 24px;
            --radius-full: 9999px;

            /* Shadows — layered */
            --shadow-xs: 0 1px 2px var(--color-shadow);
            --shadow-sm: 0 1px 3px var(--color-shadow), 0 1px 2px -1px var(--color-shadow);
            --shadow-md: 0 4px 6px -1px rgba(0,0,0,0.06), 0 2px 4px -2px rgba(0,0,0,0.04);
            --shadow-lg: 0 10px 15px -3px rgba(0,0,0,0.08), 0 4px 6px -4px rgba(0,0,0,0.04);
            --shadow-xl: 0 20px 25px -5px rgba(0,0,0,0.1), 0 8px 10px -6px rgba(0,0,0,0.04);

            /* Transitions */
            --ease-out: cubic-bezier(0.16, 1, 0.3, 1);
            --ease-in-out: cubic-bezier(0.4, 0, 0.2, 1);
            --duration-fast: 150ms;
            --duration-base: 250ms;
            --duration-slow: 350ms;
        }

        /* ===== Reset & Base ===== */
        *, *::before, *::after {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        html {
            font-size: 16px;
            -webkit-font-smoothing: antialiased;
            -moz-osx-font-smoothing: grayscale;
            text-rendering: optimizeLegibility;
        }

        body {
            font-family: var(--font-sans);
            font-size: var(--text-base);
            line-height: 1.6;
            color: var(--color-text-primary);
            background-color: var(--color-bg);
            min-height: 100vh;
        }

        /* ===== Utility Classes ===== */
        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 var(--space-md);
        }

        @media (min-width: 768px) {
            .container { padding: 0 var(--space-lg); }
        }

        @media (min-width: 1024px) {
            .container { padding: 0 var(--space-xl); }
        }

        /* ===== Interactive Elements Base ===== */
        a {
            color: var(--color-accent);
            text-decoration: none;
            transition: color var(--duration-fast) var(--ease-out);
        }
        a:hover { color: var(--color-accent-hover); }

        button, .btn {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: var(--space-sm);
            padding: var(--space-sm) var(--space-md);
            font-family: inherit;
            font-size: var(--text-sm);
            font-weight: 500;
            line-height: 1;
            border: none;
            border-radius: var(--radius-md);
            cursor: pointer;
            transition: all var(--duration-fast) var(--ease-out);
            outline: none;
        }

        button:focus-visible, .btn:focus-visible {
            box-shadow: 0 0 0 2px var(--color-bg), 0 0 0 4px var(--color-accent);
        }

        .btn-primary {
            background: var(--color-accent);
            color: #FFFFFF;
        }
        .btn-primary:hover {
            background: var(--color-accent-hover);
            transform: translateY(-1px);
            box-shadow: var(--shadow-md);
        }
        .btn-primary:active {
            transform: translateY(0) scale(0.98);
        }

        .btn-secondary {
            background: var(--color-surface);
            color: var(--color-text-primary);
            border: 1px solid var(--color-border);
        }
        .btn-secondary:hover {
            background: var(--color-surface-hover);
            border-color: rgba(0,0,0,0.12);
        }

        /* ===== Card Component ===== */
        .card {
            background: var(--color-surface);
            border-radius: var(--radius-xl);
            padding: var(--space-lg);
            box-shadow: var(--shadow-sm);
            border: 1px solid var(--color-border);
            transition: all var(--duration-base) var(--ease-out);
        }
        .card:hover {
            box-shadow: var(--shadow-lg);
            transform: translateY(-2px);
        }

        /* ===== Input Component ===== */
        input, textarea, select {
            width: 100%;
            padding: var(--space-sm) var(--space-md);
            font-family: inherit;
            font-size: var(--text-base);
            color: var(--color-text-primary);
            background: var(--color-surface);
            border: 1px solid var(--color-border);
            border-radius: var(--radius-md);
            transition: all var(--duration-fast) var(--ease-out);
            outline: none;
        }
        input:hover, textarea:hover, select:hover {
            border-color: rgba(0,0,0,0.15);
        }
        input:focus, textarea:focus, select:focus {
            border-color: var(--color-accent);
            box-shadow: 0 0 0 3px var(--color-accent-light);
        }
        input::placeholder {
            color: var(--color-text-muted);
        }

        /* ===== Section Spacing ===== */
        .section {
            padding: var(--space-3xl) 0;
        }
        @media (min-width: 768px) {
            .section { padding: var(--space-4xl) 0; }
        }

        /* ===== Typography ===== */
        h1 { font-size: var(--text-5xl); font-weight: 600; line-height: 1.1; letter-spacing: -0.02em; }
        h2 { font-size: var(--text-3xl); font-weight: 600; line-height: 1.2; letter-spacing: -0.01em; }
        h3 { font-size: var(--text-xl); font-weight: 600; line-height: 1.3; }
        p { color: var(--color-text-secondary); line-height: 1.6; }

        @media (max-width: 768px) {
            h1 { font-size: var(--text-4xl); }
            h2 { font-size: var(--text-2xl); }
        }

        /* ===== Reduced Motion ===== */
        @media (prefers-reduced-motion: reduce) {
            *, *::before, *::after {
                animation-duration: 0.01ms !important;
                transition-duration: 0.01ms !important;
            }
        }
    </style>
</head>
<body>
    <!-- Page content here -->
</body>
</html>
```

## Key Implementation Rules

1. **Never use inline styles** — all styling through CSS custom properties and classes
2. **Mobile-first media queries** — start with mobile, add `min-width` breakpoints
3. **Semantic HTML** — use `<header>`, `<main>`, `<section>`, `<nav>`, `<footer>`
4. **Accessible by default** — proper heading hierarchy, alt texts, aria-labels on icon buttons
5. **Dark mode support** — add `@media (prefers-color-scheme: dark)` with dark palette tokens

## Dark Mode Addition

When dark mode is needed, add this block:

```css
@media (prefers-color-scheme: dark) {
    :root {
        --color-bg: #000000;
        --color-surface: #1C1C1E;
        --color-surface-hover: #2C2C2E;
        --color-text-primary: #F5F5F7;
        --color-text-secondary: #A1A1A6;
        --color-text-muted: #636366;
        --color-accent: #0A84FF;
        --color-accent-hover: #409CFF;
        --color-accent-light: rgba(10, 132, 255, 0.15);
        --color-border: rgba(255, 255, 255, 0.08);
        --color-shadow: rgba(0, 0, 0, 0.3);
    }
}
```

## Glass Effect Card (Popular Pattern)

```css
.glass-card {
    background: rgba(255, 255, 255, 0.72);
    backdrop-filter: blur(20px) saturate(180%);
    -webkit-backdrop-filter: blur(20px) saturate(180%);
    border: 1px solid rgba(255, 255, 255, 0.4);
    border-radius: var(--radius-xl);
    padding: var(--space-xl);
    box-shadow: var(--shadow-lg);
}

@media (prefers-color-scheme: dark) {
    .glass-card {
        background: rgba(28, 28, 30, 0.72);
        border-color: rgba(255, 255, 255, 0.1);
    }
}
```
