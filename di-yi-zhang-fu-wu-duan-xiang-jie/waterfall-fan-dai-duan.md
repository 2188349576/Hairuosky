---
description: 群组服最重要的核心服务端！
---

# Waterfall 反代端

首先，最重要的当然是：



## 什么是反向代理？

`反向代理在电脑网络中是代理服务器的一种。服务器根据客户端的请求，从其关系的一组或多组后端服务器上获取资源，然后再将这些资源返回给客户端，客户端只会得知反向代理的IP地址，而不知道在代理服务器后面的服务器集群的存在。(摘自 WikiPedia zh_CN 反向代理)`

事实上，你知道什么是反代也没什么用。你只需要知道他实际上的应用就可以了

## 那么，什么是waterfall呢？

事实上，他是一个由Papermc主导的、一个BungeeCord服务端的衍生版。其拥有更高的性能、更好的实际应用表现、以及更加具有优势的日志记录和控制台操作。

## 为什么不选择原版的BungeeCord端呢？

正如上文所述。Waterfall端拥有更好的日志记录以及控制台操作

~~有便宜不占是傻子~~



## 一些有关Waterfall不同于普通服务端的地方



1. 首先。当然是他的性能方面了。正如本章所述，waterfall其实是一个反向代理软件，并不是一个实际上的服务端，所以他不需要多大的内存占用。一般情况下，我们选择1G-4G的区间。  在海若青空V12中，我们选择了2G的内存分配
2. waterfall服务端的暂停指令是end而非其他服务端的stop
3. 你可以选择前往[papermc官网](https://papermc.io/downloads#Waterfall)来获得waterfall的最新版本。以确保在该死的腐竹失联的时候可以自己更新waterfall来让服务器更加安全和可靠



## 启动Waterfall

当我们启动waterfall成功后。目录里就出现了该死的Config.yml设置

他是那么长...那么长....瞬间不想写了。

```
server_connect_timeout: 5000
enforce_secure_profile: false
remote_ping_cache: -1
forge_support: true
player_limit: -1
permissions:
  default:
  - bungeecord.command.server
  - bungeecord.command.list
  admin:
  - bungeecord.command.alert
  - bungeecord.command.end
  - bungeecord.command.ip
  - bungeecord.command.reload
  - bungeecord.command.kick
timeout: 30000
log_commands: false
network_compression_threshold: 256
online_mode: true
disabled_commands:
- disabledcommandhere
servers:
  lobby:
    motd: '&1Just another Waterfall - Forced Host'
    address: localhost:25565
    restricted: false
listeners:
- query_port: 25577
  motd: '&1Another Bungee server'
  tab_list: GLOBAL_PING
  query_enabled: false
  proxy_protocol: false
  forced_hosts:
    pvp.md-5.net: pvp
  ping_passthrough: false
  priorities:
  - lobby
  bind_local_address: true
  host: 0.0.0.0:25577
  max_players: 1
  tab_size: 60
  force_default_server: false
ip_forward: false
remote_ping_timeout: 5000
prevent_proxy_connections: false
groups:
  md_5:
  - admin
connection_throttle: 4000
stats: c767e908-3819-45d9-8123-4179ada2a2be
connection_throttle_limit: 3
log_pings: true

```

噢谢。正如你所见。这里的配置文件有非常非常非常多，特别特别木及其多。

淦，我为什么要选择开群组服？

好了，言归正传。接下来，我会对配置文件中的每一行配置文件进行解释说明

<pre><code># 服务器连接超时设置为5000毫秒（即5秒），如果玩家在五秒的时间内没有成功链接进入服务器，
# 那么将断开服务器和玩家之间的链接
server_connect_timeout: 5000

# 是否强制使用安全配置文件。这里设置为false，表示不强制使用安全配置文件。
enforce_secure_profile: false

# 远程ping缓存设置为-1，表示禁用缓存。
remote_ping_cache: -1

# 启用Forge模组支持。
# 当然，我服使用fabric服务端。可能会有奇怪的问题
# 到时候再说吧 （￣︶￣）↗　
forge_support: true

# 玩家连接限制设置为-1，表示不限制玩家连接数。
player_limit: -1

<strong># 权限设置。
</strong># 其实没多大用，不过是一些指令的权限罢了。
permissions:
  # 默认权限组。
  default:
  - bungeecord.command.server
  - bungeecord.command.list
  # 管理员权限组。
  admin:
  - bungeecord.command.alert
  - bungeecord.command.end
  - bungeecord.command.ip
  - bungeecord.command.reload
  - bungeecord.command.kick

# 连接超时时间设置为30000毫秒（即30秒）。
timeout: 30000

# 是否记录命令到日志。这里设置为false，表示不记录命令。
log_commands: false

# 网络压缩阈值设置为256，表示当数据包大小超过256字节时，启用网络压缩。
# 能够有效的节约服务器带宽
network_compression_threshold: 256

# 是否启用在线模式验证。这里设置为true，
# 因为服务器使用外置登录。实际上就是劫持了正版验证。转向皮肤站验证
online_mode: true

# 禁用的命令列表开始。
disabled_commands:
- disabledcommandhere

# 服务器设置。
servers:
  # 服务器名称为"lobby"。
  lobby:
    # 服务器MOTD（欢迎消息）为'&#x26;1Just another Waterfall - Forced Host'。
    motd: '&#x26;1Just another Waterfall - Forced Host'
    
    # 服务器地址为localhost:25565。
    address: localhost:25565
    
    # 是否限制连接到此服务器。这里设置为false，表示不限制。
    restricted: false

# 监听器设置开始。
listeners:
- # 监听器的查询端口设置为25577。
  # 这是玩家需要链接的端口。
  query_port: 25577
  
  # 监听器的MOTD（欢迎消息）为'&#x26;1Another Bungee server'。
  motd: '&#x26;1Another Bungee server'
  
  # 使用全局ping列表。
  tab_list: GLOBAL_PING
  
  # 禁用查询功能。
  query_enabled: false
  
  # 禁用代理协议。
  proxy_protocol: false
  
  # 强制主机设置开始。
  forced_hosts:
    pvp.md-5.net: pvp
    
  # 是否透传ping信息。这里设置为false，表示不透传。
  ping_passthrough: false
  
  # 优先级设置开始。
  priorities:
  
  - lobby
  
  # 是否绑定本地地址。这里设置为true，表示绑定。
  bind_local_address: true
  
  # 监听器的主机地址为0.0.0.0:25577。
  host: 0.0.0.0:25577
  
  # 服务器最大玩家数设置为1。
  max_players: 1
  
  # Tab列表大小设置为60。
  tab_size: 60
  
  # 是否强制使用默认服务器。这里设置为false，表示不强制。
  force_default_server: false

# 是否启用IP转发。这里设置为false，表示不启用。
ip_forward: false

# 远程ping超时设置为5000毫秒（即5秒）。
remote_ping_timeout: 5000

# 是否阻止代理连接。这里设置为false，表示不阻止。
prevent_proxy_connections: false

# 权限组设置开始。
groups:
  # 权限组名称为"md_5"。
  md_5:
  - admin

# 连接节流设置为4000毫秒（即4秒）。
connection_throttle: 4000

# 统计追踪标识为"c767e908-3819-45d9-8123-4179ada2a2be"。
stats: c767e908-3819-45d9-8123-4179ada2a2be

# 连接节流限制设置为3。
connection_throttle_limit: 3

# 是否记录ping信息到日志。这里设置为true。
log_pings: true
</code></pre>



对于Waterfall如果有更多疑问，请参阅

mcbbs [\[进阶开服\]](https://www.mcbbs.net/forum.php?mod=forumdisplay\&fid=178\&filter=typeid\&typeid=2658)[ \[2020.12.16\]\[SCT\] 跨服端搭建教程 —— 搭建 Waterfall 和 Velocity](https://www.mcbbs.net/thread-1138148-1-1.html)





