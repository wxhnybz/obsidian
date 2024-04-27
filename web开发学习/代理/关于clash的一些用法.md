# ClashX for macOS 代理使用教程
ClashX 是基于 Clash 内核的 图形界面客户端，支持 HTTPS, VMess, Shadowsocks,  
Trojan, Snell 等代理协议。

## 下载

**安装**

1. 不要直接在压缩包里打开 ClashX ，这样无法正常使用。
2. 将 ClashX 拖入“应用程序 / Applicatitons”文件夹以安装。
3. 打开“应用程序 / Applicatitons”文件夹，找到 ClashX 图标。
4. 按住 ⌃ 键的同时点击 ClashX 图标，在弹出的菜单中选取“打开”。
5. 根据屏幕上的提示操作。
6. 打开成功后，屏幕顶部菜单栏会显示 ClashX 图标 ![menu_icon_16x16__2x.png](https://xtrojan.pro/wp-content/uploads/2021/09/menu_icon_16x16__2x.png) 。
7. 如果您安装了多个代理类客户端，有可能引起端口冲突。按照本文档设置完成后，如果无法正常使用，请先尝试卸载其它代理客户端再试一次。

## 导入节点

1. 请先**关闭网页翻译功能**，避免翻译错误与教程原义不符。
2. 前往用户后台复制 **macOS** > **Clash** 的订阅地址。
3. 轻点菜单栏 ClashX 图标 > 配置 > 托管配置 > 管理 。

**导入节点**

1. 确保已购买服务套餐并且未过期；
2. 登录“用户后台”>“Mac”> “ClashX”>  轻点“复制订阅地址”；
3. 打开应用程序 > 轻点菜单栏 ClashX 图标 ![menu_icon_16x16__2x.png](https://xtrojan.pro/wp-content/uploads/2021/09/menu_icon_16x16__2x.png)   >“配置” >“托管配置”>“管理”；
4. 轻点“添加”>  在 Url 处输入“订阅地址”，在 Config Name 处输入“AUVPN”；
5. 轻点“保存 / Save”，如果导入节点失败，请尝试 WIFI 或 4G 热点；
6. 成功导入节点后，鼠标移动至“Proxy”或“GLOBAL”可显示节点列表。

**必须每天同步节点**

为了绕过 GFW 不断升级的封锁技术，持续为您提供最新稳定快速的服务，我们会在不通知您的情况下经常更新节点。为了能及时获得最新节点以及清除本地无效节点，您必须每天同步节点：

- 依次点击 ClashX >“配置 / Config”>“托管配置 / Remote Config” > “更新 / Update”。

## 选择节点

轻点图标  ![menu_icon_16x16__2x.png](https://xtrojan.pro/wp-content/uploads/2021/09/menu_icon_16x16__2x.png)  >“GLOBAL”或 “Proxy”，点击“延迟测速 / Speed test”可找到可用节点，根据您的需求选择可用节点。

**哪个节点网速最快**

Clash 的测速功能检测的是 HTTP GET 延迟，延迟 ≠ 下载速度。

- 小流量应用（电子邮件、即时通讯、音乐）依赖延迟。
- 大流量应用（视频、图片、直播）依赖下载速度。

另外，不同地区、不同运营商、不同时间段连接同一个节点的速度都有差异 。

因此，只需要在实际使用过程中，多尝试不同节点，便可找到适合自己的节点。

**全局连接 / Global 代理模式下不要选 DIRECT 和 REJECT 节点**

DIRECT 是直连，REJECT是拒绝。

Global 模式下，选 DIRECT 会无法访问国际互联网，选 REJECT 会连大陆网站都无法访问。

## 选择代理模式

轻点图标 ![menu_icon_16x16__2x.png](https://xtrojan.pro/wp-content/uploads/2021/09/menu_icon_16x16__2x.png) >“出站模式 / Proxy Mode”，根据您的需求选择代理模式：

**全局连接 / Global：代理所有流量**

适用于不依赖大陆服务的用户。

对国外流量效果非常好，大陆流量会被减速。

**规则判断 / Rules：只代理国外流量**

适用于同时使用国内外服务的用户。

大陆流量不会消耗套餐流量。

在大陆网站上查询 IP 得到的是本地 IP 地址。

在国外网站上查询 IP 得到的是代理 IP 地址。

分流规则无法做到全面且具有时效性，如果遇到以下情况，请尝试全局代理。

- 无法打开国际网站；
- 加载国际网站缓慢；
- 无法解锁 Netflix / Spotify 等区域限制内容。

**脚本模式 / Script：更灵活地自定义规则**

官方手册：[https://lancellc.gitbook.io/clash/clash-config-file/script](https://lancellc.gitbook.io/clash/clash-config-file/script)

**直接连接 / Direct：不代理任何流量**

选择此模式将导致无法翻墙，与关闭 VPN 的效果一致。

## 设置代理

轻点图标  ![menu_icon_16x16__2x.png](https://xtrojan.pro/wp-content/uploads/2021/09/menu_icon_16x16__2x.png)  >  勾选“设置为系统代理”即可访问国际互联网。

**我已选择可用节点，但 Chrome 无法访问境外网站怎么办**

Chrome 没有手动设置代理的图形界面选项，有以下方法：

- 在终端里运行以下命令：
    
    pkill Chrome; sleep 1s; open -b com.google.Chrome --args --proxy-server=http://127.0.0.1:7890
    

**LINE 无法连接服务器怎么办**

LINE 不会跟随系统代理设置，需要在 LINE 的高级设置里手动配置代理：

1. 确保浏览器可以正常访问境外网站。
2. ✅ 启用代理服务器
3. 代理服务器：**HTTP** 或 **SOCKS5 。**
4. 服务器：**127.0.0.1**:**7890**

**如何为所有应用程序设置代理**

部分应用程序不会跟随系统代理，也无法在应用程序里手动设置代理，则可以通过 TAP 模式代理这些流量。

1. 选中增强模式。
2. 取消选中设置为系统代理。

## 故障排查及解决方法

设置或使用过程中容易出错的地方，上文已基本涵盖，如果还有问题，请使用通用解决方法。

**无法使用的通用解决方法**

通用解决方法不需要排查无法使用的具体原因，就能快速解决大部分问题。

1. 将 ClashX 重置为默认设置。
    1. 依次点击 ClashX 图标 > 配置 > 打开本地配置文件夹
    2. 退出 ClashX ，删除配置文件夹下的所有文件和文件夹。
2. 使用本站提供的最新版 Clash 。
3. 您以前保存的订阅地址可能已经失效，从用户后台重新复制订阅地址。
4. 按照本教程重新设置。

这样操作后如果仍然有问题，请直接联系客服通过远程桌面帮您解决问题