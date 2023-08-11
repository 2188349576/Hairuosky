---
description: 最应该掌握的技能
---

# ※Crash-Report分析

下面是一段crash-report的内容

实际上，在服务器分析中，我们应该选取最近一次的分析

```
---- Minecraft Crash Report ----
// But it works on my machine.

Time: 2023-08-05 23:42:37
Description: Exception in server tick loop

java.lang.IllegalStateException: Failed to initialize server
	at net.minecraft.server.MinecraftServer.m_130011_(MinecraftServer.java:853) ~[server-1.20.1-20230612.114412-srg.jar%23161!/:?] {re:classloading,pl:accesstransformer:B}
	at net.minecraft.server.MinecraftServer.m_206580_(MinecraftServer.java:280) ~[server-1.20.1-20230612.114412-srg.jar%23161!/:?] {re:classloading,pl:accesstransformer:B}
	at java.lang.Thread.run(Unknown Source) [?:?] {}


A detailed walkthrough of the error, its code path and all known details is as follows:
---------------------------------------------------------------------------------------

-- System Details --
Details:
	Mohist Version: 1.20.1-283
	Minecraft Version: 1.20.1
	Minecraft Version ID: 1.20.1
	Operating System: Linux (amd64) version 5.15.0-78-generic
	Java Version: 17.0.7, Azul Systems, Inc.
	Java VM Version: OpenJDK 64-Bit Server VM (mixed mode, sharing), Azul Systems, Inc.
	Memory: 586090976 bytes (558 MiB) / 973078528 bytes (928 MiB) up to 16793993216 bytes (16016 MiB)
	CPUs: 8
	Processor Vendor: GenuineIntel
	Processor Name: 12th Gen Intel(R) Core(TM) i3-12100
	Identifier: Intel64 Family 6 Model 151 Stepping 5
	Microarchitecture: Alder Lake
	Frequency (GHz): 5.50
	Number of physical packages: 1
	Number of physical CPUs: 4
	Number of logical CPUs: 8
	Graphics card #0 name: Device
	Graphics card #0 vendor: Intel Corporation (0x8086)
	Graphics card #0 VRAM (MB): 256.00
	Graphics card #0 deviceId: 0x4692
	Graphics card #0 versionInfo: unknown
	Memory slot #0 capacity (MB): 32768.00
	Memory slot #0 clockSpeed (GHz): -0.00
	Memory slot #0 type: <OUT OF SPEC>
	Memory slot #1 capacity (MB): 32768.00
	Memory slot #1 clockSpeed (GHz): -0.00
	Memory slot #1 type: <OUT OF SPEC>
	Virtual memory max (MB): 39834.82
	Virtual memory used (MB): 31836.13
	Swap memory total (MB): 7813.00
	Swap memory used (MB): 4562.25
	JVM Flags: 0 total; 
	CraftBukkit Information: CraftServer is not running yet
	Server Running: true
	Data Packs: vanilla, mod:forge
	Enabled Feature Flags: minecraft:vanilla
	World Generation: Stable
	Is Modded: Definitely; Server brand changed to 'mohist'
	Type: Dedicated Server (map_server.txt)
	ModLauncher: 10.0.9+10.0.9+main.dcd20f30
	ModLauncher launch target: forgeserver
	ModLauncher naming: srg
	ModLauncher services: 
		mixin-0.8.5.jar mixin PLUGINSERVICE 
		eventbus-6.0.5.jar eventbus PLUGINSERVICE 
		fmlloader-1.20.1-47.1.62.jar slf4jfixer PLUGINSERVICE 
		fmlloader-1.20.1-47.1.62.jar object_holder_definalize PLUGINSERVICE 
		fmlloader-1.20.1-47.1.62.jar runtime_enum_extender PLUGINSERVICE 
		fmlloader-1.20.1-47.1.62.jar capability_token_subclass PLUGINSERVICE 
		accesstransformers-8.0.4.jar accesstransformer PLUGINSERVICE 
		fmlloader-1.20.1-47.1.62.jar runtimedistcleaner PLUGINSERVICE 
		modlauncher-10.0.9.jar mixin TRANSFORMATIONSERVICE 
		modlauncher-10.0.9.jar fml TRANSFORMATIONSERVICE 
	FML Language Providers: 
		minecraft@1.0
		lowcodefml@null
		javafml@null
	Mod List: 
		server-1.20.1-20230612.114412-srg.jar             |Minecraft                     |minecraft                     |1.20.1              |DONE      |Manifest: NOSIGNATURE
		forge-1.20.1-47.1.62-universal.jar                |Forge                         |forge                         |47.1.62             |DONE      |Manifest: NOSIGNATURE
	Crash Report UUID: 6d7f396c-0b4a-4aa2-974f-c2ae22b8cb16
	FML: 0.0
	Forge: net.minecraftforge:47.1.62
```

