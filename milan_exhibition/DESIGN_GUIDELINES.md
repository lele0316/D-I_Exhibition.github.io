# NICE TOGETHER 展览设计规范文档

## 📋 文档信息

- **项目名称**: NICE TOGETHER - SaloneSatellite 2026
- **版本**: v1.0
- **最后更新**: 2026-04-05
- **设计工具**: Figma / Sketch

---

## 🎨 色彩系统

### 主色

| 颜色名称 | HEX 值 | RGB 值 | 用途 |
|---------|--------|--------|------|
| 荧光亮柠绿 | `#D9FF00` | `rgb(217, 255, 0)` | 主色、强调色、按钮、高亮文字 |
| 淡薰衣草紫 | `#B388EB` | `rgb(179, 136, 235)` | 主色、渐变、背景 |

### 辅助色

| 颜色名称 | HEX 值 | RGB 值 | 用途 |
|---------|--------|--------|------|
| 纯白 | `#FFFFFF` | `rgb(255, 255, 255)` | 文字、背景 |
| 浅灰 | `#F0F0F0` | `rgb(240, 240, 240)` | 次要文字、边框 |
| 深灰 | `#1A1A1A` | `rgb(26, 26, 26)` | 背景、文字 |

### 渐变

```css
/* 海报主渐变 */
background: linear-gradient(135deg, #B388EB 0%, #D9FF00 50%, #B388EB 100%);
```

---

## 📝 字体系统

### 字体族

- **主字体**: Inter
- **字重范围**: 300 (Light) - 900 (Black)

### 字体层级

| 类名 | 字号 | 字重 | 行高 | 字间距 | 用途 |
|-----|------|------|------|--------|------|
| `.font-h1` | 48-72px | 900 | 0.9 | -0.02em | 主标题 |
| `.font-h2` | 36-48px | 900 | 1.1 | -0.01em | 章节标题 |
| `.font-h3` | 28-36px | 700 | 1.2 | 正常 | 板块标题 |
| `.font-h4` | 20-24px | 600 | 1.3 | 正常 | 卡片标题 |
| `.font-body-large` | 18px | 400 | 1.6 | 正常 | 大正文 |
| `.font-body` | 16px | 400 | 1.6 | 正常 | 正文 |
| `.font-body-small` | 14px | 400 | 1.5 | 正常 | 小正文 |
| `.font-caption` | 12px | 400 | 1.4 | 正常 | 说明文字 |
| `.font-brand` | 48px | 500 | 1.1 | -0.02em | 品牌标题 |

### 特殊字体样式

| 类名 | 说明 |
|-----|------|
| `.font-keyword` | 关键词样式（700 字重，荧光绿） |
| `.font-emphasis` | 强调样式（600 字重，荧光绿） |

---

## 📐 间距系统

### 基础间距变量

| 变量名 | 值 | 用途 |
|--------|-----|------|
| `--spacing-xs` | 4px | 微小间距 |
| `--spacing-sm` | 8px | 小间距 |
| `--spacing-md` | 16px | 中等间距 |
| `--spacing-lg` | 24px | 大间距（段落间距） |
| `--spacing-xl` | 32px | 超大间距 |
| `--spacing-2xl` | 48px | 区块间距 |
| `--spacing-3xl` | 64px | 大区块间距 |
| `--spacing-4xl` | 96px | 页面间距 |

### 容器尺寸

| 类名 | 最大宽度 | 用途 |
|-----|---------|------|
| `.content-max-width` | 80rem (1280px) | 主内容容器 |

---

## 🎯 组件规范

### 按钮

#### CTA 按钮（主要行动按钮）

```css
.cta-button {
    padding: 16px 32px;
    background: linear-gradient(135deg, #B388EB, #D9FF00);
    border-radius: 50px;
    font-size: 18px;
    font-weight: 700;
    color: #1A1A1A;
}

.cta-button:hover {
    transform: scale(1.05);
    box-shadow: 0 10px 40px rgba(217, 255, 0, 0.3);
}
```

#### 次要按钮

```css
.btn-hover {
    transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}

.btn-hover:hover {
    transform: scale(1.02);
    filter: brightness(1.1);
}
```

### 卡片

```css
.card-hover {
    transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}

.card-hover:hover {
    transform: scale(1.02);
}
```

### 徽章

#### 2026 米兰徽章

```css
.milano-badge {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 8px 16px;
    background: linear-gradient(135deg, #B388EB, #D9FF00);
    border-radius: 50px;
    font-weight: 700;
    color: #1A1A1A;
}
```

### 导航栏

```css
.nav-sticky {
    backdrop-filter: blur(20px);
    background: rgba(26, 26, 26, 0.8);
}
```

---

## ✨ 动效规范

### 动画曲线

