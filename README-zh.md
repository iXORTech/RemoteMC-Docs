[English](README.md) | **中文**

<h1 align="center">RemoteMC-Docs</h1>

<p align="center">
  <b>RemoteMC 系列用户与开发者手册</b>
</p>

<p align="center">
  <a href="LICENSE">
    <img src="https://img.shields.io/badge/License-CC--BY--NC--SA--4.0-important?style=for-the-badge" />
  </a>
</p>

## 贡献文档指南

**您的提交信息应当遵守 [约定式提交](https://www.conventionalcommits.org/zh-hans/v1.0.0/) 规则**

### 安装文档所需依赖

``` bash
pip3 install -r requirements.txt
```

### 编译文档（将 Sphinx 的 rst/md 文件转换为 html 文件）

（该步骤仅用于预览编辑后的文件）

``` bash
make clean
make html
```

文档会在 `docs/html` 目录下以 `zh_CN`（简体中文）生成。

如果你需要更改生成的语言，可以将 `source/conf.py` 文件中第 69 行 `language = os.environ.get('READTHEDOCS_LANGUAGE', 'zh_CN')` 中的 `zh_CN` 改为你想要的语言。

### 更新翻译文件

（该步骤以中文为例，如果需要使用其他语言，将 `zh_CN` 替换为目标语言）

``` bash
cd source
sphinx-build -b gettext . _locale
sphinx-intl update -p _locale -l zh_CN
```

该步骤会在 `source/_locale/zh_CN` 下生成一些 `.po` 文件，这些文件会被用于存储翻译内容：

- 空的翻译字符串会被增加，用于存储新增加的内容的翻译
- `#, fuzzy` 会被添加到被更改内容的 `msgid` 字符串的上一行。请更新翻译并移除 `#, fuzzy`。
- 被删除的翻译内容会被移动到 `.po` 文件的末尾并被注释，请移除这些翻译。

## 📜 协议&许可证

> **RemoteMC-Docs 基于 [CC-BY-NC-SA-4.0 许可证](license-translations/LICENSE-zh)（[原文](LICENSE)）发行**

``` text
RemoteMC-Docs (c) 由 iXOR Techbology, Cubik65536, 以及 所有贡献者 创作.

RemoteMC-Docs 根据知识共享（Creative Commons）
署名—非商业性使用—相同方式共享 4.0 公共许可协议进行分发。

您应该已经收到了一份许可证的副本。如果没有，
请参见 <http://creativecommons.org/licenses/by-nc/4.0/>。
```
