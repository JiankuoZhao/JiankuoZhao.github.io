# 发布到 GitHub Pages 的操作步骤

## 1. 准备 GitHub 仓库

1. 登录 GitHub。
2. 点击右上角 `+`，选择 `New repository`。
3. 仓库名填写：`JiankuoZhao.github.io`。
4. Visibility 可选 `Public`。
5. 不要勾选自动生成 README、`.gitignore` 或 License，因为本地项目已经包含这些文件。
6. 创建仓库。

## 2. 推送本地项目

在本项目目录打开终端：

```bash
cd C:\Users\86136\Documents\Codex\2026-06-10\c-users-86136-downloads-clayzhang999-github\outputs\JiankuoZhao.github.io
git init
git branch -M main
git add .
git commit -m "Initialize academic homepage"
git remote add origin https://github.com/JiankuoZhao/JiankuoZhao.github.io.git
git push -u origin main
```

如果 GitHub 提示需要登录，按终端提示完成认证。

## 3. 启用 GitHub Pages

1. 打开仓库：`https://github.com/JiankuoZhao/JiankuoZhao.github.io`。
2. 进入 `Settings`。
3. 左侧选择 `Pages`。
4. 在 `Build and deployment` 中，`Source` 选择 `GitHub Actions`。
5. 回到仓库的 `Actions` 页面，等待 `Deploy Next.js site to Pages` 工作流完成。

## 4. 访问主页

部署完成后访问：

```text
https://JiankuoZhao.github.io
```

首次部署可能需要等待 1-5 分钟。

## 5. 后续更新

修改内容后，在项目目录运行：

```bash
git add .
git commit -m "Update homepage content"
git push
```

GitHub Actions 会自动重新构建并发布主页。

## 6. 本地预览

本地开发预览：

```bash
npm install
npm run dev
```

构建静态站点：

```bash
npm run build
```

本项目使用 Node.js 22，GitHub Actions 已配置为 Node 22。
