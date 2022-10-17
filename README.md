# Barotrauma Chinese Fixes

# 📃简介

该项目为游戏[**潜渊症**](https://store.steampowered.com/app/602960/Barotrauma/)的官方简体中文翻译修正 Mod。以原始官方简中为基础，调整了大部分的词汇翻译。

动机：虽然游戏自带官中，但仍然有部分地方不如人意，不可否认有些地方翻译的蛮好的，但目前我对比了一遍英文的原始词条，发现官中的文本已部分落后于原版，有些文本甚至还带有误导（如有个任务叫你潜入深渊拿雷素棒，多了一个[resourcename2]），只是看着难受而已。

注：本项目为独立的**修正** mod，不是修改、覆盖原版中文翻译的内容，所以不会存在文本闪烁问题，此 mod 在方法实现上是以一个独立的新的语言包存在，所以，打上 mod 后现存的**自带中文翻译的 mod 均会失效**。

目前翻译修正范围：

1. 游戏主体界面（对应文件`Texts/SimplifiedChineseVanilla.xml`）
2. 编辑器界面（对应文件`Texts/SimplifiedChineseVanillaEditorTexts.xml`）
3. NPC左下角聊天对话（对应文件`Texts/NpcConversations_SimplifiedChinese.xml`）

**仍然在努力中...**

# 🔧下载安装

**对于能正常打开创意工坊的用户**

* 在创意工坊页面直接点击订阅

**对于不能正常打开创意工坊的用户**

* 进入本页面，下载提示的文件
* 然后将下载的文件解压至游戏目录下的 `LocalMods` 文件夹内

# 📗使用

* 无论哪种用户首先进入 **设置** - **模组**然后将右侧的`Simplified Chinese Fixes`移动至左侧，点击应用。
* 重启游戏。
* 然后在语言设置中下拉选择`中文（简体）[修正]`，然后应用。

图文在这里：[链接](./lnstallation_guide.md)

# 📕问题提交

如在使用该 mod 的情况下遇到任何问题，请在创意工坊页面下留言回复或在 GitHub 新开一个 Issues，本项目同时也开通了讨论板块，在GitHub页面上方找到Discussions，参与讨论吧。

问题一般格式如下：

> 问题描述：如【Mod 无法使用】
>
> 复现过程：如【在创意工坊中订阅后，进游戏中启用并点击应用，此时游戏弹出控制台信息，红字“xxxx”】

规范问题格式只是方便我去复现问题，节约大家时间。

# 💪参与贡献

本项目欢迎各位积极参与翻译、润色或是校对。

参与贡献一般流程可参考 [GitHub官方文档 - 快速入门 - 参与项目](https://docs.github.com/cn/get-started/quickstart/contributing-to-projects)，对于Windows用户，不想打 git 命令打到发疯可以尝试使用 GitHub Desktop。

在 Pull Request 时请选择提交到分支（branch）名为 **dev** 的分支

# :pushpin:已知问题

**问题1：** 安装此 mod 会导致其他 mod 的现存中文翻译失效

**解决办法**：

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

**第一条**，可以跑去给 mod 作者留言，申请他添加支持。

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

* 本项目遵循 [GPL3.0协议](LICENSE)。

