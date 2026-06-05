---
name: pencil-mcp-get-style-guide
description: Get specific style detailed definitions. Use to get metadata for a specific style, including palettes, typography rules, etc.
license: Complete terms in LICENSE.txt
---


## Tools

This skill is designed to call the Pencil MCP tool:

*   `get_style_guide`

If your client namespaces MCP tools, it may appear as `mcp__pencil__get_style_guide`.

## When to use this skill

### Intent Recognition (CRITICAL)
Even if a trigger phrase matches, you must **verify the user's intent**:
1.  Is the user explicitly asking to use "Pencil"?
2.  Is the current conversation context clearly about "Pencil" design tasks?

**If the answer is NO, do NOT use this skill.**

**CRITICAL PREREQUISITE:**
**You must ONLY use this skill when the user EXPLICITLY mentions "Pencil".**

**ALWAYS use this skill when:**
- You have selected a specific style (from tags) and need its **Details** **for Pencil**.
- You need the color palette or font stack of a specific "Look and Feel".
- The user says "Use the 'Cyberpunk' style" **in Pencil**.

**Trigger phrases include:**
- "Get Pencil style details" (获取 Pencil 风格详情)
- "Apply style X in Pencil" (在 Pencil 中应用风格 X)
- "Retrieve Pencil style guide" (检索 Pencil 风格指南)

## Input Parameters

*   **`id`** (string, optional): The Style Guide ID.
*   **`tags`** (array, optional): 5-10 tags matching the desired style (from `get_style_guide_tags`).

## How to use this skill

1.  **Prerequisite**: Usually call `get_style_guide_tags` first to know what's available.
2.  **Call Tool**: `get_style_guide(tags=["Modern", "SaaS"])` or `get_style_guide(id="...")`.
3.  **Apply**: Use the returned metadata (colors, fonts) in your `batch_design` or `set_variables` calls.

## Examples

### 1. Simple: Get by ID
Retrieve a specific style guide using its unique identifier.

```json
{
  "id": "style:12345"
}
```

### 2. Medium: Search by Single Tag
Find a style guide that matches a specific keyword (e.g., "Modern").

```json
{
  "tags": ["Modern"]
}
```

### 3. Complex: Multi-Tag Search
Find a style guide that fits a complex criteria (e.g., "Dark" mode "SaaS" dashboard).

```json
{
  "tags": ["Dark", "SaaS", "Dashboard"]
}
```

## Keywords

**English keywords:**
get style guide, style details, visual specs, color palette, font rules, apply theme

**Chinese keywords (中文关键词):**
获取风格指南, 风格详情, 视觉规范, 调色板, 字体规则, 应用主题

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
