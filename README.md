# LaTeX-Package: choice
Package: LaTeX package for flexibly LaTeXing choice based on hlist and LaTeX3.
Author: Kangwei Xia <kangweixia_xdyy@163.com>
Repository: https://github.com/xkwxdyy/choice
License: The LaTeX Project Public License 1.3

## 宏包编写背景
### 已经存在选择题的选项排版命令，但是有一些不足
  已经存在用[`ifthen`宏包](https://www.latexstudio.net/index/details/index/mid/2270.html)或者用[`xcoffins`宏包](https://www.latexstudio.net/index/details/index/mid/2191.html)写的相关选项命令，用于排版试卷中的选择题，比如`\xx{<arg1>}{<arg2>}{<arg3>}{<arg4>}`，但是有几个不足
  - 这样定义的命令只能且必须接受四个参数
    - 如果少于四个，那么就会有空白项，但是label依旧存在，比如`D.␣␣`
    - 多于四个固然可以用同理的方式再定义相应的命令，但是除了试卷排版，问卷排版也是一种需求，问卷的选项个数变化很大，那么要预先建立很多个命令才行，而且通常的LaTeX命令参数最多有9个，如果有更多的需求怎么办呢？所以希望存在一个相同接口的命令，可以排版任意个选项.
  - 从代码角度看，已有命令的代码并不简洁，希望可以进行优化
  - 已有的代码并没有解决label样式（arabic, roman等）切换问题，ABCD往往是手动输入封装成命令.
### 选项中如果要插图的一般做法是结合表格，但是那样的命令使用不够统一，格式和内容的分离性不好
  如果选项中有图片，已有的一种做法是手动加入表格，并且label也是手动输入. 虽然整体可以进行命令的封装成新的命令，但是上述参数个数、label样式等问题也同样存在，所以更希望的是有一种命令可以实现统一，使得用户更多关注在内容本身，契合LaTeX的内容与样式分离的想法.

## 宏包使用说明以及命令设计思路
  宏包定义主要的命令是`\choice(*)[<key-val>]{args}`，副命令有
  - `\coffinchoice[<key-val>]{args}`（基于coffin的choice排版命令）
  - `\hlistchoice[<key-val>]{args}`（基于hlist环境的排版命令）
  - `\quan{<number>}`（带圈数字）.
  
  其中`\choice(*)[<key-val>]{args}`其实是用`xparse`宏包的`NewDocumentCommand`将`\coffinchoice[<key-val>]{args}`与`\hlistchoice[<key-val>]{args}`进行统一封装：
  - `\choice[<key-val>]{args}`表示使用`\hlistchoice[<key-val>]{args}`排版
  - `\choice(*)[<key-val>]{args}`表示使用`\coffinchoice[<key-val>]{args}`排版.

### 如何使用命令
  三个副命令可以单独使用，带圈数字是基于`tikz`画的（个人觉得还是蛮不错的:) 源代码在宏包里，用户也可以自己修改成自己想要的效果）
  `\choice(*)[<key-val>]{args}`中的`{args}`不同选项用`&&`分隔开，如
  ```latex
  \choice[label-style = roman]{
    test1 &&
    test2 &&
    test3 
  }
  ```
  或者
  ```latex
  \choice*[label-style = quan, anchor = south]{
    test1 &&
    test2 &&
    test3 &&
  }
  ```
  （注：作者对输入的数据做了过滤，对后者以`&&`结尾的原本会多产生一个选项，但是经过处理后会自动删除，所以用户不用担心. 但是要注意不能使用单独的`&`（系统会报错，其实也不用我提醒：））
  如果选项里需要显示`&`的话需要使用`\&`，经测试命令不会“误伤”. (本一开始选择`&`作为分隔符，但是如果选项中使用`align`或`align*`等环境，如果里面也使用了`&`的话就会报错，最终修改为`&&`，经过测试也能正常使用`align`等可能出现`&`的环境.)

### 命令的功能
  - 可以输入任意多的选项，只需要在一个`{}`中用`&&`进行“切割”即可
  - 

### 命令的<key-val>
  - label-style: 修改label的样式，一共有下面几种
    - arabic(阿拉伯数字)
    - alph(小写英文字母)
    - Alph(大写英文字母)
    - roman(小写罗马数字)
    - Roman(大写罗马数字)
    - quan(带圈数字)

## 宏包使用例子
详见`choice_example.tex`文件（需要同时下载`chocie.sty`并放在同一目录下）

## License

The LaTeX package and Lua library are released under MIT license.
The CSL locale files and styles are redistributed under the [Creative Commons Attribution-ShareAlike 3.0 Unported license](https://creativecommons.org/licenses/by-sa/3.0/).
