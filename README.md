# Venera 漫画源配置

这是一个面向 Venera 漫画阅读器的独立漫画源配置项目，集中维护可由 Venera 加载的 JavaScript 漫画源。项目由个人维护，属于社区配置仓库，不是 Venera 官方应用，也不代表上游项目。

仓库包含在线漫画站点源，以及 Komga、Kavita、Lanraragi 等个人书库服务的连接源。各源分别实现搜索、分类、漫画详情、章节目录和阅读等能力；具体支持哪些功能，以对应源文件为准。

## 源目录

`index.json` 汇总当前收录源的名称、文件名、标识和版本。每个 `.js` 文件是一项独立源配置。

### 在线漫画站点

- 拷贝漫画、Komiic、包子漫画、Picacg、爱看漫、漫蛙吧、漫画1234、漫画柜、漫画人、漫小肆、热辣漫画、优酷漫画、再漫画、GoDa漫画、CCC追漫台、H-Comic、jcomic.net
- MangaDex、comick、Comic Walker、少年ジャンプ＋
- nhentai、ehentai、紳士漫畫、禁漫天堂、hitomi.la、18漫画

### 个人书库服务

- Komga
- Kavita
- Lanraragi

站点域名、登录要求、地区限制和反爬策略可能变化。收录不代表站点始终可访问，也不保证每个源在所有网络环境或 Venera 版本中都能正常使用。

## 使用

如果你使用的 Venera 版本支持添加自定义 JavaScript 漫画源，可从对应源文件导入；本仓库文件的 Raw 地址格式为：

```text
https://raw.githubusercontent.com/ikznbfin/venera-configs/main/<文件名>.js
```

例如，包子漫画源：

```text
https://raw.githubusercontent.com/ikznbfin/venera-configs/main/baozi.js
```

将 `<文件名>` 换成 `index.json` 中列出的 `fileName`。请按你所用 Venera 版本中的自定义源导入流程操作；如果应用不支持通过 URL 添加脚本，可直接在仓库查看或下载相应文件，再按应用支持的方式导入。

Komga、Kavita 和 Lanraragi 是连接个人书库的源，需要在 Venera 中填写你自己的服务地址及该服务要求的登录信息。不要把账号、密码或访问令牌提交到此仓库。

## 仓库结构

- `index.json`：源目录及版本信息
- `<source>.js`：单个漫画源的实现
- `_template_.js`、`_venera_.js`：源开发模板和 Venera JavaScript API 类型/接口参考

## 维护说明

源站页面、接口、域名及认证方式可能调整。遇到无法使用的源时，请先确认网络和站点本身可访问，再检查对应源的站点设置与 Venera 日志；错误日志中不要包含密码、令牌或其他凭据。

本仓库的修改只影响这里维护的配置，不会修改 Venera 应用或官方上游仓库。提交问题时，请附上源名称、Venera 版本、复现步骤和已脱敏的错误信息，便于定位。