在上述错误报告中，一共分为两个大部分

接下来，我会将这两个部分分开讲



***

```
---- Minecraft Crash Report ----
// But it works on my machine.

Time: 2023-08-05 23:42:37
Description: Exception in server tick loop

java.lang.IllegalStateException: Failed to initialize server
	at net.minecraft.server.MinecraftServer.m_130011_(MinecraftServer.java:853) ~[server-1.20.1-20230612.114412-srg.jar%23161!/:?] {re:classloading,pl:accesstransformer:B}
	at net.minecraft.server.MinecraftServer.m_206580_(MinecraftServer.java:280) ~[server-1.20.1-20230612.114412-srg.jar%23161!/:?] {re:classloading,pl:accesstransformer:B}
	at java.lang.Thread.run(Unknown Source) [?:?] {}


A detailed walkthrough of the error, its code path and all known details is as follows:
---------------------------------------------------------------------------------------
```

上面是分析报错最常用的地方，我们在这里可以看到服务器发生了什么错误，在某些情况下还能看见为什么发生了上述错误。

这一堆代码中，最重要的仍然是Description部分的代码（如下）

```
Description: Exception in server tick loop

java.lang.IllegalStateException: Failed to initialize server
	at net.minecraft.server.MinecraftServer.m_130011_(MinecraftServer.java:853) ~[server-1.20.1-20230612.114412-srg.jar%23161!/:?] {re:classloading,pl:accesstransformer:B}
	at net.minecraft.server.MinecraftServer.m_206580_(MinecraftServer.java:280) ~[server-1.20.1-20230612.114412-srg.jar%23161!/:?] {re:classloading,pl:accesstransformer:B}
	at java.lang.Thread.run(Unknown Source) [?:?] {}
```

在这里，我们可以看到服务器发生了"Exception in server tick loop"的错误。

至于为什么会发生这个错误呢，请看下面

```
java.lang.IllegalStateException: Failed to initialize server
	at net.minecraft.server.MinecraftServer.m_130011_(MinecraftServer.java:853) ~[server-1.20.1-20230612.114412-srg.jar%23161!/:?] {re:classloading,pl:accesstransformer:B}
	at net.minecraft.server.MinecraftServer.m_206580_(MinecraftServer.java:280) ~[server-1.20.1-20230612.114412-srg.jar%23161!/:?] {re:classloading,pl:accesstransformer:B}
	at java.lang.Thread.run(Unknown Source) [?:?] {}
```

“java.lang.IllegalStateException: Failed to initialize server”中其实就告诉了我们发生了什么，翻译过来就是服务器初始化失败。

也就是说服务器启动失败。那启动失败了我们需要排查什么呢？

这就是第二部分出现的原因了

第二段代码中，我们可以看到

```
Mod List: 
	server-1.20.1-20230612.114412-srg.jar             |Minecraft                     |minecraft                     |1.20.1              |DONE      |Manifest: NOSIGNATURE
	forge-1.20.1-47.1.62-universal.jar                |Forge                         |forge                         |47.1.62             |DONE      |Manifest: NOSIGNATURE
```

正因为后方的Done字，证明了MOD是正常启动的。此时服务器并未使用任何插件。所以由于插件或MOD带来的启动失败就被排除了。

那么，我们就需要去考虑下面四个部分了

1. 依赖问题：服务器可能依赖于某些库、模组或资源文件，但这些依赖项不正确或缺失，导致初始化失败。
2. Minecraft版本不匹配：服务器可能正在尝试运行与其版本不匹配的Minecraft游戏版本，导致初始化失败。
3. 服务器资源不足：服务器可能由于系统资源不足，如内存、CPU等，导致初始化失败。
4. 服务器配置错误：可能在服务器配置文件（例如bukkit.yml、server.properties等）中存在错误或不兼容的设置，导致服务器初始化失败。

这时候，就要请出我们的另一个帮手了---logs文件夹！

***

我们需要在文件夹内选择与crash-report时间相似的日志文件，解压

<figure><img src="../../.gitbook/assets/image (3) (1).png" alt=""><figcaption><p>log.zip</p></figcaption></figure>

