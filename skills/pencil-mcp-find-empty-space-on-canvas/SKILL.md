---
name: pencil-mcp-find-empty-space-on-canvas
description: Smartly find empty canvas space. Use to automatically plan artboard placement to avoid overlap and keep the canvas organized.
license: Complete terms in LICENSE.txt
---


## Tools

This skill is designed to call the Pencil MCP tool:

*   `find_empty_space_on_canvas`

If your client namespaces MCP tools, it may appear as `mcp__pencil__find_empty_space_on_canvas`.

## When to use this skill

### Intent Recognition (CRITICAL)
Even if a trigger phrase matches, you must **verify the user's intent**:
1.  Is the user explicitly asking to use "Pencil"?
2.  Is the current conversation context clearly about "Pencil" design tasks?

**If the answer is NO, do NOT use this skill.**

**CRITICAL PREREQUISITE:**
**You must ONLY use this skill when the user EXPLICITLY mentions "Pencil".**

**ALWAYS use this skill when:**
- You are about to insert a new Frame or Artboard **in Pencil**.
- You want to ensure the new element doesn't overlap with existing work **on the Pencil canvas**.
- You need to organize the canvas.

**Trigger phrases include:**
- "Find space for new screen in Pencil" (为 Pencil 新页面找位置)
- "Where can I draw in Pencil?" (我在 Pencil 哪里画？)
- "Pencil avoid overlap" (Pencil 避免重叠)

## Input Parameters

*   **`width`** (number, required): The width of the required space.
*   **`height`** (number, required): The height of the required space.
*   **`direction`** (string, optional): Search direction relative to node (e.g., "RIGHT", "BOTTOM").
*   **`nodeId`** (string, optional): Starting reference node. If omitted, searches around entire canvas content.
*   **`padding`** (number, optional): Minimum padding distance (default: 100).

## How to use this skill

1.  **Estimate Size**: Determine the size of the element you plan to create.
2.  **Call Tool**: `find_empty_space_on_canvas(width=..., height=...)`.
3.  **Use Result**: The tool returns `{x, y}` coordinates. Use these coordinates in your subsequent `batch_design` call to insert the Frame.

## Examples

### 1. Simple: Find Any Space
Find a spot for a small element (e.g., 100x100).
See [1-find-any.json](examples/1-find-any.json).

### 2. Medium: Place Next to Node
Find space to the right of an existing frame.
See [2-place-next-to.json](examples/2-place-next-to.json).

### 3. Complex: Organized Layout
Find space for a large dashboard with ample padding below the header section.
See [3-organized-layout.json](examples/3-organized-layout.json).

## Keywords

**English keywords:**
find space, empty canvas, layout planning, avoid overlap, next to node, smart placement

**Chinese keywords (中文关键词):**
查找空白, 空画布, 布局规划, 避免重叠, 节点旁, 智能放置

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
