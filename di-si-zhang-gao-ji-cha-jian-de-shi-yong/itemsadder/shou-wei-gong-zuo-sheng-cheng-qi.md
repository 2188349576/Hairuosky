---
description: 收尾工作-生成器
---

# 收尾工作-生成器

矿石 总是要在世界里生成的，对吧。

接下来，打开populators.yml

熟悉的仿制工作

```
info:
  namespace: customores
worlds_populators:
  zbs:
    block: customores:zbs
    worlds:
    - world
    - normal
    - test
    replaceable_blocks:
    - STONE
    chunk_chance: 100.0
    max_height: 30
    min_height: 10
    vein_blocks: 4
    chunk_veins: 4
  hbs:
    block: customores:hbs //方块ID
    worlds:  //能够生成的世界，test和normal是测试是否正常的世界
    //毕竟不可能在world里搞
    - world
    - normal
    - test
    replaceable_blocks: //代替的方块，也就是说他会代替部分的石头方块，不建议修改
    - STONE
    chunk_chance: 80.0  //在一个区块中出现的概率。如果不是特别稀有建议100
    max_height: 30  //生成的最高高度
    min_height: 10  //生成的最低高度
    vein_blocks: 4  //每个矿脉的最多个数
    chunk_veins: 4  //一个区块中有多少矿脉
```

iareload

iazip

然后去一个从来没有被加载的区块

<figure><img src="../../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

至此，我们的使用已经完成了，so

快去添加更多矿石罢！

注意命名规范！注意命名规范！注意命名规范！注意命名规范！注意命名规范！注意命名规范！注意命名规范！注意命名规范！注意命名规范！注意命名规范！注意命名规范！注意命名规范！注意命名规范！

最好和教程命名格式一致，这样维护会很快；最好和教程命名格式一致，这样维护会很快；最好和教程命名格式一致，这样维护会很快；最好和教程命名格式一致，这样维护会很快；最好和教程命名格式一致，这样维护会很快；最好和教程命名格式一致，这样维护会很快；最好和教程命名格式一致，这样维护会很快；最好和教程命名格式一致，这样维护会很快；
