# 付逸澜个人展示网站

纯前端个人简介网站，包含个人信息、技能、项目和简历下载，并提供 `?admin` 本地管理页。

## 本地运行

在 `site` 的上一级目录启动静态服务器，然后打开 `/site/`。直接双击 HTML 也可看到页面，但使用静态服务器才能加载 `data/profile.json`。

## 后台与发布

打开 `/site/?admin` 编辑并保存。头像支持图片，简历支持 PDF/DOC/DOCX；数据保存在当前浏览器 LocalStorage。Cloudflare Pages 导入仓库后，构建命令留空，输出目录填写 `site`。
