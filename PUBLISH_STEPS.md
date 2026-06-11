# 发布到 GitHub Pages 的操作步骤

## 1. 创建 GitHub 仓库

1. 登录 GitHub。
2. 点击右上角 `+`，选择 `New repository`。
3. 仓库名填写：`JiankuoZhao.github.io`。
4. Visibility 建议选择 `Public`。
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

推荐先在 GitHub 网页端手动启用一次：

1. 打开仓库：`https://github.com/JiankuoZhao/JiankuoZhao.github.io`。
2. 进入 `Settings`。
3. 左侧选择 `Pages`。
4. 在 `Build and deployment` 中，`Source` 选择 `GitHub Actions`。
5. 保存后，进入 `Actions` 页面，重新运行或等待 `Deploy Next.js site to Pages`。

当前 workflow 也已经配置：

```yaml
with:
  enablement: true
  static_site_generator: next
```

这个配置允许 `actions/configure-pages` 在 Pages 尚未启用时自动启用 Pages。

## 4. 如果出现 Get Pages site failed

如果 Actions 报错：

```text
Get Pages site failed. Please verify that the repository has Pages enabled and configured to build using GitHub Actions
```

处理方式：

1. 确认 `.github/workflows/nextjs.yml` 中 `actions/configure-pages@v5` 的 `with` 下有 `enablement: true`。
2. 到仓库 `Settings -> Pages`，确认 `Source` 是 `GitHub Actions`。
3. 到 `Actions` 页面重新运行失败的 workflow。
4. 如果仓库刚创建，等待 1-2 分钟后再重新运行。

## 5. 访问主页

部署完成后访问：

```text
https://JiankuoZhao.github.io
```

首次部署可能需要等待 1-5 分钟。

## 6. 后续更新

修改内容后，在项目目录运行：

```bash
git add .
git commit -m "Update homepage content"
git push
```

GitHub Actions 会自动重新构建并发布主页。
