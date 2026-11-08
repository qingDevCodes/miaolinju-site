# 喵邻居介绍页

猫咪公寓题材微信小游戏的独立宣传站，只包含公开介绍、真实截图和正式码，无游戏源码、游戏包、统计脚本或运行依赖。

- 网站：https://qingdevcodes.github.io/miaolinju-site/
- 公开仓：https://github.com/qingDevCodes/miaolinju-site
- 微信小游戏 AppID：`wx99f30143ac9176d0`；线上版本：`2.0.0`。
- 状态核对日期：2026-11-08。微信认证已通过；名称搜索是否恢复请以微信内实测为准。可尝试正式码，能否进入以微信实际提示为准。

## 本地复现

需要 Python 3，无需安装依赖或构建：

```bash
git clone https://github.com/qingDevCodes/miaolinju-site.git
cd miaolinju-site
python3 -m http.server 8080
```

打开 http://localhost:8080/，检查手机和桌面布局、正文、码图、原图链接和下载入口。核心介绍在初始 HTML 中，不依赖 JavaScript。

## 材料来源与边界

正式码 `assets/qrcode.png` 来源于项目既有 `docs/launch/mp-status-2026-11-06/qrcode.png`：2026-11-06 从当前账号后台取得的正式码，430×430 PNG；直接复制，未裁剪、重绘或修改码点。

三张截图来自项目既有 `docs/launch/assets/`，文件名保持一致：

| 文件 | 内容 | 可确认范围 |
| --- | --- | --- |
| screenshot-game.png | 公寓对局与候选猫 | 真实本地游戏截图 |
| screenshot-result.png | 年度结算 | 真实本地游戏截图 |
| screenshot-codex.png | 猫猫图鉴 | 真实本地游戏截图 |

截图真实性依据既有上架材料记录，并逐张目检。**本地版本画面，未核实与线上 2.0.0 一致，实际以微信内为准。** 不将其标作线上版本实机验收。简介复用 2026-11-06 方案中的后台简介，不额外承诺未核实功能。

图标 `assets/icon-512.png` 原样复制自游戏仓公开宣传素材 `docs/launch/assets/icon-512.png`。`assets/apple-touch-icon.png` 与根目录 `favicon.ico` 由该图标等比缩放生成。

`assets/og-cover-1200x630.png` 是 1200×630 的站外分享封面，由上述图标和真实本地截图 `screenshot-game.png` 排版合成，没有生成、重绘或补造游戏内容。它同时作为首页英雄区主视觉；其中截图仍属于本地版本材料，不是线上 2.0.0 专属实机截图。

微信认证已于 2026-11-08 通过，但认证成功不等于名称搜索限制、分享能力或最终备案状态已经自动恢复。正式码存在不保证所有账号可进入。本人仍需用管理员与非管理员微信扫码检查，并验证大陆手机访问；本网页可访问不代表微信扫码成功或名称搜索恢复。

## Pages 发布与检查

GitHub Pages 使用 `main` 分支根目录（`/`），`.nojekyll` 保持原生静态文件发布。修改后仅在此宣传仓提交、推送，无需操作游戏仓。

```bash
git add index.html styles.css sitemap.xml .nojekyll README.md assets
git commit -m "Update public introduction"
git push origin main
gh api repos/qingDevCodes/miaolinju-site/pages
gh api repos/qingDevCodes/miaolinju-site/pages/builds/latest
curl -I https://qingdevcodes.github.io/miaolinju-site/
curl -I https://qingdevcodes.github.io/miaolinju-site/assets/og-cover-1200x630.png
curl -I https://qingdevcodes.github.io/miaolinju-site/favicon.ico
curl -I https://qingdevcodes.github.io/miaolinju-site/assets/apple-touch-icon.png
curl -I https://qingdevcodes.github.io/miaolinju-site/assets/icon-512.png
curl -I https://qingdevcodes.github.io/miaolinju-site/assets/qrcode.png
```

站点首页 canonical 与 `sitemap.xml` 使用上述稳定 URL。项目型 Pages 的有效 robots 位于 `https://qingdevcodes.github.io/robots.txt`，项目子目录中的 robots 文件不能控制它；2026-11-06 检查根 robots 返回 404，本仓未改动域名根站点，也未设置 `noindex`。

Google、百度站长所有权验证和提交尚未执行；公开可读取与已被发现、抓取、收录、排名或 AI 引用是不同状态，不承诺收录。没有自有域名、国内云、付费认证或备案操作。

公开反馈请使用本仓 Issues，请勿附上后台链接、token、身份证明或私人联系方式。
