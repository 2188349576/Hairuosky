---
description: 另一个十分重要的配置文件
---

# spigot.yml

```
settings:
  //debug模式 一般用不上
  debug: false
  
  //只在服务器停止时储存玩家缓存
  save-user-cache-on-stop-only: false
  
  //群组服模式 开！
  bungeecord: true
  
  //控制将鼠标悬停在客户端服务器列表中的玩家计数上时显示的(随机选择的)样本玩家数量。
  //我也不知道啥意思
  sample-count: 12
  
  //每隔多少 ticks（20ticks/1s）刷新玩家在数据遍历中的顺序，
  //可以有效调整玩家在内存中顺序，在 PvP 服务器上有些帮助，低于100会导致性能问题
  player-shuffle: 0
  
  //玩家缓存大小
  user-cache-size: 1000
  
  //移动错误阈值 不管他
  moved-wrongly-threshold: 0.0625
  
  //移动过快阈值
  moved-too-quickly-multiplier: 10.0
  
  //超时阈值
  timeout-time: 60
  
  //关于服务器崩溃重启的相关设置
  //面板会自动调整 不需要管他
  restart-on-crash: true
  restart-script: ./start.sh
  
  //netty通信线程数
  //不管
  netty-threads: 4
  
  //一些属性设置 对于RPG来说非常重要
  attribute:
    //最大血量
    maxHealth:
      max: 2048.0
    //最大速度
    movementSpeed:
      max: 2048.0
    //最大伤害
    attackDamage:
      max: 2048.0
      
  //日志中记录村民死亡
  log-villager-deaths: false
  
  //日志记录被命名实体的死亡
  log-named-deaths: false
  
  //一些消息设置
messages:

  //不在服务器白名单内的拒绝信息
  whitelist: You are not whitelisted on this server!
  
  //输入位置指令的信息
  unknown-command: Unknown command. Type "/help" for help.
  
  //服务器满员的信息
  server-full: The server is full!
  
  //客户端版本低于服务器版本的信息
  outdated-client: Outdated client! Please use {0}
  
  //客户端版本高于服务器版本的信息
  outdated-server: Outdated server! I'm still on {0}
  
  //服务器重启时加入的拒绝信息
  restart: Server is restarting
  
//指令相关
commands:
  //日志中记录指令
  log: true
  
  //tab补全功能
  tab-complete: 0
  
  //是否发送命令命令空间
  send-namespaced: true
  
  //垃圾排除,支持多项且使用英文逗号分隔
  spam-exclusions:
  - /skill
  
  
  //屏蔽命令方块的控制台输出
  silent-commandblock-console: false
  
  //禁用bukkit对下列指令的实现
  replace-commands:
  - setblock
  - summon
  - testforblock
  - tellraw

//成就相关
advancements:
  //关闭保存
  disable-saving: false
  disabled:
  - minecraft:story/disabled
  
//取消玩家数据保存
players:
  disable-saving: false
 
//世界设置
world-settings:
  default:
    //允许在现有区块中生成低于Y=0的方块。
    below-zero-generation-in-existing-chunks: true
    
    /会禁用冗长的调试输出
    verbose: false
    
    //合并相关，就是说固定范围内的相同物品会合并在一起 能大幅提高性能
    merge-radius:
      //经验合并范围
      exp: 6.0
      //物品合并范围
      item: 4.0
      
    //实体生成范围
    mob-spawn-range: 6
    
    //凋零生成的声音范围
    wither-spawn-sound-radius: 0
    
    //末地传送门的声音范围
    end-portal-sound-radius: 0
    
    //作物成长速度微调
    //不建议修改
    growth:
      cactus-modifier: 100
      cane-modifier: 100
      melon-modifier: 100
      mushroom-modifier: 100
      pumpkin-modifier: 100
      sapling-modifier: 100
      beetroot-modifier: 100
      carrot-modifier: 100
      potato-modifier: 100
      wheat-modifier: 100
      netherwart-modifier: 100
      vine-modifier: 100
      cocoa-modifier: 100
      bamboo-modifier: 100
      sweetberry-modifier: 100
      kelp-modifier: 100
      twistingvines-modifier: 100
      weepingvines-modifier: 100
      cavevines-modifier: 100
      
    //实体活动范围
    //建议适当降低来提高服务器性能
    //单位为块，以animals为例
    //距离玩家32米以外的动物将会被冻结而不会移动
    entity-activation-range:
      animals: 32
      monsters: 32
      raiders: 48
      misc: 16
      tick-inactive-villagers: true
      ignore-spectators: false
      
    //吸引距离
    //在指定距离内被吸引
    //比如敌对生物将会在48米内前去攻击玩家
    //适当降低可以提高服务器性能
    entity-tracking-range:
      players: 48
      animals: 48
      monsters: 48
      misc: 32
      display: 128
      other: 64
      
    //对漏斗物品的检测频率
    //适当提高能够提高服务器性能
    ticks-per:
      hopper-transfer: 24
      hopper-check: 24
      
    //漏斗每次传输物品的最大数量
    hopper-amount: 3
    
    //漏斗可以强加载区块
    //严格禁用！
    //服务器要禁用所有强加载区块的东西
    hopper-can-load-chunks: false
    
    //末影龙死亡声音范围
    dragon-death-sound-radius: 0
    
    //乱七八糟的生成码  不管
    seed-village: 10387312
    seed-desert: 14357617
    seed-igloo: 14357618
    seed-jungle: 14357619
    seed-swamp: 14357620
    seed-monument: 10387313
    seed-shipwreck: 165745295
    seed-ocean: 14357621
    seed-outpost: 165745296
    seed-endcity: 10387313
    seed-slime: 987234911
    seed-nether: 30084232
    seed-mansion: 10387319
    seed-fossil: 14357921
    seed-portal: 34222645
    
    //饱食度消耗速率
    //如果希望提高难度 可以适当提高数值 反之亦然
    hunger:
      jump-walk-exhaustion: 0.05
      jump-sprint-exhaustion: 0.2
      combat-exhaustion: 0.1
      regen-exhaustion: 6.0
      swim-multiplier: 0.01
      sprint-multiplier: 0.1
      other-multiplier: 0.0
      
    //每tick处理的最多tnt数量
    //除非有**玩家非得搞一堆tnt炸服，
    //或者有大量tnt复制装置
    //这个数值建议下调
    max-tnt-per-tick: 10
    
    //视距，同server.properties
    view-distance: default
    
    //模拟距离
    //我不知道啥意思 下面是AI的解释
    //在 Minecraft 中，模拟距离（simulation distance）
    //是指服务器在不同玩家周围加载和模拟方块和实体的距离范围。
    //当玩家在服务器上移动时，服务器会加载并模拟该玩家周围一定距离内的方块和实体，
    //以让玩家获得一个无缝的游戏体验。
    simulation-distance: default
    
    //打雷的概率
    //为该数值的倒数
    thunder-chance: 100000
    
    //地上的物品消失的时间
    //适当降低可以提高服务器性能
    item-despawn-rate: 1200
    
    //允许僵尸猪灵在传送门旁边生成
    enable-zombie-pigmen-portal-spawns: true
    
    //射出的箭矢的消失时间
    //适当降低可以提高服务器性能
    arrow-despawn-rate: 1200
    
    //三叉戟的消失时间
    //同上
    trident-despawn-rate: 1200
    
    //悬挂实体的更新频率
    hanging-tick-frequency: 100
    
    //僵尸是否攻击村民
    zombie-aggressive-towards-villager: true
    
    //刷怪笼生成的怪物是否是傻子
    //傻子：原地不动 无攻击性
    nerf-spawner-mobs: false
    
//配置文件版本
config-version: 12

//统计数据的保存
stats:
  disable-saving: false
  forced-stats: {}
```
