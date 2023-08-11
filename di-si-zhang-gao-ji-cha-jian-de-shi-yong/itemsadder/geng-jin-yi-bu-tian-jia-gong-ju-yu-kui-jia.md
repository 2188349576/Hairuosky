---
description: 更进一步-添加工具与盔甲
---

# 更进一步-添加工具与盔甲

我们已经完成了矿石的添加

接下来，让我们完成工具与盔甲的添加。

接下来，我们只需要准备工具的贴图。

并将他丢尽/customores/textures/tools力

<figure><img src="../../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

接下来，打开customores/configs里的tools.yml

继续仿制代码

```
info:
  namespace: customores
items:
  zbs_axe:
    display_name: 紫宝石斧
    durability:
      max_custom_durability: 800
    resource:
      material: DIAMOND_AXE
      generate: true
      textures:
      - tools/zbs_axe.png
  zbs_pickaxe:
    display_name: 紫宝石镐
    durability:
      max_custom_durability: 800
    resource:
      material: DIAMOND_PICKAXE
      generate: true
      textures:
      - tools/zbs_pickaxe.png
  zbs_hoe:
    display_name: 紫宝石锄
    durability:
      max_custom_durability: 800
    resource:
      material: DIAMOND_HOE
      generate: true
      textures:
      - tools/zbs_hoe.png
  zbs_sword:
    display_name: 紫宝石剑
    durability:
      max_custom_durability: 800
    resource:
      material: DIAMOND_SWORD
      generate: true
      textures:
      - tools/zbs_sword.png
  zbs_shovel:
    display_name: 紫宝石铲
    durability:
      max_custom_durability: 800
    resource:
      material: DIAMOND_SHOVEL
      generate: true
      textures:
      - tools/zbs_shovel.png
      
   hbs_axe: #ID 与贴图名保持一致
    display_name: 红宝石斧  #实际的名字
    durability:
      max_custom_durability: 1800  #耐久
    resource:
      material: DIAMOND_AXE  //实际代替的东西，类型一样，要是镐子都是镐子
      generate: true  //不管
      textures:
      - tools/hbs_axe.png //贴图地址，tools下的hbs_axe.png
  hbs_pickaxe:
    display_name: 红宝石镐 //下面全部同上
    durability:
      max_custom_durability: 1800
    resource:
      material: DIAMOND_PICKAXE
      generate: true
      textures:
      - tools/hbs_pickaxe.png
  hbs_hoe:
    display_name: 红宝石锄
    durability:
      max_custom_durability: 1800
    resource:
      material: DIAMOND_HOE
      generate: true
      textures:
      - tools/hbs_hoe.png
  hbs_sword:
    display_name: 红宝石剑
    durability:
      max_custom_durability: 1800
    resource:
      material: DIAMOND_SWORD
      generate: true
      textures:
      - tools/hbs_sword.png
  hbs_shovel:
    display_name: 红宝石铲
    durability:
      max_custom_durability: 1800
    resource:
      material: DIAMOND_SHOVEL
      generate: true
      textures:
      - tools/hbs_shovel.png
```

保存，依次iareload iazip

<figure><img src="../../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

多好啊。



接下来是盔甲的添加。由于IA已经提前设定好了盔甲的模型之类的，我们只需要指定颜色这个参数就可以了

打开helmet.yml，继续仿制代码

```
info:
  namespace: customores
items:
  zbs_head:
    display_name: "紫宝石头盔"
    resource:
      generate: true
    durability:
      max_custom_durability: 275
    specific_properties:
      armor:
        slot: head
        color: c536ff
    attribute_modifiers:
      head:
        armor: 9
        armorToughness: 1
  zbs_chest:
    display_name: 紫宝石胸甲
    resource:
      generate: true
    durability:
      max_custom_durability: 400
    specific_properties:
      armor:
        slot: chest
        color: c536ff
    attribute_modifiers:
      chest:
        armor: 7
        armorToughness: 1
  zbs_legs:
    display_name: 紫宝石护腿
    resource:
      generate: true
    durability:
      max_custom_durability: 375
    specific_properties:
      armor:
        slot: legs
        color: c536ff
    attribute_modifiers:
      legs:
        armor: 5
        armorToughness: 1
  zbs_boots:
    display_name: 紫宝石靴子
    resource:
      generate: true
    durability:
      max_custom_durability: 325
    specific_properties:
      armor:
        slot: FEET
        color: c536ff
    attribute_modifiers:
      feet:
        armor: 3
        armorToughness: 1
  hbs_head:     //ID唯一，建议物品名+slot，即hbs+head
    display_name: "红宝石头盔"   //名字
    resource:
      generate: true
    durability:
      max_custom_durability: 475 //耐久，建议按照原版的耐久成比例变化，这样更均衡
      //比如，举例子，原版的钻石甲耐久分别为1220 1330 1000 1080，那一起×0.8就可以得到
      //新的耐久
    specific_properties:
      armor:
        slot: head  //槽位
        color: eb3353  //颜色，16进制代码，刚好是红色
    attribute_modifiers:
      head:
        armor: 9  //护甲值
        armorToughness: 1  //韧性
  hbs_chest:
    display_name: 红宝石胸甲  //全部同上
    resource:
      generate: true
    durability:
      max_custom_durability: 600
    specific_properties:
      armor:
        slot: chest
        color: eb3353
    attribute_modifiers:
      chest:
        armor: 7
        armorToughness: 1
  hbs_legs:
    display_name: 红宝石护腿
    resource:
      generate: true
    durability:
      max_custom_durability: 575
    specific_properties:
      armor:
        slot: legs
        color: eb3353
    attribute_modifiers:
      legs:
        armor: 5
        armorToughness: 1
  hbs_boots:
    display_name: 红宝石靴子
    resource:
      generate: true
    durability:
      max_custom_durability: 525
    specific_properties:
      armor:
        slot: FEET
        color: eb3353
    attribute_modifiers:
      feet:
        armor: 3
        armorToughness: 1
```

那么，继续iareload iazip

<figure><img src="../../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

多是一件美事啊！
