---
name: pencil-ui-design-system-antd
description: Initialize Ant Design. design system components in Pencil variables and component overview.
license: Complete terms in LICENSE.txt
---


# Ant Design System Initializer

**Constraint**: Only use this skill when the user explicitly mentions "Pencil" and "Ant Design" (or "antd") or when orchestrating a Pencil design system initialization task.

## When to use this skill

Use this skill when you need to initialize a new design system based on Ant Design specifications, specifically to set up the global color palette and create the initial component library frames in a .pen file.

## How to use this skill

This skill outputs a PENCIL_PLAN. The Agent then calls Pencil MCP tools in order: `open_document`, `set_variables`, `batch_design`, optionally `get_screenshot`.

### Step 1: Initialize Variables (set_variables)

Use `mcp__pencil__set_variables` to register Ant Design design tokens. Follow .pen file schema.

**Primary / Semantic**
- `ant-primary`: `#1677ff`
- `ant-primary-hover`: `#4096ff`
- `ant-success`: `#52c41a`
- `ant-warning`: `#faad14`
- `ant-error`: `#ff4d4f`
- `ant-info`: `#1677ff`

**Neutral / Text**
- `ant-text`: `#000000e0`
- `ant-text-secondary`: `#00000073`
- `ant-border`: `#d9d9d9`
- `ant-bg`: `#ffffff`

**Font & Radius**
- `ant-font-size-base`: `14px`
- `ant-border-radius`: `6px`

Fill from Ant Design token docs if more tokens are needed.

### Step 2: Create Component Overview Structure (batch_design)

Use `mcp__pencil__batch_design` to create a "Components Overview" frame with sections based on Ant Design documentation:

1. **General (通用)**
   - Button, Icon, Typography
2. **Layout (布局)**
   - Grid, Divider, Space
3. **Navigation (导航)**
   - Affix, Breadcrumb, Dropdown, Menu, Pagination, Steps, Tabs
4. **Data Entry (数据录入)**
   - AutoComplete, Cascader, Checkbox, DatePicker, Form, Input, InputNumber, Radio, Rate, Select, Slider, Switch, TimePicker, Transfer, Upload
5. **Data Display (数据展示)**
   - Avatar, Badge, Calendar, Card, Carousel, Collapse, Descriptions, Empty, Image, List, Popover, Statistic, Table, Tabs, Tag, Timeline, Tooltip, Tree
6. **Feedback (反馈)**
   - Alert, Drawer, Message, Modal, Notification, Progress, Result, Skeleton, Spin

Organize frames using Auto Layout. Keep each `batch_design` call to maximum 25 operations.

## Best Practices

- Verify token values against Ant Design token documentation.
- Use `set_variables` with `replace: false` unless a full reset is requested.
- Use Auto Layout for component overview frames.

## Keywords

pencil, antd, ant design, design system, init, variables, components

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
