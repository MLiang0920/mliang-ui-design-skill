# MLiang UI Design Skill

> 让 AI Agent 写出真正好看的 UI 代码

## 这是什么？

这是一个 [WorkBuddy](https://www.codebuddy.cn/) Skill，解决 AI Agent 写 UI 代码时**配色丑、布局乱、缺乏设计感**的通病。

安装后，Agent 在生成 Web UI 代码时会自动遵循：
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

### 方法一：直接复制（推荐）

将整个文件夹复制到你的 WorkBuddy Skills 目录：

```bash
# 用户级（所有项目可用）
cp -r mliang-ui-design-skill/ ~/.workbuddy/skills/web-ui-codegen/

# 项目级（仅当前项目可用）
cp -r mliang-ui-design-skill/ .workbuddy/skills/web-ui-codegen/
```

### 方法二：克隆仓库

```bash
git clone https://github.com/MLiang0920/mliang-ui-design-skill.git
cp -r mliang-ui-design-skill/ ~/.workbuddy/skills/web-ui-codegen/
```

## 文件结构

```
mliang-ui-design-skill/
├── SKILL.md                    # 核心指令（配色规则、布局规则、反模式清单）
├── README.md                   # 本文件
└── references/
    ├── template-html.md        # HTML/CSS/JS 完整启动模板
    ├── template-react.md       # React + CSS Modules 组件模板
    ├── template-vue.md         # Vue 3 Composition API 组件模板
    └── color-palettes.md       # 14 套预置和谐配色方案
```

## 使用方式

安装后无需额外操作。当你让 AI 做 Web UI 相关任务时，Skill 会自动生效。

你也可以在对话中输入 `/web-ui-codegen` 手动激活。

## 设计哲学

默认遵循 **Apple 风格简约主义**：
- 大量留白（元素之间充足的呼吸空间）
- 微妙的阴影和层次感
- 统一圆角（12-16px 卡片，8px 按钮）
- 柔和和谐的配色 + 单一强调色
- 流畅的微交互（150-300ms）
- 清晰的字体层级

## 适配 ui-ux-pro-max

本 Skill 可与 `ui-ux-pro-max` Skill 配合使用：
- `ui-ux-pro-max`：负责设计决策查询（选什么风格、配色、字体）
- `web-ui-codegen`：负责代码输出质量（确保写出来的代码好看）

## 作者

**MLiang** (丁觉昇)

- GitHub: [@MLiang0920](https://github.com/MLiang0920)
- Email: 2980125919@qq.com

## License

MIT
