# Vue 3 Starter Template

Use this as the base when generating Vue components/pages.

## Project Structure

```
src/
├── styles/
│   └── tokens.css          ← Design tokens (same as HTML template)
├── components/
│   ├── BaseButton.vue
│   ├── BaseCard.vue
│   └── BaseInput.vue
├── views/
│   └── HomeView.vue
├── App.vue
└── main.ts
```

## Component Pattern (Button Example)

```vue
<!-- BaseButton.vue -->
<script setup lang="ts">
interface Props {
  variant?: 'primary' | 'secondary' | 'ghost'
  size?: 'sm' | 'md' | 'lg'
  disabled?: boolean
}

withDefaults(defineProps<Props>(), {
  variant: 'primary',
  size: 'md',
  disabled: false,
})
</script>

<template>
  <button
    :class="['btn', variant, size]"
    :disabled="disabled"
  >
    <slot />
  </button>
</template>

<style scoped>
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
}

.ghost {
  background: transparent;
  color: var(--color-accent);
}
.ghost:hover:not(:disabled) {
  background: var(--color-accent-light);
}

/* Sizes */
.sm { padding: 6px 12px; font-size: var(--text-xs); }
.md { padding: 8px 16px; font-size: var(--text-sm); }
.lg { padding: 12px 24px; font-size: var(--text-base); border-radius: var(--radius-lg); }
</style>
```

## Component Pattern (Card Example)

```vue
<!-- BaseCard.vue -->
<script setup lang="ts">
interface Props {
  hoverable?: boolean
  padding?: 'sm' | 'md' | 'lg'
}

withDefaults(defineProps<Props>(), {
  hoverable: true,
  padding: 'md',
})
</script>

<template>
  <div :class="['card', { hoverable }, `pad-${padding}`]">
    <slot />
  </div>
</template>

<style scoped>
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
</style>
```

## Page Pattern (Landing Page)

```vue
<!-- HomeView.vue -->
<script setup lang="ts">
import BaseButton from '@/components/BaseButton.vue'
import BaseCard from '@/components/BaseCard.vue'
</script>

<template>
  <main>
    <!-- Hero Section -->
    <section class="hero">
      <div class="container">
        <h1 class="hero-title">{{标题}}</h1>
        <p class="hero-desc">{{副标题描述}}</p>
        <div class="hero-actions">
          <BaseButton size="lg">开始使用</BaseButton>
          <BaseButton variant="secondary" size="lg">了解更多</BaseButton>
        </div>
      </div>
    </section>

    <!-- Features Section -->
    <section class="features section">
      <div class="container">
        <h2 class="section-title">核心特性</h2>
        <div class="features-grid">
          <BaseCard v-for="i in 3" :key="i">
            <h3>特性 {{ i }}</h3>
            <p>特性描述文字</p>
          </BaseCard>
        </div>
      </div>
    </section>
  </main>
</template>

<style scoped>
.hero {
  padding: var(--space-4xl) 0;
  text-align: center;
}

.hero-title {
  font-size: var(--text-6xl);
  font-weight: 600;
  line-height: 1.1;
  letter-spacing: -0.02em;
  margin-bottom: var(--space-md);
}

.hero-desc {
  font-size: var(--text-xl);
  color: var(--color-text-secondary);
  max-width: 600px;
  margin: 0 auto var(--space-xl);
}

.hero-actions {
  display: flex;
  gap: var(--space-md);
  justify-content: center;
}

.section-title {
  text-align: center;
  margin-bottom: var(--space-2xl);
}

.features-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: var(--space-lg);
}

@media (max-width: 768px) {
  .hero-title { font-size: var(--text-4xl); }
  .hero-desc { font-size: var(--text-lg); }
  .hero-actions { flex-direction: column; align-items: center; }
}
</style>
```

## Key Vue-Specific Rules

1. **Scoped styles** — always use `<style scoped>` for component isolation
2. **Composition API** — use `<script setup lang="ts">` syntax
3. **CSS custom properties** — design tokens shared via global tokens.css
4. **Base prefix** — reusable components named `Base*` (BaseButton, BaseCard, BaseInput)
5. **Slot-based composition** — use `<slot>` for flexible content injection
6. **Props with defaults** — use `withDefaults(defineProps<T>(), {...})`
