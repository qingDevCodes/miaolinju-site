# 喵邻居介绍页

猫咪公寓题材微信小游戏的独立宣传站，只包含公开介绍、真实截图和正式码，无游戏源码、游戏包、统计脚本或运行依赖。

- 网站：https://qingdevcodes.github.io/miaolinju-site/
- 公开仓：https://github.com/qingDevCodes/miaolinju-site
- 微信小游戏 AppID：`wx99f30143ac9176d0`。
- 状态核对日期：2026-11-09。体验版已可在微信搜索并进入；正式版入口及非管理员账号仍待继续核实。

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

三张截图于 2026-11-09 从 PC 微信内当前可搜索到的喵邻居体验版实机截取，仅裁掉微信窗口顶栏，文件名沿用原有页面引用：

| 文件 | 内容 | 可确认范围 |
| --- | --- | --- |
| screenshot-game.png | 公寓对局、已入住猫与候选猫 | 微信体验版实机 |
| screenshot-result.png | 年度作品纪录（当前列表为空） | 微信体验版实机 |
| screenshot-codex.png | 猫猫图鉴与待解锁性格 | 微信体验版实机 |

三张截图均逐张目检，没有好友列表或其他微信侧栏信息。对局画面保留体验版自身的新手指示手势，没有大块引导弹窗；年度纪录尚无已完成年度，页面按实机空状态展示。体验版截图不作为正式版或非管理员账号可用性的证明。

图标 `assets/icon-512.png` 原样复制自游戏仓公开宣传素材 `docs/launch/assets/icon-512.png`。`assets/apple-touch-icon.png` 与根目录 `favicon.ico` 由该图标等比缩放生成。

`assets/og-cover-1200x630.png` 是 1200×630 的站外分享封面，左侧沿用现有图标与标题排版，右侧换为上述微信体验版实机对局截图 `screenshot-game.png`，没有生成、重绘或补造游戏内容。它同时作为首页英雄区主视觉。

微信认证已于 2026-11-08 通过，2026-11-09 已确认体验版可在微信搜索并进入。上方码图仍是既有正式码；体验版可搜索不等于正式版入口、非管理员账号、分享能力或最终备案状态均已验证。

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
