<div align="center">

# pencil-skills

**Pencil MCP design tool skills — design system, UI design, batch operations**

[![GitHub](https://img.shields.io/badge/github-full--statck--skills%2Fpencil-skills-green.svg)](https://github.com/full-statck-skills/pencil-skills)
[![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](LICENSE)
[![Agent Skills](https://img.shields.io/badge/Agent%20Skills-兼容-purple.svg)](https://agentskills.io)

[English](./README.md) | 简体中文

[简介](#-简介) ·
[安装](#-安装) ·
[技能列表](#-技能列表) ·
[支持的智能体](#-支持的智能体) ·
[生态](#-生态)

</div>

---

## 📖 简介

**Pencil MCP 技能** 是一组 AI 编码智能体技能，属于 [Full Stack Skills](https://github.com/partme-ai/full-stack-skills) 生态，由 [PartMe.AI](https://github.com/partme-ai) 维护。

本包包含 **28 个技能**。每个技能是一个独立的 `SKILL.md` 文件，AI 智能体按需加载。

## 📦 安装

```bash
npx skills add full-statck-skills/pencil-skills
```

或按需安装特定技能：

```bash
npx skills add full-statck-skills/pencil-skills --skill <skill-name>
```

## 🎯 技能列表 (28)

| 技能 | 描述 |
|------|------|
| `pencil-design-from-stitch-html` | "When you need to turn Stitch page HTML (or a Stitch URL) into a Pencil .pen design. Parses DOM and Tailwind, applies... |
| `pencil-mcp-batch-design` | Batch execute design changes. The Agent's 'Hands'. Core capability for inserting, updating, moving, or deleting nodes. |
| `pencil-mcp-batch-get` | Batch search and read node information. The Agent's 'Eyes'. Use to find specific components e.g. all nodes named 'But... |
| `pencil-mcp-find-empty-space-on-canvas` | Smartly find empty canvas space. Use to automatically plan artboard placement to avoid overlap and keep the canvas or... |
| `pencil-mcp-get-editor-state` | Get current design environment context. Use when you need to understand what is currently selected, canvas position, ... |
| `pencil-mcp-get-guidelines` | Get design system guidelines. Use to read and understand specifications e.g. Material Design iOS HIG or custom specs ... |
| `pencil-mcp-get-screenshot` | Get node visual screenshot. Visual Verification. Use to capture screenshots after operations to verify if the design ... |
| `pencil-mcp-get-style-guide-tags` | Explore design style tags. Use to get design inspiration, such as 'Modern', 'Dark Mode', 'SaaS' directions. |
| `pencil-mcp-get-style-guide` | Get specific style detailed definitions. Use to get metadata for a specific style, including palettes, typography rul... |
| `pencil-mcp-get-variables` | Read design variables Tokens . Use to get Design Tokens color font variables defined in the current document to ensur... |
| `pencil-mcp-open-document` | Open or create a design document. Use when you need to initialize design tasks, create new files, or switch to specif... |
| `pencil-mcp-replace-all-matching-properties` | Global property batch replace. Use for global style adjustment, e.g., 'Replace all red backgrounds with brand blue'. |
| `pencil-mcp-search-all-unique-properties` | Global property search. Use for design audit, e.g., 'Find all nodes using red background #FF0000 '. |
| `pencil-mcp-set-variables` | Set or update design variables. Use to establish or maintain a Design Token system. |
| `pencil-mcp-snapshot-layout` | Get page layout structure snapshot. Use when you need to understand the current page's DOM-like tree structure to pre... |
| `pencil-skill-creator` | Factory skill for creating new pencil-ui-design-system-* skills. Use when you need to add support for a new design sy... |
| `pencil-ui-design-spec-generator` | Translates vague user requirements into an action-level PENCIL_PLAN sequence of Pencil MCP tool calls . Does not exec... |
| `pencil-ui-design-system-antd` | Initialize Ant Design. design system components in Pencil variables and component overview. |
| `pencil-ui-design-system-bootstrap` | Initialize Bootstrap. design system components in Pencil variables and component overview. |
| `pencil-ui-design-system-echarts` | Initialize ECharts. design system components chart placeholders and data-viz tokens in Pencil. |
| `pencil-ui-design-system-element` | Initialize Element Plus. design system components in Pencil variables and component overview. |
| `pencil-ui-design-system-layui` | Initialize Layui. design system components in Pencil variables and component overview. |
| `pencil-ui-design-system-ucharts` | Initialize uCharts. design system components chart placeholders and data-viz tokens in Pencil. |
| `pencil-ui-design-system-uview` | Initialize uView 2.x . design system components in Pencil variables and component overview. |
| `pencil-ui-design-system-uviewpro` | Initialize uView Pro. design system components in Pencil variables and component overview. |
| `pencil-ui-design-system-vant` | Initialize Vant. design system components in Pencil variables and component overview. |
| `pencil-ui-designer` | The Pencil Orchestrator. Handles the flow of initializing Design System Components based on requirements. |
| `pencil` | "用于通过 Pencil MCP 读取/修改 .pen 设计文件并校验布局。用户提到 pencil/.pen/设计稿编辑、需要列出工具或执行 batch_get/batch_design 时调用。" |

## 🤖 支持的智能体

适用于 [Claude Code](https://code.claude.com)、[Codex](https://developers.openai.com/codex)、[Cursor](https://cursor.com)、[OpenCode](https://opencode.ai)、[Gemini CLI](https://geminicli.com)、[GitHub Copilot](https://github.com/features/copilot)、[Windsurf](https://codeium.com/windsurf) 及 [70+ 其他智能体](https://agentskills.io/clients)。

## 🌐 生态

| 资源 | 链接 |
|------|------|
| **Full Stack Skills** | [github.com/partme-ai/full-stack-skills](https://github.com/partme-ai/full-stack-skills) |
| **全部技能组** | [github.com/full-statck-skills](https://github.com/full-statck-skills) |
| **Agent Skills 规范** | [agentskills.io](https://agentskills.io) |
| **Skills CLI** | [github.com/vercel-labs/skills](https://github.com/vercel-labs/skills) |

## 📄 许可证

Apache 2.0 — 详见 [LICENSE](LICENSE)。
