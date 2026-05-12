---
title: Chirpy 里常用的 Markdown 扩展语法
date: 2026-05-11 10:00:00 +0800
categories: [技术笔记, Jekyll]
tags: [markdown, chirpy]
---

Chirpy 在标准 Markdown 基础上加了不少实用扩展，整理一下以后写文章方便。

## Callout 块

四种样式，对应不同语境：

> 这是一条普通提示
{: .prompt-info }

> 这是一条 tip
{: .prompt-tip }

> 这是一条警告
{: .prompt-warning }

> 这是一条危险提示
{: .prompt-danger }

## 文件路径

`_config.yml`{: .filepath } 这样标注会带背景色。

## 代码高亮

````markdown
```python
def hello(name: str) -> None:
    print(f"hello, {name}")
```
````

渲染效果：

```python
def hello(name: str) -> None:
    print(f"hello, {name}")
```

## 图片占位

```markdown
![alt](path/to/image.png){: width="400" height="200" }
_图片下方的说明文字_
```

## 数学公式

Chirpy 自带 MathJax，写 `$E=mc^2$` 就能渲染。

## 脚注

像这样写脚注[^foot]。

[^foot]: 这里是脚注内容，页面底部会自动整理。

---

够用了，更多细节看 [Chirpy 官方文档](https://chirpy.cotes.page/posts/write-a-new-post/)。
