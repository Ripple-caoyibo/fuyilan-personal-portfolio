# 任务四技术设计

## 结构

- `site/index.html`：公开主页和管理后台的语义化 DOM。
- `site/style.css`：响应式布局、主页视觉样式与后台表单样式。
- `site/app.js`：初始化数据、渲染、编辑、文件读取、下载与 LocalStorage 持久化。
- `site/data/profile.json`：可读的默认资料种子数据。
- `site/assets/avatar.svg`：默认头像插画。

## 数据流

首次载入以 `profile.json` 为种子；存在有效 `profile.v1` 本地数据时优先使用。管理页更新对象后序列化到 LocalStorage；公开页渲染同一对象。头像和简历通过 FileReader 转为 Data URL 保存在同一对象中，简历下载使用 Blob URL。

## 发布

仓库根目录为项目目录；Cloudflare Pages 选择 GitHub 仓库、生产分支 `master`，构建命令留空，输出目录填写 `site`。GitHub Pages 工作流同样发布 `site` 文件夹。

## 风险

浏览器存储有容量上限，文件上传需限制大小并展示错误；本地浏览器数据不跨设备、不向静态部署同步；后台不含身份验证。