```
2023-08-05 23:41:41,759 [1;31mERROR[m [m[main][m [mn.m.s.Main.main(300)[m: Failed to start the minecraft server
net.minecraft.util.DirectoryLock$LockException: /Hairuosky/V12-1/./world/session.lock: already locked (possibly by other Minecraft instance?)
	at net.minecraft.util.DirectoryLock$LockException.m_13648_(DirectoryLock.java:95) ~[server-1.20.1-20230612.114412-srg.jar%23161!/:?]
	at net.minecraft.util.DirectoryLock.m_13640_(DirectoryLock.java:41) ~[server-1.20.1-20230612.114412-srg.jar%23161!/:?]
	at net.minecraft.world.level.storage.LevelStorageSource$LevelStorageAccess.<init>(LevelStorageSource.java:405) ~[server-1.20.1-20230612.114412-srg.jar%23161!/:?]
	at net.minecraft.world.level.storage.LevelStorageSource.m_289864_(LevelStorageSource.java:343) ~[server-1.20.1-20230612.114412-srg.jar%23161!/:?]
	at net.minecraft.server.Main.main(Main.java:192) ~[server-1.20.1-20230612.114412-srg.jar%23161!/:?]
	at jdk.internal.reflect.NativeMethodAccessorImpl.invoke0(Native Method) ~[?:?]
	at jdk.internal.reflect.NativeMethodAccessorImpl.invoke(Unknown Source) ~[?:?]
	at jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(Unknown Source) ~[?:?]
	at java.lang.reflect.Method.invoke(Unknown Source) ~[?:?]
	at net.minecraftforge.fml.loading.targets.CommonLaunchHandler.runTarget(CommonLaunchHandler.java:111) ~[fmlloader-1.20.1-47.1.62.jar%23155!/:?]
	at net.minecraftforge.fml.loading.targets.CommonLaunchHandler.serverService(CommonLaunchHandler.java:103) ~[fmlloader-1.20.1-47.1.62.jar%23155!/:?]
	at net.minecraftforge.fml.loading.targets.CommonServerLaunchHandler.lambda$makeService$0(CommonServerLaunchHandler.java:27) ~[fmlloader-1.20.1-47.1.62.jar%23155!/:?]
	at cpw.mods.modlauncher.LaunchServiceHandlerDecorator.launch(LaunchServiceHandlerDecorator.java:30) [modlauncher-10.0.9.jar%2385!/:?]
	at cpw.mods.modlauncher.LaunchServiceHandler.launch(LaunchServiceHandler.java:53) [modlauncher-10.0.9.jar%2385!/:?]
	at cpw.mods.modlauncher.LaunchServiceHandler.launch(LaunchServiceHandler.java:71) [modlauncher-10.0.9.jar%2385!/:?]
	at cpw.mods.modlauncher.Launcher.run(Launcher.java:108) [modlauncher-10.0.9.jar%2385!/:?]
	at cpw.mods.modlauncher.Launcher.main(Launcher.java:78) [modlauncher-10.0.9.jar%2385!/:?]
	at cpw.mods.modlauncher.BootstrapLaunchConsumer.accept(BootstrapLaunchConsumer.java:26) [modlauncher-10.0.9.jar%2385!/:?]
	at cpw.mods.modlauncher.BootstrapLaunchConsumer.accept(BootstrapLaunchConsumer.java:23) [modlauncher-10.0.9.jar%2385!/:?]
	at cpw.mods.bootstraplauncher.BootstrapLauncher.main(BootstrapLauncher.java:141) [bootstraplauncher-1.1.2.jar:?]
	at com.mohistmc.MohistMCStart.main(MohistMCStart.java:95) [mohist-1.20.1-283-server.jar:1.20.1-283]
```

此时，我已经删去了log中没用的部分，只留下了有用的部分

**“Failed to start the minecraft server"的出现也印证了我们的猜想，服务器启动时失败了**

继续往下看

“net.minecraft.util.DirectoryLock$LockException: /Hairuosky/V12-1/./world/session.lock: already locked (possibly by other Minecraft instance?)”

**已经告诉我们了答案。“possibly by other Minecraft instance”(或许被其他Minecraft实例占用)**

在此次服务器启动前，服务端其实已经卡死了。所以，面板的强制关闭其实已经失效了。

虽然我们在面板看到的服务器是关闭的，但实际上在服务端系统上，它还在运行（卡死）

所以，我们就需要转到SSH上链接服务器的系统，而不是在面板上继续操作。接下来，我们使用的就应该是Ubuntu带有的杀端口功能（强制杀死占有这个端口的程序）

此时，从server.properties中可以知道，这个服务端绑定的端口是30001，那么，一切都好办。

打开服务器的shell界面

<figure><img src="../../.gitbook/assets/image (4) (1).png" alt=""><figcaption><p>shell界面</p></figcaption></figure>

输入

```
lsof -i:30001
```

shell返回给我们

```
COMMAND     PID USER   FD   TYPE   DEVICE SIZE/OFF NODE NAME
java    3149930 root  326u  IPv4 11801448      0t0  TCP *:30001 (LISTEN)
```

此时，我们可以看到，这个端口上确实有程序在运行。那么我们只需要杀掉他

在shell界面继续输入

```
kill -9 3149930
```

重启服务器即可。

至此，服务器错误分析已经完成。

如果后续有更加典型的案例，我也会加在这里面。
