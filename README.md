# leaderxin.github.io

这个仓库只有一个用途：让 `leaderxin.github.io` 的**域名根**存在。

robots 协议规定爬虫只读 `scheme://host/robots.txt`，llms.txt 的约定同理。产品官网挂在项目站
`/quant-desktop/` 下，那份 `robots.txt` 和 `llms.txt` 放在子路径里，**一次都不会被访问** ——
2026-10 的抓站核查确认了 `https://leaderxin.github.io/robots.txt` 返回 404。用户站仓库补上根目录
之后，这两个文件才真正生效。

| 文件 | 作用 |
|------|------|
| `robots.txt` | 域名根的唯一一份。整站放行，并显式列出 AI 检索类爬虫（GEO 需要）；`Sitemap:` 指向产品站的 sitemap |
| `llms.txt` | 给 AI 检索用的精简事实页。**全站唯一一份** —— 产品站不再放副本，两份必然漂移 |
| `index.html` | 一次跳转到 `/quant-desktop/`。刻意 `noindex` 且不铺内容：铺了会和真正的官网争同一个品牌词 |
| `404.html` | 根域名下的自定义 404 |

产品本身的源码与官网在 [Leaderxin/quant-desktop](https://github.com/Leaderxin/quant-desktop)，
官网内容**不要在这里改** —— 这里只放域名级的东西。

## 改 llms.txt 时注意

它的内容必须与产品站同步：平台、体积、价格、许可、功能清单。尤其是许可那条 ——
PolyForm Noncommercial 不是 MIT，**商业使用需获授权**，答案引擎漏掉这句会误导人。

产品的版本号、功能清单若有大改动，回来核对一次这个文件。
