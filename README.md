# YI STUDIO — Personal Portfolio

一个现代、响应式的个人视觉设计师作品集。项目以 React、TypeScript 与 Vite 构建，作品内容采用统一的数据结构，方便持续添加和维护。

## 网站架构

- **首页**：沉浸式产品视觉首屏、精选作品、设计方法介绍。
- **About**：个人定位、设计理念、工作方式与能力标签。
- **Works**：支持分类筛选的响应式作品网格。
- **Project Detail**：项目封面、项目简介、作品画廊以及前后项目导航。
- **Skills**：专业工具与能力清单。
- **Contact**：联系方式、社交链接和联系表单。

## 目录结构

```text
src/
├── data/
│   └── projects.ts     # 统一的作品数据与图片配置
├── App.tsx             # 页面、可复用展示组件与路由状态
├── main.tsx            # React 应用入口
└── styles.css          # 响应式视觉系统与动画
```

## 运行项目

需要 Node.js 20 或更高版本。

```bash
npm install
npm run dev
```

打开终端显示的本地地址（通常是 `http://localhost:5173`）。生成生产构建：

```bash
npm run build
npm run preview
```

## 替换个人信息

- 在 `src/App.tsx` 中更新首页介绍、About 文案、联系邮箱及社交平台链接。
- 在 `Header` 和 `Footer` 组件中将 `YI·STUDIO` 替换为你的个人品牌名称。
- `Contact` 组件目前提供浏览器端提交反馈；对接 Formspree、Resend 或自己的 API 后即可实际发送邮件。

## 替换作品图片

所有示例图片地址集中在 `src/data/projects.ts`。每个作品都使用 `cover` 作为封面，使用 `gallery` 作为详情页画廊。

要使用本地图片，请将图片放入 `public/projects/project-01/` 等目录，并将 URL 替换为：

```ts
cover: '/projects/project-01/cover.jpg',
gallery: ['/projects/project-01/cover.jpg', '/projects/project-01/detail-01.jpg']
```

建议导出 WebP/AVIF 格式，并压缩到适合页面展示的尺寸，以获得更快加载速度。

## 添加新的作品

在 `src/data/projects.ts` 的 `projects` 数组中添加一个对象：

```ts
{
  slug: 'project-name',
  title: 'PROJECT NAME',
  category: 'PRODUCT VISUAL',
  year: '2026',
  description: 'A concise project description.',
  cover: '/projects/project-name/cover.jpg',
  gallery: ['/projects/project-name/cover.jpg', '/projects/project-name/detail-01.jpg'],
  concept: 'The creative direction and design rationale.'
}
```

`category` 可使用 `PRODUCT VISUAL`、`AI CREATIVE`、`BRANDING`、`PACKAGING` 或 `E-COMMERCE`，新作品将自动出现在作品页及详情前后导航中。
