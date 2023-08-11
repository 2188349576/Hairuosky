---
description: 最重要的-合成表
---

# 最重要的-合成表

既然，大概的体系已经完成了，当然还差我们的合成表罗！

打开recipes.yml

仍然是仿制代码的工作

```
info:
  namespace: customores
recipes:
  crafting_table:
    zbs_axe:
      enabled: true
      pattern:
      - XBB
      - XAB
      - XAX
      ingredients:
        B: customores:izbs
        A: STICK
      result:
        item: customores:zbs_axe
        amount: 1
    zbs_pickaxe:
      enabled: true
      pattern:
      - BBB
      - XAX
      - XAX
      ingredients:
        B: customores:izbs
        A: STICK
      result:
        item: customores:zbs_pickaxe
        amount: 1
    zbs_hoe:
      enabled: true
      pattern:
      - XBB
      - XAX
      - XAX
      ingredients:
        B: customores:izbs
        A: STICK
      result:
        item: customores:zbs_hoe
        amount: 1
    zbs_sword:
      enabled: true
      pattern:
      - XBX
      - XBX
      - XAX
      ingredients:
        B: customores:izbs
        A: STICK
      result:
        item: customores:zbs_sword
        amount: 1
    zbs_shovel:
      enabled: true
      pattern:
      - XBX
      - XAX
      - XAX
      ingredients:
        B: customores:izbs
        A: STICK
      result:
        item: customores:zbs_shovel
        amount: 1
    zbs_boots:
      enabled: true
      pattern:
      - XXX
      - BXB
      - BXB
      ingredients:
        B: customores:izbs
      result:
        item: customores:zbs_boots
        amount: 1
    zbs_legs:
      enabled: true
      pattern:
      - BBB
      - BXB
      - BXB
      ingredients:
        B: customores:izbs
      result:
        item: customores:zbs_legs
        amount: 1
    zbs_chest:
      enabled: true
      pattern:
      - BXB
      - BBB
      - BBB
      ingredients:
        B: customores:izbs
      result:
        item: customores:zbs_chest
        amount: 1
    zbs_head:
      enabled: true
      pattern:
      - BBB
      - BXB
      - XXX
      ingredients:
        B: customores:izbs
      result:
        item: customores:zbs_head
        amount: 1
    zbs_block:
      enabled: true
      pattern:
      - BBB
      - BBB
      - BBB
      ingredients:
        B: customores:izbs
      result:
        item: customores:zbs_block
        amount: 1
    izbs:
      enabled: true
      pattern:
      - XXX
      - XBX
      - XXX
      ingredients:
        B: customores:zbs_block
      result:
        item: customores:izbs
        amount: 9
        
    hbs_axe: //红宝石斧
      enabled: true  //是否开启
      pattern:  //合成表，就是样子，X是空
      - XBB
      - XAB
      - XAX
      ingredients:
        B: customores:ihbs //B代表了自定义矿石里的ihbs，就是红宝石
        A: STICK  //原版木棍
      result:
        item: customores:hbs_axe  //合成红宝石镐子（这都是物品的ID），这就是
        //为什么不让你设置Niu或者123这种，会很乱！而且很不好维护！
        amount: 1  //合成数量1
    hbs_pickaxe:  //同上
      enabled: true
      pattern:
      - BBB
      - XAX
      - XAX
      ingredients:
        B: customores:ihbs
        A: STICK
      result:
        item: customores:hbs_pickaxe
        amount: 1
    hbs_hoe:
      enabled: true
      pattern:
      - XBB
      - XAX
      - XAX
      ingredients:
        B: customores:ihbs
        A: STICK
      result:
        item: customores:hbs_hoe
        amount: 1
    hbs_sword:
      enabled: true
      pattern:
      - XBX
      - XBX
      - XAX
      ingredients:
        B: customores:ihbs
        A: STICK
      result:
        item: customores:hbs_sword
        amount: 1
    hbs_shovel:
      enabled: true
      pattern:
      - XBX
      - XAX
      - XAX
      ingredients:
        B: customores:ihbs
        A: STICK
      result:
        item: customores:hbs_shovel
        amount: 1
    hbs_boots:
      enabled: true
      pattern:
      - XXX
      - BXB
      - BXB
      ingredients:
        B: customores:ihbs
      result:
        item: customores:hbs_boots
        amount: 1
    hbs_legs:
      enabled: true
      pattern:
      - BBB
      - BXB
      - BXB
      ingredients:
        B: customores:ihbs
      result:
        item: customores:hbs_legs
        amount: 1
    hbs_chest:
      enabled: true
      pattern:
      - BXB
      - BBB
      - BBB
      ingredients:
        B: customores:ihbs
      result:
        item: customores:hbs_chest
        amount: 1
    hbs_head:
      enabled: true
      pattern:
      - BBB
      - BXB
      - XXX
      ingredients:
        B: customores:ihbs
      result:
        item: customores:hbs_head
        amount: 1
    hbs_block:
      enabled: true
      pattern:
      - BBB
      - BBB
      - BBB
      ingredients:
        B: customores:ihbs
      result:
        item: customores:hbs_block
        amount: 1
    ihbs:
      enabled: true
      pattern:
      - XXX
      - XBX
      - XXX
      ingredients:
        B: customores:hbs_block
      result:
        item: customores:ihbs
        amount: 9
```

iareload

iazip

<figure><img src="../../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

至此，我们的工作已经完成了95%
