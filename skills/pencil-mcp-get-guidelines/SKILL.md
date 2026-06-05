---
name: pencil-mcp-get-guidelines
description: Get design system guidelines. Use to read and understand specifications e.g. Material Design iOS HIG or custom specs before designing.
license: Complete terms in LICENSE.txt
---


## Tools

This skill is designed to call the Pencil MCP tool:

*   `get_guidelines`

If your client namespaces MCP tools, it may appear as `mcp__pencil__get_guidelines`.

## When to use this skill

### Intent Recognition (CRITICAL)
Even if a trigger phrase matches, you must **verify the user's intent**:
1.  Is the user explicitly asking to use "Pencil"?
2.  Is the current conversation context clearly about "Pencil" design tasks?

**If the answer is NO, do NOT use this skill.**

**CRITICAL PREREQUISITE:**
**You must ONLY use this skill when the user EXPLICITLY mentions "Pencil".**

**ALWAYS use this skill when:**
- You need instructions on **How** to design for a specific system **in Pencil**.
- You are generating code (`topic='code'`).
- You are building a landing page (`topic='landing-page'`).
- You need to know the `.pen` schema details.

**Trigger phrases include:**
- "Get Pencil design guidelines" (获取 Pencil 设计指南)
- "How to use Tailwind in Pencil?" (怎么在 Pencil 里用 Tailwind？)
- "Pencil coding rules" (Pencil 编码规则)
- "Pencil landing page best practices" (Pencil 落地页最佳实践)

## Input Parameters

*   **`topic`** (string, required): The topic to retrieve.
    *   `design-system`: Composing screens with components.
    *   `code`: Code generation rules.
    *   `tables`: Working with tables.
    *   `tailwind`: Tailwind CSS specs.
    *   `landing-page`: High-conversion page design.

## How to use this skill

1.  **Select Topic**: Choose the relevant topic based on user intent.
2.  **Call Tool**: `get_guidelines(topic='design-system')`.
3.  **Read & Apply**: Use the returned text as instructions for your subsequent `batch_design` calls.

## Examples

### 1. Simple: Design System Guidelines
Understand how to use the available components.

```json
{
  "topic": "design-system"
}
```

### 2. Medium: Code Handoff Guidelines
Get rules for generating code from the design, useful for "Code Handoff" tasks.

```json
{
  "topic": "code"
}
```

### 3. Complex: Landing Page Best Practices
Get specific guidelines for designing high-conversion landing pages when the user asks for a marketing site.

```json
{
  "topic": "landing-page"
}
```

## Keywords

**English keywords:**
get guidelines, design rules, best practices, coding specs, documentation, how-to

**Chinese keywords (中文关键词):**
获取指南, 设计规则, 最佳实践, 编码规范, 文档, 如何做

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
