# MLiang UI Design Skill

> Make AI agents write truly beautiful UI code.

## What is this?

A [WorkBuddy](https://www.codebuddy.cn/) Skill that solves the common problem of AI-generated UI looking ugly — bad color combinations, inconsistent spacing, and lack of design sense.

Once installed, the agent automatically enforces:
- Validated harmonious color palettes (14 pre-built palettes)
- Strict spacing rhythm system (4px base grid)
- Modular typography scale (1.25 ratio)
- Layered shadow system (5 depth levels)
- Complete interaction states (hover/focus/active)
- Apple-style minimalist design as default aesthetic

## Supported Frameworks

- HTML / CSS / JavaScript (vanilla)
- React (CSS Modules)
- Vue 3 (Scoped Styles + Composition API)

## Core Problems Solved

| Common Issue | How This Skill Fixes It |
|---|---|
| Random, clashing colors | Forces selection from 14 pre-validated palettes |
| Inconsistent spacing | 4px base grid + spacing scale |
| Missing interaction states | Every component must have hover/focus/active |
| Shadows too heavy or fake | Layered shadow system (xs→xl, 5 levels) |
| Chaotic font sizes | Modular type scale |
| No design sense overall | Apple-style default + anti-pattern blacklist |

## Installation

### Option 1: Direct Copy (Recommended)

Copy the folder to your WorkBuddy Skills directory:

```bash
# User-level (available across all projects)
cp -r mliang-ui-design-skill/ ~/.workbuddy/skills/web-ui-codegen/

# Project-level (current project only)
cp -r mliang-ui-design-skill/ .workbuddy/skills/web-ui-codegen/
```

### Option 2: Clone Repository

```bash
git clone https://github.com/MLiang0920/mliang-ui-design-skill.git
cp -r mliang-ui-design-skill/ ~/.workbuddy/skills/web-ui-codegen/
```

## File Structure

```
mliang-ui-design-skill/
├── SKILL.md                    # Core instructions (color rules, layout rules, anti-patterns)
├── README.md                   # This file
├── README_CN.md                # 中文文档
└── references/
    ├── template-html.md        # HTML/CSS/JS starter template
    ├── template-react.md       # React + CSS Modules component template
    ├── template-vue.md         # Vue 3 Composition API component template
    └── color-palettes.md       # 14 pre-built harmonious color palettes
```

## Usage

No extra steps needed after installation. The skill activates automatically when you ask the AI to do Web UI tasks.

You can also type `/web-ui-codegen` in the conversation to manually activate it.

## Design Philosophy

Follows **Apple-style minimalism** by default:
- Generous whitespace (breathing room between elements)
- Subtle shadows and depth
- Consistent border-radius (12-16px for cards, 8px for buttons)
- Harmonious muted colors + single accent color
- Smooth micro-interactions (150-300ms)
- Clear typographic hierarchy

## Works with ui-ux-pro-max

This skill pairs with the `ui-ux-pro-max` skill:
- `ui-ux-pro-max`: Handles design decision queries (which style, colors, fonts to use)
- `web-ui-codegen`: Ensures the generated code actually looks beautiful

## Author

**MLiang**

- GitHub: [@MLiang0920](https://github.com/MLiang0920)
- Email: 2980125919@qq.com

## License

MIT
