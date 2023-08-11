---
description: 小试牛刀-创建一个新矿石
---

# 小试牛刀-创建一个新矿石

接下来，让我们以红宝石为例，一步一步添加它进入我们的世界

将红宝石矿石以及红宝石块的材质添加进入customores/textures/block

为了方便处理，贴图名称分别为 矿石 hbs.png，红宝石块hbs\_block.png

强烈建议这么命名，因为很整齐

<figure><img src="../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>



然后 添加红宝石的材质进入customores/textures/ore&#x20;

红宝石贴图的名称为ihbs.png

<figure><img src="../../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

接下来，打开我们的customores/configs，并打开blocks.yml

```
info:
  namespace: customores
items:
  zbs:
    display_name: 紫宝石矿
    resource:
      generate: true
      material: PAPER
      textures:
        - block/zbs.png
    specific_properties:
      block:
        cancel_drop: true
        placed_model:
          type: REAL_NOTE
          break_particles: ITEM
        break_tools_blacklist:
        - WOODEN_PICKAXE
        - STONE_PICKAXE
        break_tools_whitelist:
        - PICKAXE
        - pickaxe
  izbs:
    display_name: 紫宝石
    resource:
      material: PAPER
      generate: true
      textures:
        - ore/izbs.png
  zbs_block:
    display_name: 紫宝石块
    resource:
      material: PAPER
      generate: true
      textures:
        - block/zbs_block.png
    specific_properties:
      block:
        cancel_drop: true
        placed_model:
          type: REAL_NOTE
          break_particles: ITEM
        break_tools_blacklist:
        - WOODEN_PICKAXE
        - STONE_PICKAXE
        break_tools_whitelist:
        - PICKAXE
        - pickaxe    
loots:
  blocks:
    zbs:
      type: zbs
      drop_only_first: true
      items:
        izbs:
          item: customores:izbs
          min_amount: 1
          max_amount: 2
          chance: 100
```

根据上述代码，仿制一下，就可以得到

```
info:
  namespace: customores
items:
  zbs:
    display_name: 紫宝石矿
    resource:
      generate: true
      material: PAPER
      textures:
        - block/zbs.png
    specific_properties:
      block:
        cancel_drop: true
        placed_model:
          type: REAL_NOTE
          break_particles: ITEM
        break_tools_blacklist:
        - WOODEN_PICKAXE
        - STONE_PICKAXE
        break_tools_whitelist:
        - PICKAXE
        - pickaxe
  izbs:
    display_name: 紫宝石
    resource:
      material: PAPER
      generate: true
      textures:
        - ore/izbs.png
  zbs_block:
    display_name: 紫宝石块
    resource:
      material: PAPER
      generate: true
      textures:
        - block/zbs_block.png
    specific_properties:
      block:
        cancel_drop: true
        placed_model:
          type: REAL_NOTE
          break_particles: ITEM
        break_tools_blacklist:
        - WOODEN_PICKAXE
        - STONE_PICKAXE
        break_tools_whitelist:
        - PICKAXE
        - pickaxe
  hbs: #编号是唯一的，便于分辨和使用。默认按照贴图名称来。别搞什么Niu之类的自己甚至分不清
    display_name: 红宝石矿   #名字，可以带颜色符号，如果要带颜色符得打引号。英文引号！
    resource:    #这一部分不要管
      generate: true   
      material: PAPER
      textures:
        - block/hbs.png  #贴图地址，hbs.png在block文件夹下
    specific_properties:
      block:
        cancel_drop: true  #是否不掉落本身 类似钻石那样的都是true
        placed_model:
          type: REAL_NOTE  #不管
          break_particles: ITEM  #不管
        break_tools_blacklist: #可破坏的黑名单，在这里面的没法破坏
        - WOODEN_PICKAXE  
        - STONE_PICKAXE
        break_tools_whitelist: #白名单，只有带pickaxe的才能挖掘，也就是仅限镐
        - PICKAXE
        - pickaxe
  ihbs:
    display_name: 红宝石
    resource:
      material: PAPER
      generate: true
      textures:
        - ore/ihbs.png
  hbs_block: #配置同上
    display_name: 红宝石块
    resource:
      material: PAPER
      generate: true
      textures:
        - block/hbs_block.png
    specific_properties:
      block:
        cancel_drop: false
        placed_model:
          type: REAL_NOTE
          break_particles: ITEM
        break_tools_blacklist:
        - WOODEN_PICKAXE
        - STONE_PICKAXE
        break_tools_whitelist:
        - PICKAXE
        - pickaxe      
loots: 
  blocks:
    zbs:
      type: zbs
      drop_only_first: true
      items:
        izbs:
          item: customores:izbs
          min_amount: 1
          max_amount: 2
          chance: 100
    hbs: #掉落物配置
      type: hbs
      drop_only_first: true
      items:
        izbs:
          item: customores:ihbs #掉落物品
          min_amount: 1 #最大最小个数
          max_amount: 1
          chance: 100  #几率
```



保存 依次输入iareload iazip

我们就可以看到 红宝石矿出现力

<figure><img src="../../.gitbook/assets/image (13).png" alt=""><figcaption><p>成功</p></figcaption></figure>
