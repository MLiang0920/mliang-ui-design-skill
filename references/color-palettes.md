# Pre-Built Harmonious Color Palettes

These palettes are tested for harmony, contrast compliance, and professional quality. 
Use these directly — DO NOT invent random colors.

## Light Themes

### 1. Apple Neutral (DEFAULT — use when unsure)
Best for: General tools, SaaS, productivity apps
```
bg: #FAFAFA | surface: #FFFFFF | text: #1D1D1F | secondary: #6E6E73 | accent: #007AFF
```

### 2. Warm Stone
Best for: Lifestyle, wellness, food, hospitality
```
bg: #FAF9F7 | surface: #FFFFFF | text: #1A1816 | secondary: #6B6560 | accent: #D97706
```

### 3. Cool Slate
Best for: Enterprise, fintech, B2B, data tools
```
bg: #F8FAFC | surface: #FFFFFF | text: #0F172A | secondary: #475569 | accent: #2563EB
```

### 4. Sage Green
Best for: Health, sustainability, nature, education
```
bg: #F8FAF8 | surface: #FFFFFF | text: #1A2E1A | secondary: #5C6E5C | accent: #16A34A
```

### 5. Soft Violet
Best for: Creative tools, design, art, social
```
bg: #FAFAFF | surface: #FFFFFF | text: #1E1B4B | secondary: #6B6394 | accent: #7C3AED
```

### 6. Rose Blush
Best for: Beauty, fashion, wedding, feminine brands
```
bg: #FFFBFB | surface: #FFFFFF | text: #2D1F25 | secondary: #7A5A64 | accent: #E11D48
```

### 7. Ocean Teal
Best for: Travel, hospitality, fresh brands, startups
```
bg: #F7FFFE | surface: #FFFFFF | text: #134E4A | secondary: #5C8A85 | accent: #0D9488
```

## Dark Themes

### 8. Midnight (DEFAULT dark)
Best for: Developer tools, media, entertainment, dashboards
```
bg: #000000 | surface: #1C1C1E | text: #F5F5F7 | secondary: #A1A1A6 | accent: #0A84FF
```

### 9. Charcoal
Best for: Professional dark UIs, trading, analytics
```
bg: #0A0A0B | surface: #18181B | text: #FAFAFA | secondary: #A1A1AA | accent: #3B82F6
```

### 10. Deep Navy
Best for: Finance, crypto, trading platforms
```
bg: #0F172A | surface: #1E293B | text: #F8FAFC | secondary: #94A3B8 | accent: #22C55E
```

### 11. Purple Night
Best for: AI/ML tools, gaming, creative
```
bg: #0F0F23 | surface: #1E1D35 | text: #E2E8F0 | secondary: #94A3B8 | accent: #A78BFA
```

### 12. Warm Dark
Best for: Music, media, content platforms
```
bg: #0C0A09 | surface: #1C1917 | text: #FAFAF9 | secondary: #A8A29E | accent: #F59E0B
```

## Glassmorphism Themes

### 13. Frosted Light
```
bg: linear-gradient(135deg, #667eea 0%, #764ba2 100%)
surface: rgba(255,255,255,0.72) | backdrop-filter: blur(20px) saturate(180%)
border: 1px solid rgba(255,255,255,0.4)
text: #1D1D1F | accent: #6366F1
```

### 14. Frosted Dark
```
bg: linear-gradient(135deg, #0f0c29 0%, #302b63 50%, #24243e 100%)
surface: rgba(28,28,30,0.6) | backdrop-filter: blur(20px) saturate(150%)
border: 1px solid rgba(255,255,255,0.08)
text: #F5F5F7 | accent: #818CF8
```

## Usage Rules

1. Pick ONE palette per project — never mix palettes
2. The accent color is for buttons and links ONLY (max 10% of visible area)
3. If you need a second color (e.g., success/warning), derive from the accent:
   - Success: shift hue to green
   - Warning: shift hue to amber
   - Danger: always #DC2626 (light) or #EF4444 (dark)
4. For hover states: darken accent by 10-15% (light theme) or lighten by 10-15% (dark theme)
5. For disabled states: reduce opacity to 0.5
6. For dividers/borders: use text color at 6-8% opacity (light) or white at 8-10% opacity (dark)
