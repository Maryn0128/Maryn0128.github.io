# 鳗鱼不想动 · 个人主页

我的个人主页源码，纯手写 HTML + CSS，没有用任何框架、没有任何外部依赖（字体、图标、图片全部本地或内联），断网也能正常显示。

**线上地址：<https://maryn0128.github.io/>**

## 文件说明

| 文件 | 作用 |
| :--- | :--- |
| `index.html` | 主页。样式和交互全部写在同一个文件里，方便整份拷走 |
| `play.html` | 主页里「在线试玩」指向的猜数字小游戏 |
| `.nojekyll` | 告诉 GitHub Pages 不要用 Jekyll 处理这个仓库，加快构建、避免下划线开头的文件被忽略 |
| `README.md` | 本文件，只在仓库页面显示，不影响网站 |

## 怎么改内容

全部在 `index.html` 里，按注释找就行：

- **名字、简介**：搜 `鳗鱼`，主要出现在 `<h1>`、关于我、页脚三处
- **配色**：最上面的 `:root` 里集中了所有颜色变量，改 `--rose` 就能换掉主色
- **作品卡片**：`<article class="work">` 整块，链接在 `.work-links` 里
- **GitHub 地址**：搜 `Maryn0128`
- **页脚年份**：由 JavaScript 自动取当前年，不用手动改

改完本地双击 `index.html` 就能看效果，确认没问题再推送。

## 更新上线

```bash
git add -A
git commit -m "改了什么"
git push
```

推送后 1~2 分钟，GitHub Pages 会自动重新构建，刷新 <https://maryn0128.github.io/> 即可看到。

## 技术细节

- 响应式：手机、平板、桌面都有对应断点
- 无障碍：语义化标签、键盘焦点可见、`prefers-reduced-motion` 时关闭所有动画
- 首屏动画用 CSS `@keyframes`，滚动淡入用 `IntersectionObserver`，只在元素第一次进入视口时触发
- 卡片里的游戏缩略图是用 CSS 画出来的，不是图片
