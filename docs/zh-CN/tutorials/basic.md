---
title: Markdown 基础教程
---

## Markdown 基础教程

在本章节, 你将会学到几乎在所有的 Markdown 编辑器和渲染器中均支持的语法特性。

## 标题

Markdown 总共支持六级标题, 四级标题以后**不建议**使用

```markdown
# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题
```

## 段落文本

### 斜体

```markdown
*斜体*

_斜体_
```

输出:*斜体*

### 加粗

```markdown
**加粗**

__加粗__
```

输出: **加粗**

### 加粗斜体

```markdown
***加粗斜体***

___加粗斜体___
```

输出: ***加粗斜体***

### 删除线

```markdown
~~删除文本~~
```

输出: ~~删除文本~~

## 链接

### 超链接

```markdown
[百度](https://www.baidu.com)
```

输出: [百度](https://www.baidu.com)

### 图片链接

```markdown
![Vdok Logo](https://cdn.jsdelivr.net/gh/HerbertHe/vdok@main/assets/logo.png)
```

输出:

<img src="https://cdn.jsdelivr.net/gh/HerbertHe/vdok@main/assets/logo.png" width="150" />

## 代码渲染

### 行内代码

```markdown
`代码内容`

`console.log("Hello World!")`
```

输出: `console.log("Hello World!")`

### 代码块

````markdown
```语言类型
代码内容
```

```js
console.log("Hello World!")
```
````

输出:

```js
console.log("Hello World!")
```

## 引用块

```markdown
> 引用内容
```

输出:

> 引用内容

## 列表渲染

### 无序列表

```markdown
- item1
- item2
- item3

+ item1
+ item2
+ item3
```

输出:

- item1
- item2
- item3

### 有序列表

```markdown
1. item1
2. item2
3. item3
```

输出:

1. item1
2. item2
3. item3

### Task

```markdown
- [ ] item1
- [x] item2
- [ ] item1
```

输出:

- [ ] item1
- [x] item2
- [ ] item1

## 表格

```markdown
| 表头 | 表头 |
| 对齐方式 | 对齐方式 |
| 表格内容 | 表格内容 |

| 左对齐 | 默认对齐 | 居中对齐 | 右对齐 |
| :----- | -------- | :------: | -----: |
| 内容   | 内容     |   内容   |   内容 |
```

输出:

| 左对齐 | 默认对齐 | 居中对齐 | 右对齐 |
| :----- | -------- | :------: | -----: |
| 内容   | 内容     |   内容   |   内容 |
