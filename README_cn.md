# Jiankuo Zhao 学术主页

这是为 Jiankuo Zhao 搭建的 GitHub Pages 学术主页，基于 PRISM 个人主页模板改造。

## 主页 URL

- 仓库名：`JiankuoZhao.github.io`
- 主页地址：`https://JiankuoZhao.github.io`

## 本地运行

```bash
npm install
npm run dev
```

然后打开 `http://localhost:3000`。

## 构建

```bash
npm run build
```

静态站点会导出到 `out/` 目录。

## 主要内容文件

- `content/config.toml`：姓名、身份、机构、社交链接、导航
- `content/bio.md`：主页简介
- `content/education.md`：教育经历
- `content/publications.bib`：BibTeX 格式论文列表
- `public/avatar.png`：512 x 512 主页头像
- `public/papers/brief.png`：STAvatar 论文卡片图片
- `PUBLISH_STEPS.md`：GitHub Pages 发布步骤

CV 页面目前保持关闭，因为暂未提供 CV PDF。
