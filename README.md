# Venera 漫画源

为 Venera 维护的一组独立 JavaScript 漫画源与个人书库连接器。仓库里的每个源都是单独的脚本，目录清单记录名称、文件名、标识和版本，方便按需选择、导入和检查。

这是一个社区维护的配置仓库，不是 Venera 应用本身，也不是官方上游仓库。源脚本负责把各站点或书库的接口接入 Venera；站点服务、账号权限和网络环境由各自服务提供方决定。

## 收录内容

当前 `index.json` 列出 30 个源。在线漫画站点与目录源如下：

| 源 | 脚本 |
| --- | --- |
| 拷贝漫画 | `copy_manga.js` |
| Komiic | `komiic.js` |
| 包子漫画 | `baozi.js` |
| Picacg | `picacg.js` |
| nhentai | `nhentai.js` |
| 紳士漫畫 | `wnacg.js` |
| ehentai | `ehentai.js` |
| 禁漫天堂 | `jm.js` |
| MangaDex | `manga_dex.js` |
| 爱看漫 | `ikmmh.js` |
| 少年ジャンプ＋ | `shonen_jump_plus.js` |
| hitomi.la | `hitomi.js` |
| comick | `comick.js` |
| 优酷漫画 | `ykmh.js` |
| 再漫画 | `zaimanhua.js` |
| 漫画柜 | `manhuagui.js` |
| 漫蛙吧 | `manwaba.js` |
| カドコミ | `comic_walker.js` |
| 漫画1234 | `mh1234.js` |
| CCC追漫台 | `ccc.js` |
| GoDa漫画 | `goda.js` |
| 18漫画 | `mh18.js` |
| 漫小肆 | `mxs.js` |
| 漫画人 | `manhuaren.js` |
| H-Comic | `hcomic.js` |
| jcomic.net | `jcomic.js` |
| 热辣漫画 | `hot_manga.js` |

此外还包括连接个人书库的 Komga（`komga.js`）、Kavita（`kavita.js`）和 Lanraragi（`lanraragi.js`）。这些服务需要你自己的服务器地址及相应账号配置。

各源实现的功能和设置并不完全相同；搜索、分类、详情、章节或登录能力以对应脚本为准。`index.json` 是源名称、文件名、`key` 和版本号的目录；`_template_.js` 提供新源结构示例，`_venera_.js` 提供 Venera 源 API 的类型与接口参考。

## 导入单个源

如果你使用的 Venera 版本支持导入自定义 JavaScript 源，可以直接使用对应文件的 Raw 地址：

```text
https://raw.githubusercontent.com/ikznbfin/venera-configs/main/<脚本文件名>
```

例如，包子漫画源：

```text
https://raw.githubusercontent.com/ikznbfin/venera-configs/main/baozi.js
```

源文件名可从 [`index.json`](https://github.com/ikznbfin/venera-configs/blob/main/index.json) 查找。将地址交给应用的自定义源导入功能；如果当前版本不支持 URL 导入，可下载对应 `.js` 文件，再按应用提供的本地导入方式添加。应用的菜单位置和导入步骤可能随版本变化。

需要使用其他分支时，把地址中的 `main` 换成目标分支名。通过某个分支的 Raw 地址导入，才能明确选择该分支上的文件。

## 源更新地址

每个脚本内部还定义了供应用更新源时使用的地址。当前不少脚本指向官方上游 `venera-app/venera-configs`，而不是本 fork。也就是说，从本仓库导入 Raw 文件，不会自动把脚本内部的更新地址改成本仓库；应用后续更新时应以该脚本自身的 `url` 字段为准。若要持续使用本 fork 的改动，请用本仓库目标分支的 Raw 地址重新导入，或在脚本中将更新地址改为对应的 fork 地址。

## 配置与隐私

部分站点源需要按脚本设置域名、分流、图片 CDN 或登录信息；个人书库源需要填写你自己的服务地址和认证信息。请只在 Venera 应用的源设置中配置个人凭据，不要把密码、Cookie、访问令牌或含凭据的日志提交到 GitHub。

## 可用性说明

脚本被收录或离线解析测试通过，不代表对应网站当前可访问，也不保证每个源都能在所有网络、地区或 Venera 版本中正常阅读。站点可能调整域名、接口、反爬策略或登录要求；个人书库则取决于服务器可达性和自身配置。遇到问题时，先确认站点或服务器在当前网络可访问，再检查源设置和 Venera 日志；分享日志前请移除账号、密码、Cookie、令牌等敏感信息。
