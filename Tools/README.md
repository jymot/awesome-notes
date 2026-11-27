# Tools

开发与效率工具。配置片段见 [Config](../Config/README.md)。

## 下载器
 - [gopeed](https://github.com/GopeedLab/gopeed)
    - A modern download manager that supports all platforms. Built with Golang and Flutter.
    - Gopeed（全称 Go Speed），直译过来中文名叫做够快下载器（不是狗屁下载器！），是一款由Golang+Flutter开发的高速下载器，支持（HTTP、BitTorrent、Magnet）协议下载，并且支持全平台使用。除了基本的下载功能外，Gopeed 还是一款高度可定制化的下载器，支持通过对接APIs或者安装和开发扩展来实现更多的功能。

## 效率与终端
 - [protopie](https://www.protopie.cn/)
   - 高保真原型
 - [insomnia `The most intuitive cross-platform REST API Client 😴 https://insomnia.rest`](https://github.com/Kong/insomnia)
 - [Lepton `Cross-platform snippet/note manager based on GitHub Gist. `](https://github.com/hackjutsu/Lepton)
 - [lanproxy `anproxy是一个将局域网个人电脑、服务器代理到公网的内网穿透工具，目前仅支持tcp流量转发，可支持任何tcp上层协议（访问内网网站、本地支付接口调试、ssh访问、远程桌面...）。目前市面上提供类似服务的有花生壳、TeamView、GoToMyCloud等等，但要使用第三方的公网服务器就必须为第三方付费，并且这些服务都有各种各样的限制，此外，由于数据包会流经第三方，因此对数据安全也是一大隐患。`](https://github.com/ffay/lanproxy/)
 - [macaca `多端自动化测试解决方案`](https://github.com/alibaba/macaca)
 - [open-source-mac-os-apps `Awesome list of open source applications for macOS.`](https://github.com/serhii-londar/open-source-mac-os-apps)
 - [WeChatPlugin-MacOS `一款功能强大的 macOS 版微信小助手 v1.7.1 / A powerful assistant for wechat macOS`](https://github.com/TKkk-iOSer/WeChatPlugin-MacOS)
 - [bat `A cat(1) clone with syntax highlighting and Git integration.`](https://github.com/sharkdp/bat)
 - [ToolsOfTheTrade `Tools of The Trade, from Hacker News.`](https://github.com/cjbarber/ToolsOfTheTrade)
 - [hyper `A terminal built on web technologies https://hyper.is`](https://github.com/vercel/hyper)
 - [baiduyun `油猴脚本 直接下载百度网盘和百度网盘分享的文件,直链下载超级加速 https://greasyfork.org/zh-CN/scripts/…`](https://github.com/syhyz1990/baiduyun)
 - [jsproxy `一个基于浏览器端 JS 实现的在线代理`](https://github.com/EtherDream/jsproxy)
 - [awesome-tmux](https://github.com/rothgar/awesome-tmux)
 - [tmux](https://github.com/tmux/tmux)
 - [iina `The modern video player for macOS. https://iina.io`](https://github.com/iina/iina)
 - [cheat.sh `the only cheat sheet you need https://cheat.sh/`](https://github.com/chubin/cheat.sh)
    - 这是一个网站，更是一个实用的速查工具：简洁的 curl / browser 界面；涵盖 55 种编程语言和 1000 多种最重要的 UNIX/Linux 命令；无需安装，随处可用。

## 图像
 - [thumbor `thumbor is an open-source photo thumbnail service by globo.com`](https://github.com/thumbor/thumbor)
 - [libjpeg-turbo `图片压缩`](https://github.com/libjpeg-turbo/libjpeg-turbo)
 - [pngquant `图片压缩`](https://github.com/kornelski/pngquant)
 - [zopfli `图片压缩`](https://github.com/google/zopfli)
 - [UPNG.js `图片压缩`](https://github.com/photopea/UPNG.js)
 - [tinypng `图片压缩`](https://tinypng.com/)

## 远程桌面

对比（基于公开资料，未实测）：大多数情况 [RustDesk](https://github.com/rustdesk/rustdesk) 更省心、更成熟；[CrossDesk](https://github.com/kunkundi/crossdesk) 较新，亮点是 WebRTC P2P 和 Web 管理后台，代价是自签证书配置更麻烦、资料少。

 - [CrossDesk](https://github.com/kunkundi/crossdesk)
    - A lightweight, cross-platform remote desktop based on WebRTC, with Web client access. Prefers P2P and falls back to TURN; official public service is available.
    - 基于 WebRTC 的开源远程桌面，优先 P2P 直连，必要时走 TURN 中继；可直接用官方公共服务。[服务端](https://github.com/kunkundi/crossdesk-server) · [自托管指南](https://www.crossdesk.cn/en/self-hosting/)
    - 自建：Linux amd64/arm64 + Docker Compose；从 Release 下载 compose.yaml 与 env.example
    - 配置：填 EXTERNAL_IP、INTERNAL_IP；`openssl rand -hex 32` 生成两个不同密钥填 COTURN_AUTH_SECRET、COTURN_STATELESS_NONCE_SECRET
    - 端口：9099/TCP 信令、3478/TCP+UDP STUN/TURN、50000–60000/UDP 中继
    - 证书与客户端：自签证书需在每个客户端导入 `certs/api.crossdesk.cn_root.crt`；「设置 → 自托管配置」填地址端口，两端须指向同一服务器；Web 管理后台 `/admin`，数据存 SQLite
 - [RustDesk](https://github.com/rustdesk/rustdesk)
    - An open-source remote desktop application designed for self-hosting, as an alternative to TeamViewer.
    - 老牌开源远程桌面，社区大，覆盖 Win/Mac/Linux/iOS/Android/Web；自建服务器简单，一个 [rustdesk-server](https://github.com/rustdesk/rustdesk-server) 容器即可，资料多。
