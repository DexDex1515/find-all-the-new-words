# find-all-the-new-words

[![GitHub issues](https://img.shields.io/github/issues/Steven-AA/find-all-the-new-words.svg)](https://github.com/Steven-AA/find-all-the-new-words/issues)  [![GitHub forks](https://img.shields.io/github/forks/Steven-AA/find-all-the-new-words.svg)](https://github.com/Steven-AA/find-all-the-new-words/network)  [![GitHub stars](https://img.shields.io/github/stars/Steven-AA/find-all-the-new-words.svg)](https://github.com/Steven-AA/find-all-the-new-words/stargazers)  [![GitHub license](https://img.shields.io/github/license/Steven-AA/find-all-the-new-words.svg)](https://github.com/Steven-AA/find-all-the-new-words/blob/master/LICENSE) [![codecov](https://codecov.io/gh/Steven-AA/find-all-the-new-words/branch/master/graph/badge.svg)](https://codecov.io/gh/Steven-AA/find-all-the-new-words)  [![GitHub All Releases](https://img.shields.io/github/downloads/Steven-AA/find-all-the-new-words/total.svg)](https://github.com/Steven-AA/find-all-the-new-words)

- 找出文章中的生词（配合anki使用）
- 示例 [先背生词，再看文章 FAIDK v1.0.0](https://zhuanlan.zhihu.com/p/25003457)

## 提醒

`pyinstaller`目前并不完善，对NLTK的支持有些问题（见[stackoverflow](https://stackoverflow.com/questions/53058052/unable-to-find-c-nltk-data-while-creating-executable-using-pyinstaller)、[#2159](https://github.com/nltk/nltk/issues/2159)), logger也无法正常地读取配置文件。总之对我来说打包体验极差，我已经在这上面浪费了较多的时间，所以**打包exe无限期搁置**，请尝试安装`python`来使用这个工具。如果需要帮助可以加群询问。~~寒假期间我尽量出一个详尽的安装教程。~~

## 依赖

- Python3.6

## 交流

- 维护一个文档，对于文档有任何的问题或建议欢迎通过下方Q群或issue或邮件联系我。TODO
- 维护一个QQ群，737389550

<div align=center><img src="https://i.loli.net/2018/09/29/5baedf2a2bd6d.jpg" width = "100"/></div>

## 已知bug

- [ ] ~~exe 2.1.0后打包~~
- [ ] `config` 和`new.txt`相关的命令行参数暂不可用
- [x] 各种特殊的、奇怪的、错误的标点被剔除后，本应分开的两个单词被合并了，比如`before us：that from`会被分成`before`、`usthat`、`from`。
- [x] 中途手动退出后，本次学习保存的新单词内容错误
  - ~~临时解决方案：将`new.txt`放入`article`文件夹中，运行find模式代码~~

## 最近的更新

- 修复了`中途手动退出后，本次学习保存的新单词内容错误`的bug
- 对单词列表进行了排序
- 修复`q`只能退出一个文件的bug
- 自定义按键
- 自定义config路径
- 手动退出
- 修复`getch`无法跨平台问题
- 增加`pytest`并连接`CodeCov`
- 修复`new.txt`反复覆盖的bug
- ……

## 即将到来的新 Feature 预告

**说明**:中断恢复、过多生词自动切割这两个功能其实都是为了解决中途退出保存进度的问题，因此准备中途手动退出保存来解决这些问题

**说明**:有一些新的想法,为了节约时间，`多config选择`不做开发了，可以通过每一个文件夹里面都放一份程序来实现。`自定义config路径`功能暂时保留，用来实现多个文件夹共用一个config。

### 2.1.*

- [ ] 输出含有新单词的句子
- [ ] 输出标注后的文章
- [ ] 查询本地词典
- [ ] 生成可直接导入 Anki 的文件（即不再通过`英语单词制卡工具`）
- [ ] 自定义输出文件模板

## 使用

- 把文章放在 `./article` 文件夹中
- build 模式用来建立自己的词汇库，即 `old.txt`，同时也可以将新单词列出来，建议建立的时候挑选较短的文章，一篇一篇来
- 词库建立好了就可以使用 `find` 模式批量查找生词
  
## exe文件

- exe文件 release 里面
- 解压后 ，快捷方式需要你自己重新创建
- 如果还需要帮助，你可以参考上面给的示例

## 关于anki

- [Anki——近乎完美的神器](https://zhuanlan.zhihu.com/-anki)

## 更新

### 2019年07月??日 2.2.0

- ~~通过命令行指定文件~~
- 输出标记过的文章

### 2019年04月26日 2.1.1

- 修复了`中途手动退出后，本次学习保存的新单词内容错误`的bug
- 对单词列表进行了排序

### 2018年11月26日 2.1.0

- 修复`q`只能退出一个文件的bug
- 自定义按键
- 自定义config路径

### 2018年11月22日 2.0.5

- 手动退出
- 修复`getch`无法跨平台问题
- 增加budge
- 增加`pytest`并连接`CodeCov`
- 更正所有`FAIDN`为`FAIDK`:D
- ~~修复部分python3版本没有`decode`的问题~~(`linux`平台下`getch`返回值为`str`，因此没有`decode`)

### 2018年11月16日 2.0.4

- 修复`new.txt`反复覆盖的bug
- 增加上一次运行时的生成的`new.txt`是否保留的选择
- 修复`articles`中的文件没有自动移动到`old_articles`的bug

### 2018年10月10日 2.0.3

- 使用`logging`替代`print`
- 增加`/log/FAIDN.log`文件

### 2018年09月30日 2.0.2

- 词形还原，提供四种模式，修改`FAIDN.config`中的`LEMMATIZATION_MODE`来修改模式，目前支持四种模式。这里需要感谢[@ninja33](https://github.com/ninja33)
  - `None`不做处理
  - `list`使用字典映射来词形还原。字典来自[这里](https://github.com/michmech/lemmatization-lists/blob/master/lemmatization-en.txt)，里面共有条41760词条，如果文章中的单词不在此字典中，保持原样
  - `NLTK`
  - `both`先使用字典，后使用`NLTK`

### 2018年09月28日 2.0.1

- 重构代码，我也不知道是重构好了还是重构差了。。。
- 鸽了一个暑假，接下来更新可能稳定一点
- 这个版本我只做了简单测试，所以记得备份自己的`old.txt`，其他应该不会造成什么损失
- 维护一个QQ群，万一有人用呢，也满足一下我的虚荣心，更新可能快点。737389550

<div align=center><img src="https://i.loli.net/2018/09/29/5baedf2a2bd6d.jpg" width = "100"/></div>

### 2018年05月16日 1.0.1

- 删除了pattern 的词形还原
- 修复了一个文件命名错误导致把`old.txt`覆盖了的bug，它把我的词库弄没了。我希望没有给你们带来什么损失，毕竟并没有人来报bug。

### 2018年03月14日 1.0.0

- 添加 v1.0.0 release
- 添加 json indent

### 2018年03月14日 0.2.3

- 增加 `FAIDN.config`, 支持自定义目录

### 2018年02月27日 0.2.2

- 从 python 2.7 更新到 python 3.6
- 增加词形还原功能

### 2017年04月08日 0.2.1

- 修复old.txt文件没有单词的bug
- 修复build 模式输入2会报错的bug

### 2017年03月07日 0.2.0

- 省略回车，节省时间
- 按照pylint规范化代码
- 添加0.2.0的exe程序
- 修复.py与exe不同的路径情况（用于生成exe的Python文件已放入压缩包）
