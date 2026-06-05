---
name: pencil-mcp-get-style-guide-tags
description: Explore design style tags. Use to get design inspiration, such as 'Modern', 'Dark Mode', 'SaaS' directions.
license: Complete terms in LICENSE.txt
---


## Tools

This skill is designed to call the Pencil MCP tool:

*   `get_style_guide_tags`

If your client namespaces MCP tools, it may appear as `mcp__pencil__get_style_guide_tags`.

## When to use this skill

### Intent Recognition (CRITICAL)
Even if a trigger phrase matches, you must **verify the user's intent**:
1.  Is the user explicitly asking to use "Pencil"?
2.  Is the current conversation context clearly about "Pencil" design tasks?

**If the answer is NO, do NOT use this skill.**

**CRITICAL PREREQUISITE:**
**You must ONLY use this skill when the user EXPLICITLY mentions "Pencil".**

**ALWAYS use this skill when:**
- You need **Inspiration** **for a Pencil design**.
- The user gives vague style requirements ("Make it cool", "Modern look") **in Pencil**.
- You are exploring design directions.
- **Prerequisite** for `get_style_guide`.

**Trigger phrases include:**
- "Get Pencil style tags" (获取 Pencil 风格标签)
- "Explore Pencil styles" (探索 Pencil 风格)
- "Pencil inspiration" (Pencil 灵感)
- "What styles are available in Pencil?" (Pencil 有什么风格可用？)

## Input Parameters

*   **`id`** (string, optional): Specific style guide ID.
*   **`tags`** (array, optional): Filter tags.

## How to use this skill

1.  **Call Tool**: `get_style_guide_tags()`.
2.  **Analyze**: Look at the returned tags (e.g., "Minimalist", "Cyberpunk", "Corporate").
3.  **Next Step**: Use the interesting tags in `get_style_guide`.

## Examples

### 1. Simple: Explore All Tags
Get a list of all available style tags to find inspiration.

```json
{}
```

### 2. Medium: Get Tags for Specific Style
If a style ID is known (e.g., from a previous session), get its associated tags to find similar styles.

```json
{
  "id": "style:minimalist-dark"
}
```

### 3. Complex: Filter Tags (Conceptual)
Get tags that are relevant to a specific design context (if supported by the backend logic, otherwise same as Simple).

```json
{}
```

## Keywords

**English keywords:**
style tags, design inspiration, explore trends, visual direction, aesthetic tags, mood board

**Chinese keywords (中文关键词):**
风格标签, 设计灵感, 探索趋势, 视觉方向, 美学标签, 情绪板

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
