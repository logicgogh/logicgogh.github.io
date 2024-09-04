+++
title = '在任何 Markdown 文件中支持 Mermaid 图表'
date = 2024-09-04T17:38:11+08:00
draft = true
+++


在日常的笔记和文档工作中，**Markdown** 是许多开发者和写作者的首选工具。它以简单易用的纯文本格式和直观的语法著称，使得书写和编辑过程快速高效。然而，当涉及到创建复杂的图表或可视化内容时，Markdown 的原生功能显得有些不足。**Mermaid** 作为一种基于文本的图表生成工具，能够帮助我们轻松创建流程图、序列图、甘特图等复杂的可视化内容。因此，将 Markdown 与 Mermaid 结合起来，能够显著增强我们的文档书写和信息展示能力。

然而，标准的 Markdown 语法并不原生支持 Mermaid 格式，因此在许多情况下，我们需要借助一些特定的 Markdown 编辑器（如 Typora、Obsidian）来实现这一功能。但如果你偏好一种基于纯文本的工作流，并且不希望被特定的 GUI 编辑器绑定，依赖额外的软件来实现 Mermaid 的支持无疑会带来一定的不便。

为此，这篇文章将介绍一种使用 **Pandoc** 搭配 **mermaid-filter** 的解决方案。这种方法允许你在本地编辑 Markdown 文件时，依然以纯文本格式书写，其中的 Mermaid 图表仅作为插入的代码块存在，无需任何 GUI 程序的依赖，能够真正实现 Markdown 文件在任何环境下的跨平台兼容性。

## 解决方案概述

我们的目标是通过 `Pandoc` 和 `mermaid-filter` 实现 Mermaid 图表在 Markdown 文件中的无缝支持，并能够在常用的 Markdown 编辑器中进行预览。`Pandoc` 是一款强大的文档转换工具，支持多种格式之间的转换，而 `mermaid-filter` 则是一个基于 Node.js 的 Pandoc 过滤器，能够处理 Mermaid 代码块并将其转换为图像。

### 步骤 1：安装 Pandoc

首先，我们需要安装 Pandoc。Pandoc 是一个多功能的文档转换工具，它能够将 Markdown 文件转换为 HTML、PDF、Docx 等多种格式。

#### 安装 Pandoc

根据你的操作系统，选择合适的方式安装 Pandoc：

- **Windows**: 前往 [Pandoc 官方下载页面](https://pandoc.org/installing.html)，下载并运行适用于 Windows 的安装程序。
- **macOS**: 可以使用 Homebrew 进行安装，运行以下命令：
  ```sh
  brew install pandoc
  ```
- **Linux**: 大多数 Linux 发行版的软件源中都包含 Pandoc，可以使用包管理器安装：
  ```sh
  sudo apt install pandoc  # Ubuntu 或 Debian
  sudo dnf install pandoc  # Fedora
  sudo pacman -S pandoc    # Arch Linux
  ```

安装完成后，可以通过以下命令检查 Pandoc 是否安装成功：
```sh
pandoc --version
```

### 步骤 2：安装 Mermaid Filter

接下来，我们需要安装 `mermaid-filter`。`mermaid-filter` 是一个 Pandoc 过滤器，它能够识别 Markdown 文件中的 Mermaid 代码块并将其转换为图像格式。

#### 安装 Mermaid Filter

`mermaid-filter` 是一个基于 Node.js 的工具，因此你需要先安装 Node.js 和 npm（Node 包管理器）。安装完成后，运行以下命令来安装 `mermaid-filter`：

```sh
npm install --global mermaid-filter
```

安装完成后，可以通过以下命令检查 `mermaid-filter` 是否安装成功：

```sh
mermaid-filter --version
```

### 步骤 3：配置 Markdown 编辑器的预览功能

在成功安装 Pandoc 和 `mermaid-filter` 之后，你可以配置你的 Markdown 编辑器来支持 Mermaid 图表的预览。以下以 Ghostwriter（一个流行的 Markdown 编辑器）为例，展示如何进行配置。

#### 配置 Ghostwriter 的预览选项

1. 打开 Ghostwriter，进入 **设置** -> **预览** 选项。
2. 在 **预览命令行参数** 中，添加以下参数：
   ```sh
   --filter mermaid-filter
   ```
   这将告诉 Ghostwriter 使用 Pandoc 和 Mermaid Filter 来处理 Mermaid 代码块。

3. 完成配置后，打开一个包含 Mermaid 图表的 Markdown 文件，预览功能即可生效。

### 总结

通过以上步骤，我们实现了在任何 Markdown 文件中支持 Mermaid 图表的功能。使用 Pandoc 和 Mermaid Filter 的方法不仅实现了对 Mermaid 图表的支持，同时保持了文档的纯文本格式，避免了对特定 GUI 编辑器的依赖。这种方法适用于各种工作流，尤其是那些基于命令行或纯文本的工作流。

现在，你可以自由地在 Markdown 文件中插入 Mermaid 图表，并在任何支持 Pandoc 的环境中进行转换和预览。享受这种无缝的、跨平台的工作体验吧！
