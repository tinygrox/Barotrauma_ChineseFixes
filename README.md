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

**问题1：** 安装此 mod 会导致其他 mod 的中文翻译失效

**解决办法**：

因为此 mod 为一个独立语言包，对游戏来说相当于是新的语种，该语种名称为我设置的【CHS2】，而现存 mod 支持的中文翻译，其语种名称为【Simplified Chinese】而不是【CHS2】，故失效

1. 找到 mod 的中文翻译文件，复制一份，将文件名改成任意，打开复制的文件，找到在最上面的`<infotexts language="Simplified Chinese" nowhitespace="true" translatedname="中文(简体)">`将`language="Simplified Chinese"`改成`language="CHS2"`，然后保存。
2. 在 mod 的filelist.xml文件中添加一行`<Text file="【mod的路径】/【你刚刚修改的文件名】.xml" />`
3. 重启游戏

# 📜许可证

* TBD

