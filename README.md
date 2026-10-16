# Portfolio Motion Reference

David 旧版个人网站的完整实现，用作页面动效、滚动交互与中英文排版的参考。基于 Next.js、React、GSAP、ScrollMagic 和 smooth-scrollbar。

## 看点

- **首屏入场**：标题字词从位移、旋转和缩放状态汇聚，彩色圆点循环上浮。
- **滚动叙事**：About 逐字显色、章节翻字、标题随滚动速度轻微倾斜。
- **层次与反馈**：产品图片视差、卡片依次显现、标题与轨道的指针反馈。
- **双语排版**：自托管 Nunito 与 Noto Sans SC，支持中文和英文切换。
- **响应式体验**：桌面虚拟滚动，移动端原生滚动，适配减少动态效果偏好。

## 本地预览

需要 Node.js **22.13+** 和 npm。

```bash
git clone https://github.com/CrystalDavid/Portfolio-Motion-Reference.git
cd Portfolio-Motion-Reference
npm ci
npm run dev
```

打开 [http://localhost:3000](http://localhost:3000)。生产静态文件可通过以下命令生成到 `apps/web/out/`：

```bash
npm run build
```

## 动效从哪里看

| 效果 | 实现入口 | 说明 |
| --- | --- | --- |
| 首屏文字与章节入场 | [motion-controller.tsx](apps/web/app/motion-controller.tsx) | [Hero 入场](docs/animation/hero-entrance.md) |
| 虚拟滚动与锚点返回 | [smooth-scroll.tsx](apps/web/app/smooth-scroll.tsx) | [滚动机制](docs/animation/scrolling.md) |
| 逐字显色、wave、视差与指针反馈 | [wickret-runtime.tsx](apps/web/app/wickret-runtime.tsx) | [章节效果](docs/animation/about-and-section-reveals.md) |
| 漂浮圆点 | [floating-decor.tsx](apps/web/app/floating-decor.tsx) | [完整动效清单](docs/animation/inventory.md) |
| 字体与页面样式 | [globals.css](apps/web/app/globals.css) | [排版](docs/ui/typography.md) |
| 滚动和动效参数 | [site-contract](packages/site-contract/) | [运行时架构](docs/architecture/runtime.md) |

## 修改内容

主页位于 [apps/web/app/page.tsx](apps/web/app/page.tsx)，文章内容位于 [articles/data.ts](apps/web/app/articles/data.ts)，图片和字体位于 [public](apps/web/public/)。布局与断点见 [响应式说明](docs/ui/responsive.md)。

## 检查

```bash
npm run lint
npm run build
npm run test:rendered
```
