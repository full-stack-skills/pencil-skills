---
name: pencil-mcp-get-editor-state
description: Get current design environment context. Use when you need to understand what is currently selected, canvas position, and environment state before any task.
license: Complete terms in LICENSE.txt
---


## Tools

This skill is designed to call the Pencil MCP tool:

*   `get_editor_state`

If your client namespaces MCP tools, it may appear as `mcp__pencil__get_editor_state`.

## When to use this skill

### Intent Recognition (CRITICAL)
Even if a trigger phrase matches, you must **verify the user's intent**:
1.  Is the user explicitly asking to use "Pencil"?
2.  Is the current conversation context clearly about "Pencil" design tasks?

**If the answer is NO, do NOT use this skill.** (e.g., "What is selected?" might refer to selected text in the IDE, not the Pencil canvas).

**CRITICAL PREREQUISITE:**
**You must ONLY use this skill when the user EXPLICITLY mentions "Pencil".**

**ALWAYS use this skill when:**
- You need to know what the user has currently selected on the canvas.
- You need to check the active document path.
- You are starting a new design task and need to orient yourself.
- The user asks "What am I looking at?" or "Get context" **in Pencil**.

**Trigger phrases include:**
- "Get Pencil editor state" (获取 Pencil 编辑器状态)
- "Check current selection in Pencil" (检查 Pencil 当前选区)
- "What is selected in Pencil?" (Pencil 中选中了什么？)
- "Where am I on the Pencil canvas?" (我在 Pencil 画布哪里？)

## Input Parameters

*   **`include_schema`** (boolean, optional): 
    *   Set to `true` if you want the `.pen` file schema to be included. 
    *   If you are already aware of the schema, set to `false` (default) to save context.

## How to use this skill

1.  **Call the MCP Tool**: Invoke `get_editor_state`.
2.  **Analyze Output**:
    *   Check `selection`: List of selected node IDs.
    *   Check `activePageId`: Current page ID.
    *   Check `filePath`: Path of the current document.

## Examples

### 1. Simple: Basic State Check
Get the current state to understand what the user is looking at.
See [1-basic-check.json](examples/1-basic-check.json).

### 2. Medium: State with Schema
Get state including the .pen file schema to understand the document structure definitions.
See [2-with-schema.json](examples/2-with-schema.json).

### 3. Complex: State Verification (Explicit)
Explicitly checking state during a multi-step workflow where schema is already known.
See [3-explicit-check.json](examples/3-explicit-check.json).

## Keywords

**English keywords:**
get state, editor context, current selection, active document, canvas position, check environment

**Chinese keywords (中文关键词):**
获取状态, 编辑器上下文, 当前选区, 选中节点, 画布位置, 环境检查

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

## 使用流程

### Step 1: 环境准备
确保开发环境已安装必要的依赖和工具。

### Step 2: 配置初始化
根据项目需求进行基础配置。

### Step 3: 核心功能使用
按照示例代码实现核心功能。

### Step 4: 测试验证
运行测试确保功能正常。

### Step 5: 部署上线
完成开发后进行部署和监控。
