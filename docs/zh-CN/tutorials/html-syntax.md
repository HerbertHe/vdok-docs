---
title: HTML 语法支持
---

## HTML 语法支持

Markdown 常用于基于 Web 的文档渲染, 其渲染原理是将 Markdown 语法渲染为 HTML 对应样式, 因此 Markdown **原生支持**直接插入 HTML 元素进行渲染。因为 Markdown 原生语法太过简约, 无法做到 [富文本](https://zh.wikipedia.org/wiki/RTF) 的丰富表示, 因此引入 HTML 常用元素进行语法拓展。

## 段落文本

### 下划线

```html
<u>下划线</u>
```

输出: <u>下划线</u>

### 键盘文本

```html
<kbd>Ctrl + K</kbd>
```

输出: <kbd>Ctrl + K</kdb>

## 折叠块

```html
<details>
<summary>标题</summary>

内容
</details>
```

输出:

<details>
<summary>标题</summary>

内容
</details>
