# 许嵩歌词意象百科

> Vae 歌词创作研究图鉴 —— 一个静态网页应用，整理许嵩歌词中的意象、用典、自创词、谐音空耳、术语、时间、颜色、人物动物、季节节气、地名等分类。

## 功能特性

- **8 大分类导航**：意象总览、地名、人物动物、季节节气、颜色、时间、典故用典、趣味彩蛋（含自创词、谐音空耳、术语、作词相关）
- **实时搜索**：支持歌曲名、歌词、意象关键词检索，含关键词高亮与同义词匹配
- **意象标签云**：按条目数量差异化显示标签大小
- **卡片网格 + 加载更多**：3 列响应式布局，分页加载意象条目
- **详情弹窗**：点击卡片查看完整意象解读与歌词出处
- **彩色关键词高亮**：颜色分类下的关键词按实际色彩渲染
- **访问统计**：基于不蒜子（busuanzi）的 PV / UV 统计

## 数据概览

| 指标 | 数值 |
|---|---|
| 覆盖歌曲 | 165 首 |
| 意象条目 | 819 条 |
| 典故用典 | 60 条 |
| 分类 | 10 类 |

## 技术栈

- **框架**：React 19 + TypeScript
- **构建工具**：Vite 8
- **路由**：React Router v7（HashRouter，兼容任意静态托管）
- **样式**：Tailwind CSS v4 + shadcn/ui（new-york 风格）
- **动画**：framer-motion + gsap + @formkit/auto-animate
- **图表**：echarts + recharts
- **图标**：lucide-react
- **状态管理**：React useState / useMemo（无全局状态库）

## 数据来源

歌词数据来源于 Excel 统计表（Vae 歌词统计），已内联为 `src/data/lyricsdata.ts` 纯前端静态数据，无需后端服务。

## 项目结构

```
src/
├── components/
│   ├── Layout.tsx          # 布局容器
│   ├── Header.tsx          # 顶部固定导航栏
│   └── Footer.tsx          # 底部页脚（含访问统计）
├── pages/HomePage/
│   ├── HomePage.tsx        # 首页主组件
│   └── sections/
│       ├── HeroSection.tsx       # Hero 大标题
│       ├── StatsSection.tsx      # 统计卡片
│       ├── SearchSection.tsx     # 搜索框
│       ├── TagCloudSection.tsx   # 意象标签云
│       ├── EntriesSection.tsx    # 意象卡片网格 + 加载更多
│       ├── LyricCard.tsx         # 单张意象卡片
│       ├── LyricDetailDialog.tsx # 详情弹窗
│       └── AboutSection.tsx      # 关于板块（含友情链接）
├── data/
│   └── lyricsdata.ts       # 歌词意象数据（819 条）
└── app.tsx                 # 路由配置
```

## 本地运行

```bash
# 安装依赖
npm install

# 启动开发服务器
npm run dev
```

## 构建部署

```bash
# 构建生产版本
npm run build
```

构建产物输出至 `dist/` 目录，为纯静态文件。由于使用 HashRouter，可部署到任意静态托管服务（GitHub Pages、Vercel、Netlify、Nginx 等），无需配置 SPA fallback。

## 第三方服务

- **不蒜子统计**（busuanzi）：Footer 中注入 `busuanzi.pure.mini.js`，展示总访问量（PV）和访客数（UV）

## 版本信息

- 页面版本：2026.09.06-rev70
- 数据版本：2026.08.24-rev51

## 署名

整理：B站UP主 [@我贼6贼6贼6](https://space.bilibili.com/12550061)
交流：Q群 730818497

## 版权声明

本项目仅供歌词研究、学习交流与个人收藏使用，非商业用途。

- 歌词及相关作品的著作权归许嵩本人及相应版权方（如海蝶音乐/太合音乐等）所有
- 本项目不提供歌词下载、不用于任何盈利目的
- 如版权方认为本项目侵犯权益，请联系仓库所有者，将第一时间处理
