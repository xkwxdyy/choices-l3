# LaTeX-Package: choice

Package: LaTeX package for flexibly LaTeXing choice items based on hlist and LaTeX3.

Author: Kangwei Xia <kangweixia_xdyy@163.com>

Repository: https://github.com/xkwxdyy/choice

License: The LaTeX Project Public License 1.3

## 宏包说明

  `choice`宏包是一个用于排版选项的宏包, 包含但不限于以下特点：
	- 可以排版任意数量的选项
	- 可以方便切换标签风格`label-style`
	- 可以更改标签`label`与内容的相对位置
	- 可以调整标签`label`的偏移
	- 自动识别是否使用 `includegraphics` 命令并自行调整 `anchor` 的位置（仅 `choice*` 有此功能,  之所以会有 `choice*` 命令, 就是因为基于 `hlist` 环境的 `choice` 只有一个方位, 无法更改, 所以需要用另外的方法处理（ `choice*` 是用 `coffin` 进行处理））.
		**此功能的实现需要将 `expl3` 宏包更新至最新（至少是2021-11-12后）, 否则可能无法使用且会报错.**

  在需要排版选项的情况中（比如试卷、问卷排版等）`choice`宏包可以发挥重要作用, 旨在让用户更多关注在内容本身, 契合LaTeX的内容与样式分离的思想. 

  `choice`宏包是基于`hlist`环境与LaTeX3开发的LaTeX宏包, 它提供了`choice(*)` 两个主命令与`coffinchoice`、`hlistchoice`和`quan`三个副命令. 
`choice`和`choice*`是利用了`xparse`宏包对`hlistchoice`与`coffinchoice`命令进行封装. 其中`choice`等效于`hlistchoice`, `choice`等效于`coffinchoice`. 

  通常情况下使用 `choice` 命令就够了, 但是用户如果有排版图片的需求, 可能需要将 `label` 置于内容的上方或下方, 而 `choice` 命令基于 `hlist` 环境编写, 所以`label` 只能置于内容的左侧, 这个时候只需要使用`choice*`, 会自动更改`anchor`为`south`, 如果需要修改自动的`anchor`为其它的方位可以使用`\choicesetup{autopic = north}` .

更多宏包细节与命令欢迎阅读宏包手册`choice_usrmanual.pdf`
