---
name: pencil-ui-design-system-echarts
description: Initialize ECharts. design system components chart placeholders and data-viz tokens in Pencil.
license: Complete terms in LICENSE.txt
---


# ECharts Design System Initializer

**Constraint**: Only use this skill when the user explicitly mentions "Pencil" and "ECharts" or when orchestrating a Pencil design system initialization task for charts.

## When to use this skill

Use this skill when you need to initialize a chart/design system based on ECharts specifications in a .pen file: set up chart theme colors and create placeholder frames for chart types (line, bar, pie, etc.).

## How to use this skill

This skill outputs a PENCIL_PLAN. The Agent then calls Pencil MCP tools in order: `open_document`, `set_variables`, `batch_design`, optionally `get_screenshot`.

### Step 1: Initialize Variables (set_variables)

Use `mcp__pencil__set_variables` to register ECharts-related design tokens (chart theme colors, font). Follow .pen file schema.

**Chart colors (palette)**
- `echarts-color-1`: `#5470c6`
- `echarts-color-2`: `#91cc75`
- `echarts-color-3`: `#fac858`
- `echarts-color-4`: `#ee6666`
- `echarts-color-5`: `#73c0de`

**Axis / grid / text**
- `echarts-axis-line-color`: `#6e7079`
- `echarts-split-line-color`: `#e0e6f1`
- `echarts-text-color`: `#6e7079`
- `echarts-font-size`: `12px`

Fill from ECharts theme docs if more tokens are needed.

### Step 2: Create Component Overview Structure (batch_design)

Use `mcp__pencil__batch_design` to create a "Charts Overview" frame with placeholder sections for chart types (data-viz components):

1. **Basic Charts (基础图表)**
   - Line, Bar, Pie, Scatter, Radar, Gauge
2. **Complex Charts (复杂图表)**
   - Candlestick, Heatmap, Tree, Treemap, Sunburst, Parallel, Sankey, Funnel, PictorialBar
3. **Containers (容器)**
   - Chart container placeholder, Legend placeholder, Grid placeholder

Organize frames using Auto Layout. Keep each `batch_design` call to maximum 25 operations.

## Best Practices

- Verify token values against ECharts theme documentation.
- Use `set_variables` with `replace: false` unless a full reset is requested.
- Chart "components" here are placeholder frames for layout; actual chart config is code-side.

## Keywords

pencil, echarts, chart, design system, init, variables, data visualization

## References

- `references/contract.md` – Design tokens and chart type naming.
- `references/official.md` – Link to official documentation.
- `references/examples.md` – Example PENCIL_PLAN.
- `references/components.md` – Chart type specifications.

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
