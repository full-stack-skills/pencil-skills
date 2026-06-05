<div align="center">

# pencil-skills

**Pencil MCP design tool skills — design system, UI design, batch operations**

[![GitHub](https://img.shields.io/badge/github-full--statck--skills%2Fpencil-skills-green.svg)](https://github.com/full-statck-skills/pencil-skills)
[![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](LICENSE)
[![Agent Skills](https://img.shields.io/badge/Agent%20Skills-Compatible-purple.svg)](https://agentskills.io)

English | [简体中文](./README.zh-CN.md)

[Introduction](#-introduction) ·
[Install](#-install) ·
[Skills](#-skills) ·
[Supported Agents](#-supported-agents) ·
[Ecosystem](#-ecosystem)

</div>

---

## 📖 Introduction

**Pencil MCP Skills** is a curated collection of Agent Skills for AI coding agents, part of the [Full Stack Skills](https://github.com/partme-ai/full-stack-skills) ecosystem maintained by [PartMe.AI](https://github.com/partme-ai).

This package includes **28 skills**. Each skill is a self-contained `SKILL.md` file that AI agents load on-demand.

## 📦 Install

```bash
npx skills add full-statck-skills/pencil-skills
```

Or install specific skills:

```bash
npx skills add full-statck-skills/pencil-skills --skill <skill-name>
```

## 🎯 Skills (28)

| Skill | Description |
|-------|-------------|
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

## 🤖 Supported Agents

Works with [Claude Code](https://code.claude.com), [Codex](https://developers.openai.com/codex), [Cursor](https://cursor.com), [OpenCode](https://opencode.ai), [Gemini CLI](https://geminicli.com), [GitHub Copilot](https://github.com/features/copilot), [Windsurf](https://codeium.com/windsurf), and [70+ others](https://agentskills.io/clients).

### Claude Code Installation

**Option 1: npx skills CLI (Recommended)**

```bash
npx skills add full-statck-skills/pencil-skills
```

**Option 2: Manual Installation**

```bash
git clone https://github.com/full-statck-skills/pencil-skills.git
cp -r pencil-skills/skills/* .claude/skills/
```

For more details, see the [Claude Code Skills Guide](https://code.claude.com/docs/en/skills) and [Agent Skills Spec](https://agentskills.io/).

## 🌐 Ecosystem

| Resource | Link |
|----------|------|
| **Full Stack Skills** | [github.com/partme-ai/full-stack-skills](https://github.com/partme-ai/full-stack-skills) |
| **All Skill Groups** | [github.com/full-statck-skills](https://github.com/full-statck-skills) |
| **Agent Skills Spec** | [agentskills.io](https://agentskills.io) |
| **Skills CLI** | [github.com/vercel-labs/skills](https://github.com/vercel-labs/skills) |

## 📄 License

Apache 2.0 — see [LICENSE](LICENSE).
