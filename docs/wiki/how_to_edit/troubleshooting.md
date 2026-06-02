---
title: 本地预览与常见问题
authors: 龚玉雷
comments: true
---

# 本地预览与常见问题

本文整理本地预览 Wiki 时常见问题，便于协作排查与复用。

## 使用 uv 本地预览

```bash
uv venv
source .venv/bin/activate
uv pip install -r requirements.txt
uv run mkdocs serve
```

如果只想补装缺失插件，也可以单独安装：

```bash
uv pip install mkdocs-macros-plugin mkdocs-git-revision-date-localized-plugin
```

## 使用 pip 本地预览

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
mkdocs serve
```

如果只想补装缺失插件，也可以单独安装：

```bash
pip install mkdocs-macros-plugin mkdocs-git-revision-date-localized-plugin
```

## 常见报错与解决

### 1) zsh: no matches found: mkdocs-static-i18n[material]

zsh 会把方括号当作通配符。请加引号：

```bash
uv pip install "mkdocs-static-i18n[material]"
```

### 2) Config value 'plugins': The "macros" plugin is not installed

插件名与包名不同，正确包名：

```bash
uv pip install mkdocs-macros-plugin
```

### 3) Config value 'plugins': The "git-revision-date-localized" plugin is not installed

正确包名：

```bash
uv pip install mkdocs-git-revision-date-localized-plugin
```

## 反馈与补充

如果遇到新问题，请在仓库 issue 中记录，或直接在本页补充。