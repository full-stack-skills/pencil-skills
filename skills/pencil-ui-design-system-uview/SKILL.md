---
name: pencil-ui-design-system-uview
description: Initialize uView 2.x . design system components in Pencil variables and component overview.
license: Complete terms in LICENSE.txt
---


# uView Design System Initializer

**Constraint**: Only use this skill when the user explicitly mentions "Pencil" and "uView" (2.x, not uView Pro) or when orchestrating a Pencil design system initialization task.

## When to use this skill

Use this skill when you need to initialize a new design system based on uView 2.x specifications, specifically to set up the global color palette and create the initial component library frames in a .pen file.

## How to use this skill

This skill outputs a PENCIL_PLAN. The Agent then calls Pencil MCP tools in order: `open_document`, `set_variables`, `batch_design`, optionally `get_screenshot`.

### Step 1: Initialize Variables (set_variables)

Use `mcp__pencil__set_variables` to register uView 2.x design tokens. Follow .pen file schema.

**Primary / Semantic**
- `u-type-primary`: `#3c9cff`
- `u-type-success`: `#5ac725`
- `u-type-warning`: `#f9ae3d`
- `u-type-error`: `#f56c6c`
- `u-type-info`: `#909399`

**Text & Border**
- `u-main-color`: `#303133`
- `u-content-color`: `#606266`
- `u-tips-color`: `#909399`
- `u-border-color`: `#e4e7ed`
- `u-radius`: `4px`

**Font**
- `u-font-size-base`: `14px` (28rpx)

Fill from uView 2.x docs if more tokens are needed.

### Step 2: Create Component Overview Structure (batch_design)

Use `mcp__pencil__batch_design` to create a "Components Overview" frame with sections based on uView 2.x documentation:

1. **Basic (基础)**
   - Icon, Button, Layout, Cell, Badge, Tag
2. **Form (表单)**
   - Form, Input, Textarea, Radio, Checkbox, Switch, Rate, Upload, Picker, Select, DatetimePicker, Search, NumberBox, CodeInput
3. **Data (数据)**
   - Table, List, Calendar, CountDown, CountTo, Progress, CircleProgress
4. **Feedback (反馈)**
   - ActionSheet, Modal, Toast, Notify, SwipeAction, Collapse, Popup
5. **Layout (布局)**
   - Grid, Divider, Sticky, IndexList, Swiper, Waterfall
6. **Navigation (导航)**
   - Navbar, Tabbar, Tabs, BackTop, Link, Section

Organize frames using Auto Layout. Keep each `batch_design` call to maximum 25 operations.

## Best Practices

- Verify token values against uView 2.x documentation (distinct from uView Pro).
- Use `set_variables` with `replace: false` unless a full reset is requested.
- Use Auto Layout for component overview frames.

## Keywords

pencil, uview, uview 2, design system, init, variables, components

## References

- `references/contract.md` – Design tokens and component naming.
- `references/official.md` – Link to official documentation.
- `references/examples.md` – Example PENCIL_PLAN.
- `references/components.md` – Component specifications.

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
