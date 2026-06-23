# Clone Website

这是一个用于“反向分析并复刻网站”的 skill。

它会把目标 URL 拆成可审计的研究材料和组件规格，再基于这些规格实现 Next.js / App Router 页面。

## 安装

使用 npx 从 GitHub 安装当前仓库中的 skill：

```bash
npx skills@latest add grove94/grove-better-skills clone-website
```

从仓库根目录执行：

```bash
./install.sh clone-website
```

覆盖已安装版本：

```bash
npx skills@latest add grove94/grove-better-skills clone-website --force
```

或在本地仓库中执行：

```bash
./install.sh clone-website --force
```

## 适用场景

适合在以下场景使用：

- “帮我 clone 这个网站”
- “按这个页面做一个 pixel-perfect 版本”
- “把这个官网复刻成 Next.js”
- “分析这个 URL 的设计、交互和资源，然后重建”
- “一次处理多个 URL，并把研究材料分目录保存”

## 推荐输入

```text
Use $clone-website to rebuild https://example.com as a pixel-perfect Next.js clone.
```

也可以给多个 URL：

```text
Use $clone-website to clone https://example.com https://example.org
```

## 它会做什么

- 用浏览器工具打开目标页面并截图
- 抽取字体、颜色、图片、视频、SVG、favicon 和真实文案
- 扫描滚动、点击、hover、响应式断点等交互行为
- 为每个 section / component 写 `docs/research/components/*.spec.md`
- 基于规格拆分任务，尽量并行构建
- 合并组件，跑构建，并做视觉 QA

## 前置条件

推荐在已经准备好的 Next.js / App Router / Tailwind / shadcn 项目里使用。这个 skill 依赖浏览器自动化工具来观察网页，如果当前环境没有浏览器工具，agent 应该先停下来说明需要接入浏览器能力。

## 输出材料

常见输出包括：

- `docs/research/BEHAVIORS.md`
- `docs/research/PAGE_TOPOLOGY.md`
- `docs/research/components/*.spec.md`
- `docs/design-references/*.png`
- `public/` 下下载的图片、视频和 SEO 资源
- `src/components/*`
- `src/app/page.tsx`

## 质量标准

完成前至少要验证：

- `npm run build` 通过
- 桌面和移动端截图与原站逐段对比
- 交互状态已检查，包括 scroll、click、hover 和响应式布局
- 已说明剩余差异或已知限制
