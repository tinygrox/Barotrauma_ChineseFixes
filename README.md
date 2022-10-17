# Barotrauma Chinese Fixes

# 📃简介

该项目为游戏[**潜渊症**](https://store.steampowered.com/app/602960/Barotrauma/)的汉化修正 Mod。Mod 以原始官方简中为基础，调整了大部分的词汇翻译

虽然有了官中，但仍然有部分地方不如人意，目前官中文本已部分落后于原版，有些文本甚至还带有误导，缺少了翻译前后一致性。

本Mod旨在对官中的一些修正。

注：本项目为“修正” mod，不会修改、覆盖原版中文翻译内容，不会存在文本闪烁问题，此 mod 在方法实现上是以一个独立的新的语言包存在，所以，打上 mod 后现存的任何其他原有中文翻译的 mod 均会失效。

**仍然在开发中...**

# 🔧下载安装

**对于能正常打开创意工坊的用户**

* 在创意工坊页面直接点击订阅

**对于不能正常打开创意工坊的用户**

* 进入本页面，下载提示的文件
* 然后将下载的文件解压至游戏目录下的 `LocalMods` 文件夹内

# 📗使用

* 无论哪种用户首先进入设置-模组然后将右侧的`Chinese Fix`移动至左侧，点击应用
* 然后在语言设置中下拉选择`中文（简体）[修正]`，然后再应用一遍
* 最好重启一遍游戏

# 📕问题提交

如遇到任何问题，请在创意工坊页面下留言回复或在 github 新开一个 Issues：

问题一般格式如下：

> 问题描述：如【Mod 无法使用】
>
> 复现过程：如【在创意工坊中订阅后，进游戏中启用并点击应用，此时游戏弹出控制台信息，红字“xxxx”】

规范问题格式只是方便我去复现问题，节约大家时间。

# 💪参与贡献

本项目欢迎各位积极参与翻译、润色或是校对。

参与贡献一般流程可参考 [GitHub官方文档 - 快速入门 - 参与项目](https://docs.github.com/cn/get-started/quickstart/contributing-to-projects)，对于Windows用户，不想打 git 命令打到发疯可以尝试使用 GitHub Desktop。

在 Pull Request 时请选择提交到分支 （*branch*）**"dev"**下

# :pushpin:已知问题

**问题1：** 安装此 mod 会导致其他 mod 的现存中文翻译失效

**解决办法1**：

因为此 mod 对游戏来说相当于是新的语言包，语言名称为我设置的【Simplified Chinese Fixes】，在xml文件中定义为`<infotexts language="Simplified Chinese Fixes" ...>`，而不是原官中的`language="Simplified Chinese"`，而现存支持中文翻译的 mod 中，在xml的翻译中都是`<infotexts language="Simplified Chinese">`，故会失效。所以解决办法如下：

---

**对于 mod 作者来说**，只需复制原有的中文翻译文件，然后把

```xml
<infotexts language="Simplified Chinese" nowhitespace="true" translatedname="中文(简体)">
```

改成

```xml
<infotexts language="Simplified Chinese Fixes" nowhitespace="true" translatedname="中文(简体)[修正]">
```

然后相应的在`filelist.xml`中加入刚才新加的文件即可。

---

**对于普通玩家**来说，大致有 2 条路可走：

**第一条**，可以跑去给 mod 作者留言，申请他添加支持，不过这种要看别人心情了，还可能要等到猴年马月。

**第二条**，可以自己手动做一个mod，方法很简单，首先进入游戏根目录下的`LocalMods`文件夹，新建一个文件夹，名称随意，建议英文。

进入到新建的文件夹内，新建 2 个文件，一个是翻译文件，这个可以复制你玩的 mod 里的中文翻译，复制到你的，跟上面的步骤一样。

用文本编辑器（推荐使用微软的VS Code，而不是系统自带的记事本）打开文件内容改成类似这样

```xml
<?xml version="1.0" encoding="utf-8"?>
<infotexts language="Simplified Chinese Fixes" nowhitespace="true" translatedname="中文(简体)[修正]">
    ...
</infotexts>
```

另一个文件名为`filelist.xml`，里面这样写

```xml
<?xml version="1.0" encoding="utf-8"?>
<contentpackage name="你的 mod 名称" modversion="1.0.1" corepackage="False">
  <Text file="%ModDir%/【你的翻译文件名】.xml" />
   <!--如果后续要支持多个 mod，记得添加所有的翻译文件-->
</contentpackage>
```

然后就在游戏里看到了你自己的 “翻译” mod，启用即可。推荐。

# 📜许可证

* TBD

