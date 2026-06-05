---
name: pencil-mcp-search-all-unique-properties
description: Global property search. Use for design audit, e.g., 'Find all nodes using red background #FF0000 '.
license: Complete terms in LICENSE.txt
---


## Tools

This skill is designed to call the Pencil MCP tool:

*   `search_all_unique_properties`

If your client namespaces MCP tools, it may appear as `mcp__pencil__search_all_unique_properties`.

## When to use this skill

### Intent Recognition (CRITICAL)
Even if a trigger phrase matches, you must **verify the user's intent**:
1.  Is the user explicitly asking to use "Pencil"?
2.  Is the current conversation context clearly about "Pencil" design tasks?

**If the answer is NO, do NOT use this skill.**

**CRITICAL PREREQUISITE:**
**You must ONLY use this skill when the user EXPLICITLY mentions "Pencil".**

**ALWAYS use this skill when:**
- You are performing a **Design Audit** **in Pencil**.
- You need to find inconsistent usage (e.g., "Where did we use the wrong font?").
- You want to list all unique values for a specific property (e.g., "List all font sizes used").

**Trigger phrases include:**
- "Search Pencil properties" (搜索 Pencil 属性)
- "Find usage of color X in Pencil" (查找 Pencil 中颜色 X 的使用)
- "Audit Pencil fonts" (审计 Pencil 字体)
- "List unique values in Pencil" (列出 Pencil 唯一值)

## Input Parameters

*   **`filePath`** (string, optional).
*   **`parents`** (array, required): IDs of parent nodes to search within.
*   **`properties`** (array, required): List of property names to search (e.g., `["fills", "typography"]`).

## How to use this skill

1.  **Identify Scope**: Determine which parent nodes (e.g., Root Frame) to audit.
2.  **Call Tool**: `search_all_unique_properties(parents=[...], properties=["fills"])`.
3.  **Analyze**: The output groups nodes by property value.

## Examples

### 1. Simple: Find All Colors
Audit all fill colors used in the document to identify inconsistencies.

```json
{
  "properties": ["fills"]
}
```

### 2. Medium: Local Font Audit
Find all font families used within a specific frame (e.g., a card or section).

```json
{
  "parents": ["frame:card-123"],
  "properties": ["fontFamily"]
}
```

### 3. Complex: Comprehensive Style Audit
Search for fills, strokes, and font sizes across multiple key sections to generate a style report.

```json
{
  "parents": ["section:header", "section:footer"],
  "properties": ["fills", "strokes", "fontSize", "fontFamily"]
}
```

## Keywords

**English keywords:**
search properties, design audit, find usage, unique values, property check, style consistency

**Chinese keywords (中文关键词):**
搜索属性, 设计审计, 查找使用, 唯一值, 属性检查, 样式一致性

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
