---
name: pencil-mcp-replace-all-matching-properties
description: Global property batch replace. Use for global style adjustment, e.g., 'Replace all red backgrounds with brand blue'.
license: Complete terms in LICENSE.txt
---


## Tools

This skill is designed to call the Pencil MCP tool:

*   `replace_all_matching_properties`

If your client namespaces MCP tools, it may appear as `mcp__pencil__replace_all_matching_properties`.

## When to use this skill

### Intent Recognition (CRITICAL)
Even if a trigger phrase matches, you must **verify the user's intent**:
1.  Is the user explicitly asking to use "Pencil"?
2.  Is the current conversation context clearly about "Pencil" design tasks?

**If the answer is NO, do NOT use this skill.** (e.g., "Replace properties" might refer to refactoring code).

**CRITICAL PREREQUISITE:**
**You must ONLY use this skill when the user EXPLICITLY mentions "Pencil".**

**ALWAYS use this skill when:**
- You need to make **Global Changes** or **Batch Updates** **in Pencil**.
- The user asks to "Change all X to Y".
- You are refactoring styles (e.g., "Replace hex codes with variables").

**Trigger phrases include:**
- "Replace Pencil properties" (替换 Pencil 属性)
- "Change all colors in Pencil" (修改 Pencil 所有颜色)
- "Batch update Pencil fonts" (批量更新 Pencil 字体)
- "Pencil global style replace" (Pencil 全局样式替换)

## Input Parameters

*   **`filePath`** (string, optional).
*   **`parents`** (array, required): IDs of parent nodes to search within.
*   **`properties`** (array, required): List of replacement rules.
    *   Each rule defines the `property`, `match` (value to find), and `replace` (new value).

## How to use this skill

1.  **Define Rules**: "Find `fills: #FF0000`, Replace with `fills: #0000FF`".
2.  **Call Tool**: `replace_all_matching_properties(...)`.
3.  **Verify**: Call `get_screenshot` to verify the global change.

## Examples

### 1. Simple: Global Color Swap
Replace all instances of Red (#FF0000) with Blue (#0000FF) across the entire document.

```json
{
  "properties": [
    {
      "property": "fills",
      "from": { "color": "#FF0000" },
      "to": { "color": "#0000FF" }
    }
  ]
}
```

### 2. Medium: Local Font Update
Change the font family from "Arial" to "Roboto" only within the Footer section.

```json
{
  "parents": ["frame:footer"],
  "properties": [
    {
      "property": "fontFamily",
      "from": "Arial",
      "to": "Roboto"
    }
  ]
}
```

### 3. Complex: Batch Style Migration
Update multiple properties (color and font) simultaneously across several frames to migrate to a new brand style.

```json
{
  "parents": ["frame:home", "frame:profile"],
  "properties": [
    {
      "property": "fills",
      "from": { "color": "#OLD_COLOR" },
      "to": { "color": "#NEW_COLOR" }
    },
    {
      "property": "fontSize",
      "from": 12,
      "to": 14
    }
  ]
}
```

## Keywords

**English keywords:**
replace properties, batch update, global change, style refactor, bulk edit, theme switch

**Chinese keywords (中文关键词):**
替换属性, 批量更新, 全局修改, 样式重构, 批量编辑, 主题切换

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
