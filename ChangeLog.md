# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]
- 增加识别插入图片代码自动将`anchor`变成`south`或者`north`，并可以在导言区设置默认
- `label-style`增加一个`none`的选项

## [v2.3.0] - 2021-12-24


### Added
- `prelabel`增加了同义键值: `pre-label`
- `poslabel`增加了同义键值: `pos-label`, `postlabel`, `post-label`

### Changed

### Fixed
- 删除`coffinchoice`排版时的`\noindent`, `topsep`键值产生了预想的效果（原来是会产生`bottom`的效果）
