# 第二章 HTML网页和结构

## 基本元素与树形结构

WebKit中，这个文档会被构建成DOM树。

## WebKit的网页渲染过程

浏览器的主要作用是将用户输入的“URL”转变为可视化的图像。主要分为两个过程：用URL请求资源，将资源构建成DOM树；从DOM树生成可视化图像。

从网页URL到DOM树的流程：

```mermaid
graph TB
	网页URL-->网页内容,js,css等
	网页内容,js,css等-->DOM树
	网页URL-.1.->各种资源加载器
	各种资源加载器-.2.-网络模块
	各种资源加载器-.3.->网页内容,js,css等
	网页内容,js,css等-.4.->HTML解释器
	HTML解释器-.5.->DOM树
	HTML解释器-.6.-Javascript引擎
	Javascript引擎-.7.->DOM树
	HTML解释器-.8.->各种资源加载器
	
```

上述过程中，网页在加载和渲染过程中会发出“DOMContent”事件和DOM的“onload”事件，分别在DOM树构建完成后，以及DOM构建完成并且网页依赖的资源都加载完成。

WebKit利用CSS和DOM树构建RenderObject树直到绘图上下文：

```mermaid
graph TB
	CSS-.1.->CSS解释器
	CSS解释器-.2.->RenderObject树
	RenderObject树-.-布局计算
	DOM树-->RenderObject树
	RenderObject树--3-->RenderLayer树
	RenderLayer树--3-->绘图上下文
```

绘图上下文到最终生成图像：

```mermaid
graph TB
	绘图上下文-->最终的图像
	绘图上下文-.1.->绘图具体实现类
	绘图具体实现类-.2.-2D图形库
	绘图具体实现类-.2.-3D图形库
	绘图具体实现类-.3.->最终的图像
```

问题：

chrome的performance的使用