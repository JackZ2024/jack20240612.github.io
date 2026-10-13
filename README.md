# 网站文件与发布方法

这是本地静态网站草稿，尚未部署，没有在线网址。无需 Node、数据库或构建步骤。只发布本目录中的网页文件；不要上传桌面软件目录、OAuth JSON、token.dpapi 或个人上传记录。

## 文件

- `index.html`：软件介绍首页。
- `privacy.html`：隐私政策（按当前基础版代码编写）。
- `styles.css`：共用样式，支持手机和桌面。
- `.nojekyll`：GitHub Pages 使用的空文件。

双击 `index.html` 可以在浏览器预览；不要将 `file://` 本地地址填入 Google 控制台。

## 发布前需要补齐的信息

搜索两份 HTML 中所有 `【待填写：…】` 并替换：

1. 开发者名称：填写真实的个人、团队或公司名称，和 Google OAuth 应用信息保持一致。
2. 联系邮箱：已填写 `jack20240612@outlook.com`，首页和隐私政策均可点击发送邮件。
3. 生效日期：填写确认并正式发布政策的日期。
4. 托管服务商名称与隐私政策网址：例如部署到 GitHub Pages 后填写 GitHub，以及 https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement 。不要在选择托管平台前承诺实际服务商。

完成核对后，删除两份 HTML 中的 `<div class="draft">…</div>` 和 `<meta name="robots" content="noindex">`。保留页脚的第三方政策链接。网站里的功能说明应始终与发布的软件版本一致；这些文件不表示 Google 已审核通过。

如果新增服务器、统计、崩溃上报、多账号、更多权限或数据存储，先修改相应政策内容。当前软件尚未添加政策阅读与同意入口；正式分发前需要让用户能在软件内方便地查看政策，并完成必要的同意流程。仅上传这两个网页不代表整个软件已满足所有发布要求。

## 上传到 GitHub Pages

1. 登录 GitHub，创建公开仓库 `你的用户名.github.io`（仓库名中的用户名须与账号一致）。
2. 将 `index.html`、`privacy.html`、`styles.css` 和 `.nojekyll` 上传到仓库根目录，不要再包一层 `website` 文件夹。
3. 进入仓库 Settings → Pages，选择 Deploy from a branch → `main` → `/ (root)`，保存。
4. 等待 GitHub Pages 部署成功，实际网站地址会显示在 Pages 设置页。
5. 使用未登录或无痕窗口打开首页和隐私政策，确认都可公开访问、内容完整且无待填写项。

完成后在 Google OAuth 品牌信息中填写实际地址：

| 字段 | 格式示例（必须替换用户名） |
| --- | --- |
| 首页网址 | `https://你的用户名.github.io/` |
| 隐私政策网址 | `https://你的用户名.github.io/privacy.html` |
| 已获授权的网域 | `你的用户名.github.io` |

如果网站部署在项目子路径，主页和隐私政策网址都应包含该路径；网域字段只填写网域。正式验证时，按 Google Search Console 的提示验证网站所有权。若需要 HTML 验证文件，把它放在指定位置；若使用 HTML meta 标签验证，把 Google 提供的完整标签加入首页 `<head>`，重新部署。不要公开账号凭据。

## 参考

- Google OAuth 品牌验证：https://developers.google.com/identity/protocols/oauth2/production-readiness/brand-verification
- Google API 用户数据政策：https://developers.google.com/terms/api-services-user-data-policy
- YouTube 开发者政策：https://developers.google.com/youtube/terms/developer-policies
- GitHub Pages：https://docs.github.com/en/pages/getting-started-with-github-pages/what-is-github-pages
- 网站所有权验证：https://support.google.com/webmasters/answer/9008080
