---
name: pencil-mcp-set-variables
description: Set or update design variables. Use to establish or maintain a Design Token system.
license: Complete terms in LICENSE.txt
---


## Tools

This skill is designed to call the Pencil MCP tool:

*   `set_variables`

If your client namespaces MCP tools, it may appear as `mcp__pencil__set_variables`.

## When to use this skill

### Intent Recognition (CRITICAL)
Even if a trigger phrase matches, you must **verify the user's intent**:
1.  Is the user explicitly asking to use "Pencil"?
2.  Is the current conversation context clearly about "Pencil" design tasks?

**If the answer is NO, do NOT use this skill.** (e.g., "Set variables" might refer to .env files).

**CRITICAL PREREQUISITE:**
**You must ONLY use this skill when the user EXPLICITLY mentions "Pencil".**

**ALWAYS use this skill when:**
- You are initializing a Design System (e.g., "Init uView Pro colors") **in Pencil**.
- You need to update the theme (e.g., "Apply Dark Mode") **in Pencil**.
- You want to define new Design Tokens.

**Trigger phrases include:**
- "Set Pencil variables" (设置 Pencil 变量)
- "Update Pencil tokens" (更新 Pencil 令牌)
- "Change Pencil theme" (修改 Pencil 主题)
- "Define Pencil colors" (定义 Pencil 颜色)

## Input Parameters

*   **`filePath`** (string, optional): Path to `.pen` file.
*   **`variables`** (object, required): The variable definitions matching the `.pen` schema.
*   **`replace`** (boolean, optional): 
    *   `true`: Completely replace all existing variables.
    *   `false` (default): Merge/Update existing variables.

## How to use this skill

1.  **Define Schema**: Construct the variable objects (Name, Type, Value, Theme Modes).
2.  **Call Tool**: `set_variables(variables={...})`.
3.  **Verify**: Optionally call `get_variables` to confirm changes.

## Examples

### 1. Simple: Add a Color
Register a single new color variable.

```json
{
  "variables": [
    {
      "name": "brand/primary",
      "value": "#0066FF",
      "type": "color"
    }
  ]
}
```

### 2. Medium: Update Theme Tokens
Update multiple variables for a specific theme (e.g., Dark Mode) by merging.

```json
{
  "replace": false,
  "variables": [
    { "name": "bg/default", "value": "#121212", "type": "color" },
    { "name": "text/primary", "value": "#FFFFFF", "type": "color" }
  ]
}
```

### 3. Complex: Full System Replacement
Completely replace the existing variable system with a new set of tokens.

```json
{
  "replace": true,
  "variables": [
    { "name": "spacing/small", "value": 8, "type": "float" },
    { "name": "spacing/medium", "value": 16, "type": "float" },
    { "name": "font/base", "value": "Inter", "type": "string" }
  ]
}
```

## Keywords

**English keywords:**
set variables, update tokens, define theme, design system init, color definition, style dictionary

**Chinese keywords (中文关键词):**
设置变量, 更新令牌, 定义主题, 设计系统初始化, 颜色定义, 样式字典

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