| 曲线 | 用途 |
|------|------|
| `ease-out` | 淡出动画 |
| `cubic-bezier(0.4, 0, 0.2, 1)` | 标准过渡 |

### 动画时长

| 动画类型 | 时长 |
|---------|------|
| 淡入淡出 | 0.5s |
| 悬停效果 | 0.3s |
| 渐变动画 | 15s |
| 浮动动画 | 3s |

### 关键动画

#### 淡入上移动画

```css
.fade-in-up {
    opacity: 0;
    transform: translateY(30px);
    transition: opacity 0.5s ease-out, transform 0.5s ease-out;
}

.fade-in-up.visible {
    opacity: 1;
    transform: translateY(0);
}
```

#### 浮动动画

```css
@keyframes float {
    0%, 100% { transform: translateY(0px); }
    50% { transform: translateY(-10px); }
}

.float-animation {
    animation: float 3s ease-in-out infinite;
}
```

#### 渐变动画

```css
@keyframes gradientShift {
    0% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
}

.bg-gradient-poster {
    background-size: 400% 400%;
    animation: gradientShift 15s cubic-bezier(0.4, 0, 0.2, 1) infinite;
}
```

---

## 📱 响应式设计

### 断点

| 断点 | 宽度 | 设备类型 |
|------|------|---------|
| 默认 | < 768px | 移动端 |
| `md` | ≥ 768px | 平板 |
| `lg` | ≥ 1024px | 桌面端 |

### 响应式展示模式

| 设备 | 作品展示方式 |
|------|-------------|
| 移动端 | 水平滑动容器 |
| 平板 | 2列网格 |
| 桌面端 | 4列网格 |

### 移动端优化

- 禁用背景渐变动画
- 简化动效
- 优化触摸区域
- 汉堡菜单导航

---

## ♿ 可访问性规范 (WCAG 2.1 AA)

### 焦点样式

```css
.focus-visible-ring:focus-visible {
    outline: 2px solid #D9FF00;
    outline-offset: 2px;
}
```

### ARIA 标签

| 元素 | 必需属性 |
|------|---------|
| 导航 | `role="navigation"`, `aria-label` |
| 菜单 | `role="menu"`, `aria-expanded` |
| 菜单项 | `role="menuitem"` |
| 模态框 | `role="dialog"`, `aria-modal="true"`, `aria-labelledby` |
| 列表 | `role="list"`, `aria-label` |
| 列表项 | `role="listitem"`, `aria-label` |

### 装饰性元素

```html
<svg aria-hidden="true">...</svg>
```

---

## 📂 CMS 数据结构

### 作品数据

```javascript
const worksData = {
    planet: [
        { 
            title: { en: 'Title', zh: '标题' }, 
            designer: { en: 'Designer', zh: '设计师' } 
        }
    ],
    people: [...],
    partner: [...]
};
```

### 网站内容数据

```javascript
const cmsData = {
    hero: {
        title: { en: '', zh: '' },
        subtitle: { en: '', zh: '' },
        date: { en: '', zh: '' },
        location: { en: '', zh: '' },
        venue: { en: '', zh: '' }
    },
    about: {
        background: { en: '', zh: '' },
        niceMeaning: { en: '', zh: '' },
        togetherMeaning: { en: '', zh: '' }
    }
};
```

---

## 🧪 浏览器兼容性

### 支持的浏览器

| 浏览器 | 最低版本 |
|--------|---------|
| Chrome | 90+ |
| Firefox | 88+ |
| Safari | 14+ |
| Edge | 90+ |

### CSS 特性支持

- ✅ CSS Grid
- ✅ Flexbox
- ✅ CSS Custom Properties (Variables)
- ✅ backdrop-filter
- ✅ CSS animations
- ✅ Intersection Observer API

---

## 📦 交付物清单

### 设计文件
- [ ] Figma 设计源文件
- [ ] Sketch 设计源文件
- [ ] 设计规范文档 (本文档)

### 前端代码
- [x] `index.html` - 主页面
- [x] `DESIGN_GUIDELINES.md` - 设计规范文档

### 测试报告
- [ ] 跨设备测试报告
- [ ] 可访问性测试报告
- [ ] 性能测试报告

### 配置文档
- [ ] CMS 配置指南
- [ ] 部署指南

---

## 🔗 参考链接

- [Tailwind CSS 文档](https://tailwindcss.com/docs)
- [WCAG 2.1 指南](https://www.w3.org/TR/WCAG21/)
- [Inter 字体](https://fonts.google.com/specimen/Inter)

---

## 📝 更新日志

### v1.0 (2026-04-05)
- ✅ 初始版本发布
- ✅ 完整的色彩系统
- ✅ 完整的字体层级
- ✅ 响应式设计规范
- ✅ 可访问性规范
- ✅ CMS 数据结构
