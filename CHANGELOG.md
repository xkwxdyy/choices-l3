# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]
- 预录入答案（福建南平文杰老师提出）
  - 打乱顺序也要有用
- 修改命令名为`\xchoices`

## [v3.2.3] - 2022-01-24
### Fixed
- 旧版本expl3的报错信息bug修复（[#2](https://github.com/xkwxdyy/choices-l3/issues/2)）

## [v3.2.2] - 2022-01-22
### Fixed
- 用`\use:c`优化不同的anchor设置命令

## [v3.2.1] - 2022-01-16
### Added
- 增加了svg宏包的`\includesvg`命令的识别

## [v3.2.0] - 2022-01-09
### Added
- 增加了未知选项的报错

### Changed
- 根据代码规范优化了部分键值的键名

## [v3.1.2] - 2021-12-31
### Fixed
- 修复join改为attach后出现的间距问题（重新改为attach并微调各个距离）

## [v3.1.1] - 2021-12-30
### Fixed
- 修复了anchor为south或north的垂直偏移量，使得选项尽可能居中

## [v3.1.0] - 2021-12-26
### Added
- 增加了行数的计算
- 加入了content_coffin的偏移量计算
- 用str方式增加anchor判断功能

### Fixed
- 优化了对齐效果
- 优化了插图与无图时的参数设置
- `choice`命令与`exam`文类的冲突问题

## [v3.0.0] - 2021-12-25
### Changed
- 修改命令名从`\choice(*)`为`\choices`
- 修改宏包名为`choices`

### Fixed
处理了与`exam`文类的冲突

## [v2.4.0] - 2021-12-25
### Added
- 增加了乱序功能，并通过randomitem键值控制

## [v2.3.1] - 2021-12-25
### Added
- 宏包中添加了引擎、宏包的版本判断
- 手册中补充了“需要更新`expl3`宏包”的说明
- 用户手册基本完工

## [v2.3.0] - 2021-12-24


### Added
- `prelabel`增加了同义键值: `pre-label`
- `poslabel`增加了同义键值: `pos-label`, `postlabel`, `post-label`
- 自动识别内容中是否有includegraphic，并自动调整anchor
- 增加了`autopic`键值，设置图片的默认排版anchor

### Changed
- `xshift`修改为`firstcolsep`的dim设置
- 原来的`yshift`修改为`belowsep`
- 用修改`topsep`的方式定义yshift

### Removed
- 去掉了`firstcolsep`等一系列同义键值


### Fixed
- 删除`coffinchoice`排版时的`\noindent`, `topsep`键值产生了预想的效果（原来是会产生`bottom`的效果）
