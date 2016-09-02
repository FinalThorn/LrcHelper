# 简介
**然后去看Tips**

**运行要.NET Framework4.5.2的支持**

针对网易云音乐开发，根据提供的歌曲ID或**歌单ID**是的自动下载整理歌词**包括翻译**的功能，顺面为Walkman设计了翻译延迟1秒的功能。

**支持批量下载歌单内的歌曲的歌词包括翻译！！**

**支持批量下载歌单内的歌曲的歌词包括翻译！！**

**支持批量下载歌单内的歌曲的歌词包括翻译！！**

**支持批量下载歌单内的歌曲的歌词包括翻译！！**

**支持批量下载歌单内的歌曲的歌词包括翻译！！**

**支持批量下载歌单内的歌曲的歌词包括翻译！！**

**支持批量下载歌单内的歌曲的歌词包括翻译！！**

**支持批量下载歌单内的歌曲的歌词包括翻译！！**

**支持批量下载歌单内的歌曲的歌词包括翻译！！**

**支持批量下载歌单内的歌曲的歌词包括翻译！！**

## 具体操作方法(严谨向)

-----
* **完全手动或半自动操作**

完全手动操作以及半自动操作*仅* 对外文歌词且有本地语言翻译的情况有使用意义。

基于以上前提，在以下几个情况下才需要进行完全手动操作
1. 无法自动操作(Log报错)
2. 软件无法连接到网络但是有可用的歌词翻译时间轴等信息
3. 任性

界面两个大的文本框里面的讲解是针对完全手动或半自动的。对于输入文本的换行符等均有要求。


例子:

完全手动第一步

在左边的文本框内输入"今夜...我〗"，这个可以从网易云音乐(或其他)的网页版内复制所得。然后点击按钮"手动第1步"。


*(注意*
*1. 文本头尾不能有换行符，且文本的换行符应为\r\n 通过按钮"修正"可能能解决部分问题*
*2. 文本不能有空行，省略号等与歌词无关的内容，需要确保一行外文歌词一行本地翻译)*

半自动第一步

在左上部分"AUTO"中点击"音乐ID"，然后输入音乐ID并勾上半自动获取目标音乐的外文歌词，点击按钮"GET!"它将会填充到右边的文本框中。


第二步

在右边的文本框内输入"[00...てね"，这个可以通过像163Lyric等软件获得，**若是半自动操作那么软件应该已经填写完毕，仅需进行格式调整，格式同上1**。然后点击按钮"手动第2步"。


结束

此时右边的文本框应已经有了结果，可以复制到lrc文件中。


-----
* **自动操作**
* 
自动操作可以对付大多数情景，这应该是首选的操作方法。注意，这是对网易云音乐开发的。使用的是网易云音乐的API

在左上部分"AUTO"在选择音乐ID或歌单ID并输入对应的ID号，然后点击按钮"GET!"。

1. 若选择的是音乐ID，lrc文件(UTF-8)会在软件所处目录下生成，出现错误提示会生成log文件请进行半自动操作。
2. 若选择的是歌单ID，lrc文件(UTF-8)会在软件所处目录的以歌单名命名的文件夹中生成。无论成功与否均有log生成。若出现错误可查看log以确定具体音乐信息进行半自动操作。
-----
## Tips:

1. 本地翻译比外文歌词慢一秒。因为我是给Walkman输歌，Walkman不能正常显示两个相同时间的歌词。方法的参数中好像可以修改延迟时长DelaySec但并不可以。写死在里面了，要修改ArrangeLyricAndTranslation里具体的实现来更改延迟时长
2. 软件提示文白间杂，中英具备，就是不讲语法。会意即可无需深究。
3. 操作是在主线程上所以界面假死，可以看Log或者文件数目来看进度。
4. 自动是从网易云音乐上的。整个软件是为网易云设计的。
5. 除了长得丑易出错难维护不好用外**没别的缺点了**
6. **最重要:编译要Json90r1的支持(引用了Newtonsoft.Json),dll是Net45版本。运行要.NET Framework4.5.2的支持**
## TO DO:
(很难lan实现的功能)

1. 更改UI
2. 代码重构：让代码结构更加严谨，希望就一个歌单操作下再分名称和所含音乐ID，音乐操作下再分名称和歌词，歌词再分歌词和翻译。
3. 多线程同时下载但好像实现意义不大
4. 正则再优化下，肯定很多诡异的情况下触发的Bug

## License:

在[MIT 协议](https://mit-license.org/)下发布.

## 参考&感谢:

获取外文歌词的代码基于ituff的[163lyric项目](https://github.com/ituff/163lyric)的实现，进行了修改。(但是ituff并没有指定那个项目的开源协议)

感谢Monnlib.com的所有人Moon在这个博客上发表了[自己整理的API](http://moonlib.com/606.html)。

## 更新信息(最近在上)

* 2016.9.2 Fix Bugs
* 2016.8.30 Log文件内容实现对齐，AUTO实现执行线程与UI线程分离，可实时看进度与错误数
* 2016.8.29 初版