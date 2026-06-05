---
name: pencil-ui-designer
description: The Pencil Orchestrator. Handles the flow of initializing Design System Components based on requirements.
license: Apache 2.0
---


# Pencil Designer (Master Skill)

This is the entry point for all Pencil design tasks. It acts as the **"Orchestrator Agent"** that plans and executes the component initialization workflow.

## When to use this skill

### Intent Recognition (CRITICAL)
Even if a trigger phrase matches, you must **verify the user's intent**:
1.  Is the user explicitly asking to use "Pencil"?
2.  Is the current conversation context clearly about "Pencil" design tasks?

**If the answer is NO, do NOT use this skill.**

**CRITICAL PREREQUISITE:**
**You must ONLY use this skill when the user EXPLICITLY mentions "Pencil".**

**Trigger phrases include:**
- "Pencil, initialize components for..." (Pencil, 初始化...组件)
- "Use Pencil to design system..." (使用 Pencil 设计系统...)
- "Pencil flow..." (Pencil 流...)

## Workflow

### 1) Intent Classification

Determine the target framework and components required.

### 2) Framework Routing

Route the request to the specific `pencil-ui-design-system-*` skill.

**Mapping:**
- `layui` -> `pencil-ui-design-system-layui`
- `antd`, `ant design` -> `pencil-ui-design-system-antd`
- `bootstrap` -> `pencil-ui-design-system-bootstrap`
- `element`, `element-plus` -> `pencil-ui-design-system-element`
- `uview` -> `pencil-ui-design-system-uview`
- `uview pro`, `uviewpro` -> `pencil-ui-design-system-uviewpro`
- `vant` -> `pencil-ui-design-system-vant`
- `ucharts` -> `pencil-ui-design-system-ucharts`
- `echarts` -> `pencil-ui-design-system-echarts`

### 3) Execution

Invoke the target skill to generate the "Design System Components" initialization plan.

### 4) Output

Return the structured plan (JSON/Action List) to the user.

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
