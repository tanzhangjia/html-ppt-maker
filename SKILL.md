---
name: html-ppt-maker
description: "Generate single-file HTML presentations (PPT风格) with web research and image sourcing. Use when the user wants to: (1) Create presentation slides from a topic, (2) Research a topic and build slides, (3) Find online images and embed them in slides, (4) Generate any HTML-based PPT. Output is one self-contained .html file with multi-section scroll layout."
---

# HTML PPT Maker

## 核心风格规范

**白底、浅灰外面、精致卡片、有CSS细节。**

### 页面背景
- 页面外背景: `#f5f7fa`（浅灰）
- 每页卡片: `#fff`（纯白）
- 圆角 `border-radius: 16px`
- 阴影: `0 1px 3px rgba(0,0,0,0.04), 0 8px 32px rgba(0,0,0,0.04)`

### 封面
- 深蓝渐变: `#0f172a → #1e3a5f → #3b82f6`
- 白字，居中。所有文字 `color:#fff`，禁止半透明

### 卡片（核心样式）

每张卡片必须有 **顶部彩色渐变条**（4px高），用不同颜色区分层级：

| 用途 | Class | 颜色 |
|------|-------|------|
| 主信息 | `.card.blue` | `#3b82f6 → #60a5fa` |
| 成功/正向 | `.card.green` | `#22c55e → #4ade80` |
| 警告/增长 | `.card.orange` | `#f97316 → #fb923c` |
| 创意 | `.card.purple` | `#8b5cf6 → #a78bfa` |
| 品牌/女性 | `.card.pink` | `#ec4899 → #f472b6` |
| 科技/冷静 | `.card.teal` | `#14b8a6 → #2dd4bf` |
| 危险 | `.card.rose` | `#e11d48 → #fb7185` |
| 注意 | `.card.amber` | `#d97706 → #fbbf24` |
| 深紫 | `.card.indigo` | `#4f46e5 → #818cf8` |

卡片内其他样式：
- 背景 `#fff`，边框 `#e9edf2`
- 圆角 `12px`，内边距 `24px`
- 标题 `17px` 深色 `#0f172a`，正文 `15px` `#475569`
- hover 阴影加深效果

### 目录页
- 2列 × N行 彩色卡片网格
- 每张卡片: 大号数字(32px) + 标题 + 描述
- 每张卡片顶部彩条颜色不同

### 内容布局
- `h2`: 30px 粗体 `#0f172a`，带 flex gap
- `.section-title`: 13px 蓝色 `#3b82f6`，letter-spacing 3px，大写
- 正文: 17px `#475569`，行高 1.8
- 列表: 16px
- `two-col` / `three-col` 网格

### 流程图
- `.flow-box`: `#f8fafc`，圆角10px，浅阴影
- `.flow-arrow`: `#94a3b8`

### 大数字
- `.big-num`: 48px 800weight，渐变文字 `#3b82f6 → #8b5cf6`

### 代码块
- `.code-block`: 浅灰底 + monospace 字体，用于展示prompt示例

### 总结框
- `.summary-box`: 浅蓝色渐变边框，圆角14px

## 工作流

1. 问主题 + 大约页数
2. 网络搜索内容素材
3. 生成HTML，按上面的组件拼装：
   `封面 → 目录页(TOC卡片) → [内容页(双栏/三栏/流程图等)] × N → 总结页`
4. 自检：
   - 每页白底，浅灰外底
   - 卡片都有顶部彩条
   - 正文16px+
   - 没大面积空白
5. 交付

## 风格分层

本skill是一个"风格一族"——白底精致卡片风格。未来如果有新风格（例如全黑科技风、手绘风、复古风），在 `references/layouts/` 下作为独立风格族存放，每个风格族有自己独立的模板+说明。
