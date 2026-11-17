# CordiAct website

CordiAct 品牌与产品官网。纯静态 HTML / CSS，无前端依赖、第三方字体、分析脚本或构建步骤。

- 网站：https://cordiact.dev
- 产品：https://github.com/wuyhong715/CordiAct
- 发布目录：`public/`

## 本地预览

```sh
python3 -m http.server 8000 --directory public
```

## 部署

使用 Cloudflare Pages Direct Upload，项目名称 `cordiact-site`，生产分支 `main`：

```sh
CLOUDFLARE_ACCOUNT_ID=<account-id> CLOUDFLARE_API_TOKEN=<pages-only-token> \
  npx wrangler@4 pages deploy public --project-name=cordiact-site --branch=main
```

不要将令牌提交到源码。自动发布使用 GitHub Actions；仅将本账号 `Cloudflare Pages:Edit` 的专用令牌存入仓库 Actions Secret `CLOUDFLARE_API_TOKEN`，账号 ID 放到 Actions Variable `CLOUDFLARE_ACCOUNT_ID`。不得使用部署时临时提供的超广权限令牌作为长期部署凭证。

绑定自定义域需同时完成 Pages 域名关联与 DNS CNAME；HTTPS 由 Cloudflare 自动签发与续期。`www` 使用独立的 Pages 跳转项目，301 到根域，保留路径与查询参数。

## 内容边界

概念图不是应用截图；目前仅链接仓库、README 和 Issues，不提供未经确认的稳定版下载或完整可用性承诺。本站未声明产品许可；具体以产品仓库为准。
