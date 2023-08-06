---
description: 最重要的配置文件
---

# server.properties



```
#Minecraft server properties
#Sat Aug 05 21:23:18 CST 2023
//允许飞行。建议在有飞行物品等服务器开启
//否则他将会在普通玩家滞空时间过长后踢出服务器
allow-flight=true

//允许地狱
//允许服务器生成地狱 默认开
allow-nether=true

//向OP广播控制台指令 默认开
broadcast-console-to-ops=true

//将rcon机器人的指令广播给OP 服务器rcon默认关
//因为俩机器人都挂了。设置了也没用
broadcast-rcon-to-ops=true

//debug开关，可以获得服务端更多的相关信息以分析服务器错误
debug=false

//服务器难度设置 必须hard 要不然太简单多没意思
//是吧😁
difficulty=hard

//启用命令方块
//强烈建议关 否则如果服务器带有NBT编辑类的东西
//可能导致玩家获取命令方块然后获得OP权限
enable-command-block=false

//启用jmx监视
//JMX是Java平台的一种管理和监控技术，它允许你监控和管理应用程序、
//设备和系统。
//JMX监控允许你以更高级的方式监控和管理服务器的运行状态和性能指标。
//当enable-jmx-monitoring设置为true时，
//Minecraft服务器将启用JMX监控功能，这样你可以通过JMX工具连接到服务器，
//获取和查看关于服务器的各种信息，例如内存使用情况、
//线程状态、GC（Garbage Collection）统计等。
//这对于服务器管理员和开发人员来说是一种强大的工具，
//可以帮助他们更好地了解服务器的运行状况并进行故障排除和优化。
enable-jmx-monitoring=false

//启用查询
//让服务器可以被软件等查询在线状态等
enable-query=false

//启用rcon 默认禁用，机器人都被风控了怎么用？！
enable-rcon=false

//是否启用Minecraft服务器状态查询的设置。
//mc百科上要用 默认开
enable-status=true

// 是否强制启用安全配置文件
enforce-secure-profile=true

// 是否强制启用白名单
enforce-whitelist=false

// 实体广播范围百分比
entity-broadcast-range-percentage=100

// 是否强制游戏模式
force-gamemode=false

// 函数权限级别
function-permission-level=2

// 默认游戏模式
gamemode=survival

// 是否生成结构
generate-structures=true

// 生成器设置
generator-settings={}

// 是否开启硬核模式
hardcore=false

// 是否隐藏在线玩家
hide-online-players=false

// 初始禁用的数据包
initial-disabled-packs=

// 初始启用的数据包
initial-enabled-packs=vanilla

// 世界名称 也就是根目录下主世界的文件夹
level-name=world

// 世界种子
level-seed=

// 世界类型 根据添加的MOD可以调整世界类型
level-type=minecraft:normal

// 最大连接的相邻区块更新数
max-chained-neighbor-updates=1000000

// 最大玩家数量
max-players=50

// 最大刻钟时间
max-tick-time=60000

// 最大世界尺寸
max-world-size=29999984

// 服务器的MOTD（欢迎消息）
motd=A Minecraft Server

// 网络压缩阈值 设置为-1为禁用。让waterfall进行相关处理
network-compression-threshold=-1

// 是否启用在线模式验证
//服务器使用外置登录也需要它噢！
online-mode=true

// 操作员权限级别
// 4级可以使用reload stop指令
op-permission-level=4

// 玩家空闲超时时间
player-idle-timeout=0

// 是否阻止代理连接
prevent-proxy-connections=false

// 是否开启PvP
pvp=true

// 查询端口
query.port=30001

// 请求限制
rate-limit=0

// RCON密码
rcon.password=

// RCON端口
rcon.port=25575

// 是否需要资源包
// 由IA托管，这里不需要设置
require-resource-pack=false

// 资源包URL
// 同上
resource-pack=

// 资源包提示
resource-pack-prompt=

// 资源包SHA1校验值
resource-pack-sha1=

// 服务器IP地址。默认不填，服务端会默认0.0.0.0 也就是所有人可访问
server-ip=

// 服务器端口
server-port=30001

// 模拟距离
simulation-distance=10

// 是否生成动物
spawn-animals=true

// 是否生成怪物
spawn-monsters=true

// 是否生成NPC
spawn-npcs=true

// 生成保护半径
spawn-protection=16

// 是否同步区块写入
sync-chunk-writes=true

// 文本过滤配置
text-filtering-config=

// 是否使用本机传输
use-native-transport=true

// 视距
// 根据服务器性能 适当减小到4
// 服务器那颗12100小钢炮+64G 6000Mhz D5和杂牌硬盘怎么招的住！
view-distance=10

// 是否启用白名单
white-list=false
```
