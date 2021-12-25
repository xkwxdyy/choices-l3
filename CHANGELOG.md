# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]
- `coffinchoice`的对齐问题
- `choice`命令与`exam`文类的冲突问题
- 预录入答案


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
