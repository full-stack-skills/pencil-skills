---
name: pencil-mcp-get-variables
description: Read design variables Tokens . Use to get Design Tokens color font variables defined in the current document to ensure consistency.
license: Complete terms in LICENSE.txt
---


## Tools

This skill is designed to call the Pencil MCP tool:

*   `get_variables`

If your client namespaces MCP tools, it may appear as `mcp__pencil__get_variables`.

## When to use this skill

### Intent Recognition (CRITICAL)
Even if a trigger phrase matches, you must **verify the user's intent**:
1.  Is the user explicitly asking to use "Pencil"?
2.  Is the current conversation context clearly about "Pencil" design tasks?

**If the answer is NO, do NOT use this skill.** (e.g., "Get variables" might refer to environment variables or code variables).

**CRITICAL PREREQUISITE:**
**You must ONLY use this skill when the user EXPLICITLY mentions "Pencil".**

**ALWAYS use this skill when:**
- You need to know the available Design Tokens (Colors, Typography, Spacing) **in Pencil**.
- You want to use semantic names (e.g., `primary-color`) instead of hardcoded hex codes.
- You are checking the current theme.

**Trigger phrases include:**
- "Get Pencil variables" (获取 Pencil 变量)
- "Read Pencil design tokens" (读取 Pencil 设计令牌)
- "Check Pencil colors" (检查 Pencil 颜色)
- "List Pencil theme values" (列出 Pencil 主题值)

## Input Parameters

*   **`filePath`** (string, optional): Path to the `.pen` file.

## How to use this skill

1.  **Call Tool**: `get_variables()`.
2.  **Analyze Output**: The result is a list/map of variable definitions.
3.  **Apply**: Use the variable IDs or names in `batch_design` operations (e.g., `fill: { type: "var", id: "var_123" }`).

## Examples

### 1. Simple: Get All Variables
Retrieve all variables defined in the current document.

```json
{}
```

### 2. Medium: Get from Specific File
Read variables from a different design file (e.g., a shared library).

```json
{
  "filePath": "/Users/design/system/tokens.pen"
}
```

### 3. Complex: Theme Audit (Conceptual)
Same as simple, but used when auditing themes.

```json
{}
```

## Keywords

**English keywords:**
get variables, read tokens, design system, theme values, color palette, typography tokens

**Chinese keywords (中文关键词):**
获取变量, 读取令牌, 设计系统, 主题值, 调色板, 字体令牌

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
