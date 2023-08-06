---
description: 它依然十分重要
---

# Bukkit.yml

```
# bukkit.yml

# 服务器设置
settings:
  # 是否允许进入末地
  allow-end: true
  
  # 是否在服务器过载时发出警告
  warn-on-overload: false
  
  
  # 指定权限文件名称 不管
  permissions-file: permissions.yml
  
  # 更新文件夹名称不管
  update-folder: update
  
  
  # 是否启用插件分析 不管
  plugin-profiling: false
  
  # 连接节流（每秒处理连接的最大数） 不管
  connection-throttle: 4000
  
  # 是否查询插件信息 不管
  query-plugins: true
  
  # 废弃警告详细程度，默认为默认
  deprecated-verbose: default
  
  # 关闭服务器时显示的消息
  shutdown-message: Server closed
  
  # 最小Bukkit API版本要求
  minimum-api: none
  
  # 是否使用地图颜色缓存
  use-map-color-cache: true

# 生成限制设置 适当降低能够优化服务器性能 尤其对于MOD服务器
spawn-limits:
  # 怪物生成限制
  monsters: 70
  # 动物生成限制
  animals: 10
  # 水生动物生成限制
  water-animals: 5
  # 水中环境生物生成限制
  water-ambient: 20
  # 水下地形生物生成限制
  water-underground-creature: 5
  # 环境生物生成限制
  ambient: 15

# 区块垃圾回收设置
chunk-gc:
  # 垃圾回收周期（以tick为单位）
  period-in-ticks: 600

# 游戏tick设置
ticks-per:
  # 动物生成tick
  animal-spawns: 400
  # 怪物生成tick
  monster-spawns: 1
  # 水生动物生成tick
  water-spawns: 1
  # 水中环境生物生成tick
  water-ambient-spawns: 1
  # 水下地形生物生成tick
  water-underground-creature-spawns: 1
  # 环境生物生成tick
  ambient-spawns: 1
  # 自动保存节拍（以tick为单位） 适当提高或者禁用可以节约性能
  autosave: 6000

# 命令别名（在commands.yml中定义）
aliases: now-in-commands.yml

```
