# TIANGONG · GitHub Pages 部署包

这是已经预渲染好的纯静态版本，不需要 Node、npm、构建命令或服务器。

## 最省事的部署方法

1. 在 GitHub 新建一个 **Public** 仓库，例如 `tiangong`。
2. 解压本 ZIP，把 `TIANGONG_GITHUB_PAGES` 文件夹内的全部内容上传到仓库根目录。
   - 必须让 `index.html` 直接出现在仓库首页，不能再套一层文件夹。
   - `.github` 和 `.nojekyll` 也要一并上传。
3. 打开仓库的 **Settings → Pages**。
4. 在 **Build and deployment → Source** 选择 **GitHub Actions**。
5. 打开仓库的 **Actions** 页面，等待 `Deploy TIANGONG to GitHub Pages` 变成绿色。
6. 成品地址通常是：`https://你的用户名.github.io/仓库名/`

如果仓库名就是 `你的用户名.github.io`，地址则是：`https://你的用户名.github.io/`

## 重要说明

- 本包已经处理 GitHub 项目仓库的子路径，不要求仓库必须命名为 `用户名.github.io`。
- GitHub Pages 是静态托管；本项目没有 API、数据库或可被当作代理的后端接口。
- 首次发布通常需要几分钟。后续替换文件并提交后，Actions 会自动重新部署。
- 若 Actions 提示 Pages 未启用，请回到 **Settings → Pages**，确认 Source 为 **GitHub Actions**。
- 若 GitHub 网页端没有上传隐藏目录 `.github`，可在仓库里手动创建 `.github/workflows/deploy-pages.yml`，内容已包含在本包中。

## 文件结构

- `index.html`：静态首页
- `_next/`：前端脚本与样式
- `models/`：3D 模型
- `textures/`：材质与天体纹理
- `stills/`：静帧降级内容
- `.github/workflows/deploy-pages.yml`：自动部署流程
- `.nojekyll`：保证 GitHub Pages 正常发布 `_next` 目录

项目为个人概念作品，与任何官方机构无隶属、合作或授权关系。
