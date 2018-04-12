# Markdown CSS

## 目的

收集常用，好用的Markdown的CSS文件

## 文件简介

1. MyGitHub2.css

该文件来自liteide中预定义的CSS：GitHub2.css，我在其基础上添加了2-6级标题的序号，当使用`##`时，会自动在前面生成`1. `，下面是一个演示例子：

	# 文档名称，做了居中处理
	## 一级标题
	### 二级标题
    正文首行缩进

生成后的效果：

			        文档名称，做了居中处理

	1 一级标题
	1.1 二级标题
       正文首行缩进


使用这个CSS，可以用来写word中带序号的标题文档了

2. github2.css

这个 CSS 文件是基于 typora 软件来使用的，里面实现了标题的编号，正文首行缩进暂时没有实现。


## 原理

### 标题的编号

其实就是用到了CSS里面元素的before属性，可以在内容前面添加自定义的内容，另外还用到了conter计数器，用来记录编号值，例如二级标题：

    h2:before {
      content: "" counter(heading2) "  ";
    }

### 正文首行缩进

使用到了CSS中的`text-indent`属性:

    body > p {  text-indent:2em  }

## 使用方法

### LiteIDE 编辑器

1. 将指定的CSS文件拷贝到LiteIDE的安装目录中`liteide\share\liteide\markdown\css`
- 使用LiteIDE编写Markdown文件，在预览的时候选择指定的页面样式即可

### Typora 编辑器

1. 打开 Typora，点击菜单栏 File -> Preferences -> Custom Themes -> Open Themes Folder
2. 将 github2.css 文件拷贝到 Themes Folder 里面，重启 Typora 软件即可在菜单栏的 Themes 里面选择该样式

## 后续想实现的功能

1. 目录如何生成：Word里面的目录自动生成非常方便，对于比较大的文档，如果有目录，可以更方便的查看文档，这点不知道CSS能否实现了
- 如何指定分页：例如文档第一页是文档封面，可能有Logo图片，文档时间，文档信息之类的，需要单独一页显示，但目前Markdown的分页是按内容自动分的，如何能添加像Word里面的分页符
- 如何添加页眉页脚：word里面的页眉页脚也是比较方便的，比如文档右下角的页码、左上角的Logo等
