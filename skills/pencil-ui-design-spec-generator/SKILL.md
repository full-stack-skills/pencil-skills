---
name: pencil-ui-design-spec-generator
description: Translates vague user requirements into an action-level PENCIL_PLAN sequence of Pencil MCP tool calls . Does not execute; outputs the plan only.
license: Complete terms in LICENSE.txt
---


# Pencil UI Design Spec Generator

**Constraint**: Only use this skill when the user explicitly mentions "Pencil" or when orchestrating a Pencil design task (e.g. "use Pencil to draw", "initialize design system with Pencil").

## Purpose

This skill acts as a **planner**. It takes a high-level user request (e.g. "create a login form in Pencil", "init layui design system with Pencil") and outputs a **PENCIL_PLAN**: a strict sequence of steps, each step specifying which Pencil MCP tool to call and with what intent/parameters. The Agent then executes the plan by calling Pencil MCP tools in order; this skill does **not** call any MCP tool.

## Input

- **User request**: e.g. "Create a login form with Pencil", "Initialize uView Pro design system in Pencil", "Draw a dashboard layout in Pencil".

## Output format (STRICT)

Return a **PENCIL_PLAN** as a numbered list. Each step must specify:

- **Tool** (MCP tool name, e.g. `mcp__pencil__open_document`, `mcp__pencil__set_variables`, `mcp__pencil__batch_design`, `mcp__pencil__get_screenshot`).
- **Intent**: What this step achieves.
- **Key parameters**: Minimal parameter summary (e.g. `filePathOrTemplate: 'new'`, `variables: { primary: '#1890ff', ... }`, `operations: "root=I(document, ...)"`).

Example:

```text
PENCIL_PLAN

Step 1: mcp__pencil__open_document
Intent: Create a new design document.
Parameters: filePathOrTemplate: 'new'

Step 2: mcp__pencil__get_editor_state
Intent: Get current document root and reusable components.
Parameters: include_schema: false

Step 3: mcp__pencil__set_variables
Intent: Initialize design system color palette.
Parameters: variables: { primary: '#1890ff', ... }, replace: false

Step 4: mcp__pencil__batch_design
Intent: Create "Components Overview" frame with Basic/Form/Data sections.
Parameters: operations: "root=I(document, { type: 'frame', layout: 'vertical', name: 'Components Overview' }) ..."

Step 5: mcp__pencil__get_screenshot
Intent: Verify the generated layout.
Parameters: nodeId: <root-id from Step 4>
```

## Logic rules

1. **New document**: If the user asks to "create" or "init" and no file is open, start with `open_document('new')` and optionally `get_editor_state`.
2. **Design system init**: If the user asks to "init XXX design system", include `set_variables` (from the corresponding pencil-ui-design-system-* skill) and `batch_design` for component overview; optionally call `get_guidelines(topic: 'design-system')` first.
3. **Single screen / form**: Plan `batch_design` operations (insert frames, text, components); keep each call to at most ~25 operations; then `get_screenshot` to verify.
4. **No execution**: This skill only outputs the PENCIL_PLAN. The Agent (or user) executes by calling the listed MCP tools in order.

## Integration with Pencil path

1. **PRD** or user request → this skill outputs **PENCIL_PLAN**.
2. **pencil-ui-design-system-*** skills provide the concrete variables and component structure for a given design system; the generator may reference them when building the plan.
3. Agent calls **pencil-mcp-*** skills (or MCP tools directly) to execute each step.

## Keywords

**English:** PENCIL_PLAN, Pencil plan, action-level plan, design spec, Pencil steps, MCP tool sequence, plan generator

**中文关键词：** PENCIL_PLAN、Pencil 计划、动作级计划、设计规范、Pencil 步骤、MCP 工具序列、计划生成

## References

- [Pencil MCP 工具说明](../../docs/pencil-mcp-tools.md) — 各 MCP 方法参数与用法。
- [Pencil MCP](../../docs/Pencil%20MCP.md) — 官方 MCP 说明。

## 能力边界

### ✅ 适用场景
- 当你需要使用此技能对应的技术栈时
- 当项目需要遵循最佳实践时
- 当需要快速上手或深入理解核心概念时

### ⚠️ 需要注意
- 复杂业务逻辑需要结合具体场景调整
- 性能优化需要根据实际数据量评估

### ❌ 不适用场景
- 不相关的技术栈或框架
- 需要完全自定义的特殊场景

## 常见陷阱 (Gotchas)

1. **版本兼容性**：注意框架版本与依赖库的兼容性，不同版本 API 可能有差异
2. **配置文件格式**：配置文件格式错误是最常见的问题，建议使用编辑器的语法检查
3. **环境变量**：确保所有必要的环境变量已正确设置，敏感信息不要硬编码
4. **依赖冲突**：多版本共存时注意依赖冲突，使用 lock 文件锁定版本
5. **性能陷阱**：大数据量场景下注意性能优化，避免 N+1 查询等常见问题
