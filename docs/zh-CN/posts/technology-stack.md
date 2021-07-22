---
title: Vdok的技术栈
---

# 技术栈

Vdok 的开发站在巨人的肩膀上！感谢开源社区的项目, 才可以使 Vdok 的想法走进现实, 并使之更容易实现。

## 项目参考

项目在设计之初, 正好在阅读 [slidev](https://github.com/slidevjs/slidev) 的源码, 因此目录结构和代码参考了该项目, 感谢 [Anthony Fu](https://github.com/antfu) 开发的 slidev 项目在实际的开发之中给予了我很多的灵感。

## 开源项目

下面是主要使用到的开源项目, 并会说明选择的原因和所做的事情。

### Vditor

[Vditor](https://github.com/Vanessa219/vditor) (2.9k stars) 是一个优秀的兼容 Markdown 通用语法的编辑器, 基于 JavaScript 原生开发支持主流的开发框架。在此基础上, Vditor 提供了大量的拓展语法和提供了自定义渲染支持。Vditor 的底层 Markdown 语法解析器为 [Lute](https://github.com/88250/lute), 一个基于编译原理由 Golang 写的语法解析器和渲染器。

基于对 Vditor 和 Lute 项目的贡献和对于源码的深度了解, Vdok 可以最大程度上做到代码安全和自主特性定义。

Vdok 设计之初的目的之一是, 为 Vditor 社区拓展生态。Vdok 在最大努力上兼容 Vditor 的所有语法特性 (需要注意的是, 在部分 HTML 的渲染上, Vdok 和 Vditor 的渲染效果并不相同, 这是基于对 Vdok 项目实际的考量)。Vdok 基于 Vditor 自定义部分渲染器, 为了更多的语法支持和更好的用户体验；Vdok 基于其基础样式, 修改了大量的样式以适配全站主题和夜间模式的需要。

关于 Vdok 基于 Vditor 所做的事情, 可以查看源码和更新日志。

### Windi CSS

[Windi CSS](https://windicss.org/) (2.6k stars) 是一个样式工具类项目, 为前端开发关于样式的部分提供了开箱即用的解决方案。相比于 Tailwind, Windi 有更快的编译速度和更多的语法特性支持。基于 Windi CSS, Vdok 的样式覆盖了 Vditor 默认的样式, 更容易实现夜间模式和RTL
等这些特性。

作为 Windi CSS 文档项目的贡献者和中文文档的 maintainer 之一, Windi CSS 让我在使用中爱不释手, 并将它首选为 Vdok 的样式依赖。

### Vite

[Vite](https://vitejs.dev/) (29k starts) 是一个由 [尤雨溪](https://github.com/yyx990803) 设计开发并著提升前端开发构建速度、提升前端开发体验的构建工具, 这对于 Vdok 项目来说非常重要。Vdok 在设计上跟绝大多的文档生成工具有明显的差异, Vdok 既不是一个编译向的文档生成工具, 也不是一个 iife 式的文档生成工具, 我更愿意称之为半编译式的文档生成工具。在运行时和编译时, Vdok 所做的工作是不同的, 而这些努力都是为了更快的文档构建速度, 因此 Vite 是作为底层构建工具的不二之选。

### React
