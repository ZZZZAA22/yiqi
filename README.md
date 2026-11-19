# Yiqi Network 英文公司官网

为 Guangzhou Yiqi Network Technology Co., Ltd. 制作的英文静态企业主页，面向综合跨境电商业务。

已包含公司全名、完整地址、`yiqinetwork.com` 和 `hello@yiqinetwork.com`。页面包含公司介绍、业务方向、邮件联系入口和公司信息，适配手机与桌面。

## 本地查看

双击 `index.html` 即可查看。所有字体、插画、样式和脚本都在本文件夹内，无须安装 Node.js 或运行构建命令。

邮件链接使用 `mailto:`，点击后由访客的邮件应用处理。

## 上传 GitHub 并发布

1. 新建 GitHub 仓库，例如 `yiqinetwork`。使用 GitHub Free 时可选 Public 仓库。
2. 解压交付的 ZIP，将里面的全部文件和 `assets` 文件夹上传到仓库根目录并提交。上传后，仓库首页应能直接看到 `index.html`，请勿在外面多套一层 `yiqinetwork` 文件夹，也不要只上传 ZIP。
3. 打开仓库 **Settings → Pages**。
4. 在 **Build and deployment → Source** 选择 **Deploy from a branch**。
5. 选择上传文件所在的分支（通常是 `main`）和 **/(root)**，点击 **Save**。
6. 等待 GitHub 部署完成，在 Pages 设置中查看网站地址和部署状态。

文件中的相对路径也适用于 `https://你的用户名.github.io/仓库名/`。当前交付包已包含自定义域名文件 `CNAME`；如果先只想用 GitHub 默认地址预览，可暂时删除仓库中的 `CNAME`，并在 Pages 设置里清空 Custom domain。正式绑定时再填写 `yiqinetwork.com`。

操作依据：[GitHub 官方发布说明](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)。

## 绑定 yiqinetwork.com

1. 先在仓库 **Settings → Pages → Custom domain** 填入 `yiqinetwork.com` 并保存。交付包里的 `CNAME` 内容也已设为此域名；仍需在 Pages 设置中确认绑定。
2. 到域名服务商的 DNS 设置中，为根域名添加以下 4 条 A 记录（记录名称通常填 `@`）。如果已有冲突的同名网站解析，先核对并调整。

| 类型 | 名称 | 值 |
| --- | --- | --- |
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |

3. 如需同时支持 `www.yiqinetwork.com`，添加 `www` 的 CNAME 记录，值填 `你的GitHub用户名.github.io`，不加 `https://`，也不加仓库名。这里 DNS 的 CNAME 记录与仓库里的 `CNAME` 文件是两个不同的设置。
4. DNS 校验和证书准备完成后，在 Pages 设置中勾选 **Enforce HTTPS**。

DNS 解析和 HTTPS 选项可能需要最多 24 小时生效。上述记录值已根据 2026-11-19 的 [GitHub 官方域名说明](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site) 核对，后续以官方文档为准。

本次交付的是网站文件；GitHub 发布与域名 DNS 配置由你在自己的账号中完成。

## 文件说明

| 文件 | 用途 |
| --- | --- |
| `index.html` | 英文文案、公司资料、SEO 信息 |
| `styles.css` | 颜色、字体、布局和手机端适配 |
| `script.js` | 手机导航和页脚年份 |
| `assets/commerce-illustration.svg` | 原创可编辑电商插画 |
| `assets/favicon.svg` | 网站图标 |
| `assets/Manrope.ttf` | 本地字体 |
| `assets/Manrope-OFL.txt` | 字体授权 |
| `CNAME` | GitHub Pages 自定义域名文件 |
| `.nojekyll` | 直接提供静态文件 |
| `robots.txt`、`sitemap.xml` | 搜索引擎抓取信息 |

## 修改内容

- 修改介绍或联系方式：编辑 `index.html`。邮箱和公司信息在页面正文与顶部 JSON-LD 资料中均有使用，请同步更新。
- 修改配色：编辑 `styles.css` 顶部的 `:root` 变量。
- 更换 Logo：调整 `index.html` 中的品牌图形和 `assets/favicon.svg`。
- 更换域名：同步修改 `CNAME`、`index.html` 中的网址及 SEO/JSON-LD 信息、`robots.txt`、`sitemap.xml`。

Manrope 字体来自 [google/fonts 官方仓库](https://github.com/google/fonts/tree/main/ofl/manrope)，使用 SIL Open Font License，授权文件随包附带。插画为本项目原创 SVG。
