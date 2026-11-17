# website/ 官网骨架 — 部署说明与待办（2026-11-11）

## 当前状态
本地骨架 v1，两页：`index.html`（英文，根路径默认）+ `zh-Hans/index.html`（简中）。
纯静态、无 JS、自包含 CSS；素材自包含（assets/ 下 icon + 6×2 语截图 + 60s 视频 + 视频海报）。

## 🔴 红线：不影响现有线上页面
线上现有（GitHub Pages，4gk5msrpwv-cpu 账号）：
- `/privacy-pages/` — 隐私政策 11+ 语（ASC 审核引用，**绝不能动**）
- `/product/` — 22 语营销落地页（现有引流承接页，**绝不能动**）

部署时**只新增文件、不修改不删除**上述两个目录的任何内容。

## 部署方案（域名 learnnest.cn 过审后执行，二选一）
- **方案 ①（推荐）**：新建 user-site 仓库 `4gk5msrpwv-cpu/4g5msrpwv-cpu.github.io`（若已存在则直接用），把 website/ 内容放**仓库根**，同时把现有 privacy-pages、product 两目录原样迁入 → 绑定 learnnest.cn 后：根=官网、`/privacy-pages/` 与 `/product/` 路径不变（旧 github.io 链接继续有效，ASC 引用零破坏）
- **方案 ②**：website/ 作为现有仓库（privacy-pages 项目仓库）根目录新增文件 → 官网 URL 会带 /privacy-pages/ 前缀，不优雅，仅应急

## TODO（上线前必办）
1. 🔴 App Store CTA 替换为 ASC 实际 App 页 URL（两页各一处，搜 `apps.apple.com`）
2. 🔴 canonical/hreflang 已写死 learnnest.cn——若最终部署结构不同需同步修改
3. 🔴 GSC + Bing Webmaster 提交 sitemap（部署后）
4. 🟡 隐私/支持链接目前指向 github.io 绝对地址——域名生效后改为相对路径 `/privacy-pages/`
5. 🟡 英文版视频：当前视频为中文旁白，英文页未嵌入；需制作英文旁白版（edge-tts 可复用 8 段流程）
6. 🟡 changelog 的 1.0.2 描述为占位（"First public release"），按 ASC 实际版本历史校正
7. 🟢 og:image 建议后续换 1280×630 分享大图（可用 header_en_3840x1646.png 裁切）
8. 🟢 分析：部署后挂 Cloudflare Web Analytics（无 Cookie）
