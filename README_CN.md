# MLiang UI Design Skill

[English](./README.md)

> 让 AI Agent 写出真正好看的 UI 代码

## 这是什么？

一套适用于**所有 AI 编程助手**（Cursor、Windsurf、Copilot、Claude、WorkBuddy、Cline 等）的 UI 设计规则集，解决 AI 生成 UI 代码时**配色丑、布局乱、缺乏设计感**的通病。

加载到你的 Agent 上下文后，它会自动遵循：
- 经过验证的和谐配色方案（14 套预置 palette）
- 严格的间距韵律系统（4px 基准网格）
- 模块化字体比例（1.25 倍递进）
- 分层阴影体系（5 级深度）
- 完整交互态规范（hover/focus/active）
- Apple 风格简约设计为默认美学

## 支持框架

- HTML / CSS / JavaScript（纯原生）
- React（CSS Modules）
- Vue 3（Scoped Styles + Composition API）

## 核心解决的问题

| 常见问题 | 本 Skill 的做法 |
|---|---|
| 配色随机，不协调 | 强制从 14 套预验证调色板中选取 |
| 间距随意，没有节奏 | 4px 基准网格 + spacing scale |
| 没有交互态 | 每个组件必须有 hover/focus/active |
| 阴影太重或太假 | 分层阴影系统（xs→xl 五级） |
| 字体大小混乱 | 模块化字体比例 |
| 整体没有设计感 | Apple 风格默认 + Anti-pattern 黑名单 |

## 安装方法

### 通用方法（适用于所有 AI Agent）

将 `SKILL.md` 的内容复制到你的 Agent 的指令/规则文件中：

- **Cursor**：粘贴到 `.cursorrules` 或项目规则中
- **Windsurf**：粘贴到 `.windsurfrules`
- **GitHub Copilot**：粘贴到 `.github/copilot-instructions.md`
- **Claude Projects**：作为项目知识添加
- **ChatGPT**：粘贴到自定义指令中
- **Cline / Roo Code**：添加为自定义指令
- **WorkBuddy**：复制文件夹到 `~/.workbuddy/skills/web-ui-codegen/`

### 快速开始

```bash
git clone https://github.com/MLiang0920/mliang-ui-design-skill.git
```

然后将 `SKILL.md` 内容粘贴到你的 Agent 指令文件中，或者如果你的 Agent 支持 Skill/插件系统，直接使用整个文件夹。

### WorkBuddy 专用安装

```bash
# 用户级（所有项目可用）
cp -r mliang-ui-design-skill/ ~/.workbuddy/skills/web-ui-codegen/

# 项目级（仅当前项目可用）
cp -r mliang-ui-design-skill/ .workbuddy/skills/web-ui-codegen/
```

## 文件结构

```
mliang-ui-design-skill/
├── SKILL.md                    # 核心指令（配色规则、布局规则、反模式清单）
├── README.md                   # 英文文档
├── README_CN.md                # 本文件（中文文档）
├── LICENSE                     # MIT 许可证
└── references/
    ├── template-html.md        # HTML/CSS/JS 完整启动模板
    ├── template-react.md       # React + CSS Modules 组件模板
    ├── template-vue.md         # Vue 3 Composition API 组件模板
    └── color-palettes.md       # 14 套预置和谐配色方案
```

## 使用方式

加载到 AI Agent 上下文后无需额外操作，Agent 生成 UI 代码时会自动遵循设计规则。

需要喂给 Agent 的关键文件：
1. **`SKILL.md`** — 核心规则（必须）
2. **`references/color-palettes.md`** — 预置调色板（推荐）
3. **`references/template-*.md`** — 框架模板（选择你使用的技术栈）

## 设计哲学

默认遵循 **Apple 风格简约主义**：
- 大量留白（元素之间充足的呼吸空间）
- 微妙的阴影和层次感
- 统一圆角（12-16px 卡片，8px 按钮）
- 柔和和谐的配色 + 单一强调色
- 流畅的微交互（150-300ms）
- 清晰的字体层级

## 兼容性

| Agent | 使用方式 |
|---|---|
| Cursor | `.cursorrules` 或 Rules 设置 |
| Windsurf | `.windsurfrules` |
| GitHub Copilot | `.github/copilot-instructions.md` |
| Claude (Projects) | 作为项目知识添加 |
| ChatGPT | 粘贴到自定义指令 |
| Cline / Roo Code | 自定义指令 |
| WorkBuddy | Skills 文件夹（`~/.workbuddy/skills/`） |
| 其他任何 Agent | 将 `SKILL.md` 粘贴到系统提示词中 |

## 作者

**MLiang**

- GitHub: [@MLiang0920](https://github.com/MLiang0920)
- Email: 2980125919@qq.com

## 许可证

MIT
