﻿访问 [Release 页面](https://github.com/Ludoux/LRCHelper/releases) 来获得最新的发布版本，或者手动编译代码尝鲜（但通常二进制文件与源代码所对应）

-----

**运行要 .NET Framework 4.6.2 的支持**

针对网易云音乐开发，根据提供的歌曲/歌单/专辑 ID，自动下载整理歌词（含翻译）的功能，顺便为  SONY®WALKMAN® 设计了翻译延迟 1 秒的功能。

## 写在前面

学习目的~~~///(^v^)\\\~~~

## Screenshots

![LrcDownloader](https://raw.githubusercontent.com/Ludoux/LrcHelper/master/Pic/LrcDownloader.png)

## 具体操作方法（Release 版本）

（目前版本去除了手动模式，若有需要烦请 Release 页面下载 Pre-release 的 v0.0.0-beta 版本）。

在 AUTO-SET 功能（默认）开启时，可以直接复制其对应的链接（ex https://music.163.com/#/song?id=461332109 ），软件在切入前台时会自动填充，

或者手动输入对应的 ID 号并选择 ID 所对应的含义（Music/Playlist/Album）

提供了高级设置（AdvancedSettings），勾选了单选框后便可以进行设置调整。

然后点击按钮“GET”。

1. 若为是音乐 ID，.lrc 文件（UTF-8）会在软件所处目录下生成，结束时会在 Status 处显示详情。
2. 若为是歌单/专辑 ID，.lrc 文件（UTF-8）会在软件所处目录的以歌单名命名的文件夹中生成，结束时会在 Status 处显示详情，更具体信息请查看生成的 Log.txt 文件。

## Tips

1. 翻译比外文歌词默认慢一秒，可以在高级设置中更改。
2. 目前歌词歌单仅支持网易云。在很久远的未来会以附加组件的方式进行弥补。

## Known Bugs

1. 稳定性。

## TODO


1. 增加歌曲信息，歌词信息等，Tag 更多方法。
2. 写其它的歌词文件处理方法。
3. 继续封装，完善代码安全性和可维护性。

## License

在 MIT 协议下发布。

## 参考&感谢:

获取外文歌词的代码基于 ituff 的 [163lyric项目](https://github.com/ituff/163lyric) 的实现，进行了修改。（但是 ituff 并没有指定那个项目的开源协议）

感谢 Moonlib.com 的所有人 Moon 在这个博客上发表了 [自己整理的API](http://moonlib.com/606.html) 。

## 更新信息（最近在上）

* 2017.8.8  允许多个 tag 值。（v1.0.8 #Release）
* 2017.8.6  增加了 FilenamePattern 功能，背后是重新实现了写文本文件的逻辑，还有对网易云音乐上歌曲歌手专辑等的获取；各种大大小小的优化。
* 2017.7.12 优化了下代码，使用枚举。（v1.0.7 #Release）
* 2017.7.11 修 bugs；更改了新的功能（case 1）中部分符号的大小（倍率？），增加了新的符号；更改了关键函数的实现，部分更改为属性；写了点注释。
* 2017.7.10 新的功能正式提供了，可以在高级设置中启用（填 1）；高级设置也支持调整延时。（v1.0.6 #Release）
* 2017.7.6  或许支持了新的翻译歌词显示形式：尽可能地同屏显示原文和翻译。
* 2017.6.7  （v1.0.5 #Release）
* 2017.6.5  功能增加：支持了直接从专辑（album）链接下载歌词，不用再保存为歌单。近一个月的时间在修 bug：tag 采用白名单模式，不符合的 pass 掉以免进入时轴处理。对并行处理有了错误捕获。采用 https 链接。使用 int64 存储 ID 因为测试时遇到了长 ID 直接爆掉……（#Weekly）
* 2017.5.1  支持 offset ，稳定性提升。（#Weekly）（v1.0.4 #Release）
* 2017.4.29 软件支持检查更新，修上次更新出现的 bug ，升级框架到4.6.2。（#Weekly）（v1.0.3 #Release）
* 2017.4.14 修 Bug，清理无用代码。支持同行多个时间轴，支持排序。（#Weekly）
* 2017.4.2  日常修 bug，Json.NET 升为 10.0.2，更改核心代码，将时间轴以 int 方式存储方便以后排序，更改了翻译延时处理的方法，清理了原本的过时的时轴规范方法。（换用最新的 Visual Studio 2017 而且升级过程异常顺利）（#Weekly）
* 2017.3.12 可以取消（Cancel）操作了（#Weekly）（v1.0.2 #Release）
* 2017.3.11 更改了核心代码——允许空白歌词（含翻译）存在，对翻译处理更大度，更改了对于翻译是否存在的实现，修复了一个经常发生关于延迟修复的bug。注意 cancel 仍有问题。（#Weekly）
* 2017.2.17 删除一无用方法，进入代码优化阶段。（#Weekly）
* 2017.2.12 新增了 Auto-Set 功能，使用更方便。（#Weekly）
* 2017.2.5  允许取消操作，有 BUG，使用 Task 实现 UI 和下载线程分离，修复 LICENSE 编码错误，不稳定的代码版本。
* 2017.2.4  使用了 TPL 类库实现了并行循环下载 @Playlist 模式，速度较原先提高了（效果因设备而异）；优化代码，Fix Bugs。（v1.0.1 #Release）
* 2017.1.25 粗略的代码重构，重写了实现。未广泛测试。（v1.0.0 #Release）
* 2016.9.2  Fix Bugs。（v0.0.0-beta #Release）
* 2016.8.30 Log 文件内容实现对齐，AUTO 实现执行线程与 UI 线程分离，可实时看进度与错误数。
* 2016.8.29 初版。