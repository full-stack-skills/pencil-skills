---
name: pencil-mcp-open-document
description: Open or create a design document. Use when you need to initialize design tasks, create new files, or switch to specific designs.
license: Complete terms in LICENSE.txt
---


## Tools

This skill is designed to call the Pencil MCP tool:

*   `open_document`

If your client namespaces MCP tools, it may appear as `mcp__pencil__open_document`. Full parameter details: [docs/pencil-mcp-tools.md](../../docs/pencil-mcp-tools.md).

## When to use this skill

### Intent Recognition (CRITICAL)
Even if a trigger phrase matches, you must **verify the user's intent**:
1.  Is the user explicitly asking to use "Pencil"?
2.  Is the current conversation context clearly about "Pencil" design tasks?

**If the answer is NO, do NOT use this skill.** (e.g., "Open file" might refer to reading a code file, not a .pen design).

**CRITICAL PREREQUISITE:**
**You must ONLY use this skill when the user EXPLICITLY mentions "Pencil".**

**ALWAYS use this skill when:**
- The user asks to create a **new** design document **in Pencil**.
- The user provides a file path and asks to open it **with Pencil**.
- You need to switch the active editor to a specific `.pen` file.

**Trigger phrases include:**
- "Create a new document in Pencil" (在 Pencil 中新建文档)
- "Pencil open file..." (Pencil 打开文件...)
- "Start a new design with Pencil" (用 Pencil 开始新设计)
- "Pencil switch to [path]" (Pencil 切换到 [路径])

## Input Parameters

*   **`filePathOrTemplate`** (string, required):
    *   Value: `'new'` to create a fresh, empty document.
    *   Value: Absolute file path (e.g., `/path/to/design.pen`) to open an existing file.
    *   **Note**: No other template names are valid.

## How to use this skill

1.  **Analyze Request**: Determine if it's a "New" or "Open" request.
2.  **Call Tool**:
    *   For new: `open_document(filePathOrTemplate='new')`
    *   For existing: `open_document(filePathOrTemplate='/path/to/file.pen')`

## Examples

- **New document**: `open_document(filePathOrTemplate='new')` — initialize a fresh canvas.
- **Open file**: `open_document(filePathOrTemplate='/path/to/design.pen')` — open existing .pen file.
- **Switch context**: Same as open file; use when switching to another .pen in the same session.

## Keywords

**English keywords:**
open document, create file, new design, load file, switch document, initialize canvas

**Chinese keywords (中文关键词):**
打开文档, 创建文件, 新建设计, 加载文件, 切换文档, 初始化画布

## References

- [Pencil MCP 工具说明](../../docs/pencil-mcp-tools.md) — open_document 等方法的完整参数。

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
