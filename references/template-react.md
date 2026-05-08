# React Starter Template

Use this as the base when generating React components/pages.

## Project Structure

```
src/
├── styles/
│   └── tokens.css          ← Design tokens (same as HTML template)
├── components/
│   ├── Button/
│   │   ├── Button.tsx
│   │   └── Button.module.css
│   ├── Card/
│   │   ├── Card.tsx
│   │   └── Card.module.css
│   └── Input/
│       ├── Input.tsx
│       └── Input.module.css
├── pages/
│   └── Home.tsx
└── App.tsx
```

## Base Token File (tokens.css)

Import this in the root `App.tsx` or `index.css`. Use the same CSS custom properties defined in `template-html.md`.

## Component Pattern (Button Example)

```tsx
// Button.tsx
import styles from './Button.module.css';

interface ButtonProps {
  variant?: 'primary' | 'secondary' | 'ghost';
  size?: 'sm' | 'md' | 'lg';
  children: React.ReactNode;
  onClick?: () => void;
  disabled?: boolean;
  className?: string;
}

export function Button({
  variant = 'primary',
  size = 'md',
  children,
  onClick,
  disabled = false,
  className = '',
}: ButtonProps) {
  return (
    <button
      className={`${styles.btn} ${styles[variant]} ${styles[size]} ${className}`}
      onClick={onClick}
      disabled={disabled}
    >
      {children}
    </button>
  );
}
```

```css
/* Button.module.css */
.btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: var(--space-sm);
  font-family: inherit;
  font-weight: 500;
  border: none;
  border-radius: var(--radius-md);
  cursor: pointer;
  transition: all var(--duration-fast) var(--ease-out);
  outline: none;
  white-space: nowrap;
}

.btn:focus-visible {
  box-shadow: 0 0 0 2px var(--color-bg), 0 0 0 4px var(--color-accent);
}

.btn:disabled {
  opacity: 0.5;
  cursor: not-allowed;
  transform: none !important;
}

/* Variants */
.primary {
  background: var(--color-accent);
  color: #FFFFFF;
}
.primary:hover:not(:disabled) {
  background: var(--color-accent-hover);
  transform: translateY(-1px);
  box-shadow: var(--shadow-md);
}
.primary:active:not(:disabled) {
  transform: translateY(0) scale(0.98);
}

.secondary {
  background: var(--color-surface);
  color: var(--color-text-primary);
  border: 1px solid var(--color-border);
}
.secondary:hover:not(:disabled) {
  background: var(--color-surface-hover);
  border-color: rgba(0,0,0,0.12);
}

.ghost {
  background: transparent;
  color: var(--color-accent);
}
.ghost:hover:not(:disabled) {
  background: var(--color-accent-light);
}

/* Sizes */
.sm {
  padding: 6px 12px;
  font-size: var(--text-xs);
  border-radius: var(--radius-sm);
}
.md {
  padding: 8px 16px;
  font-size: var(--text-sm);
}
.lg {
  padding: 12px 24px;
  font-size: var(--text-base);
  border-radius: var(--radius-lg);
}
```

## Component Pattern (Card Example)

```tsx
// Card.tsx
import styles from './Card.module.css';

interface CardProps {
  children: React.ReactNode;
  hoverable?: boolean;
  padding?: 'sm' | 'md' | 'lg';
  className?: string;
}

export function Card({
  children,
  hoverable = true,
  padding = 'md',
  className = '',
}: CardProps) {
  return (
    <div className={`${styles.card} ${hoverable ? styles.hoverable : ''} ${styles[`pad-${padding}`]} ${className}`}>
      {children}
    </div>
  );
}
```

```css
/* Card.module.css */
.card {
  background: var(--color-surface);
  border-radius: var(--radius-xl);
  box-shadow: var(--shadow-sm);
  border: 1px solid var(--color-border);
  transition: all var(--duration-base) var(--ease-out);
}

.hoverable:hover {
  box-shadow: var(--shadow-lg);
  transform: translateY(-2px);
}

.pad-sm { padding: var(--space-md); }
.pad-md { padding: var(--space-lg); }
.pad-lg { padding: var(--space-xl); }
```

## Key React-Specific Rules

1. **CSS Modules preferred** — scoped styles, no class name collisions
2. **Design tokens via CSS vars** — NOT JS constants (allows theme switching)
3. **Compound components** — break complex UI into composable pieces
4. **Proper TypeScript interfaces** — all props typed, optional props with defaults
5. **Accessibility** — use semantic elements, add `aria-label` for icon buttons
6. **Forwarded refs** — for components that wrap native elements (inputs, buttons)
