# Flex 布局学习笔记

直接抄和翻译 Udacity React 学位的一节课（[Flexbox Guide](https://classroom.udacity.com/nanodegrees/nd019/parts/580105de-1f39-4975-866d-4f430f1aef1d/modules/be422d8e-8927-496d-b203-1868289e90c5/lessons/0d761c28-fb21-432e-a822-f9495ec1b64b/concepts/90f2cd35-dd1a-48a4-a764-cc6e9fec0122)）, 做了一些修改（用微信小程序的框架举例）

如果可以的话，还是推荐直接看课程～

## 简介
Whenever I learn a new technology, I like to answer the question, “Why does this specific technology exist?”
为什么这技术还存在？

 is to create a more efficient way to “layout, align, and distribute space among items”
为了方便地: *对齐*，*布局* 和分配 *元素* 之间的空白

**设计的理念是：** 让 `父元素` 控制 `子元素` 的布局

## 目录
- Flexbox Axes
- Flex Direction
- Justify Content
	- Flex-Start
	- Center
	- Flex-End
	- Space-Between
	- Space-Around
- Align Items
	- Flex-Start
	- Center
	- Flex-End
	- Stretch
- Centering Content
- The Flex Property
- Aligning Individual Items

## Flexbox Axes（轴线）

![Flexbox Axes: Main Axis and Cross Axis](https://d17h27t6h515a5.cloudfront.net/topher/2017/September/59b84519_nd019-c1-l3-flexbox-1/nd019-c1-l3-flexbox-1.jpg "Flexbox Axes: Main Axis and Cross Axis")

当谈到 `Flexbox` 框架时，最重要的概念是： `Main Axis（主轴）` 和 `Cross Axis（十字轴）` 这两条轴线。其余的 `FlexBox 设置` 如：*对齐*，*定位*，*拉伸*，*分布*，*缩小*，*居中*，*包裹（wrap）*，都是沿着这两条轴线进行设置的

## Flex Direction（方向）

当谈到 `主轴` 和 `十字轴` 时，要非常谨慎地留意  **默认效果 **。因为我们可以设置任意 `轴线` 为 `主轴` 或者 `十字轴`，这就引出我们第一个要介绍的设置属性：  `flex-direction`

`flex-direction` 有两个值：
- `row`
- `column`

在默认情况下：`flex-direction` 是 `column`，即：竖着的轴线为 `主轴`，横着的轴线为 `十字轴`

而当设置 `flex-direction` 为 `row` 时，则：竖着的轴线为 `十字轴`，横着的轴线为 `主轴`

![\`flex-direction\` changes which axis is the Main Axis.](https://d17h27t6h515a5.cloudfront.net/topher/2017/September/59b8454e_nd019-c1-l3-flexbox-2/nd019-c1-l3-flexbox-2.jpg "`flex-direction` 决定了哪条 轴线 为 主轴线")

## Justify Content

现在开始谈有趣的部分。看看我们能用哪些 `属性（perties）` 和 `值（values）` 来沿着轴线进行对齐。那么现在先专注于 `主轴线（Main Axis）` 的情况

为了定义 `子元素` 应该如何沿着 `主轴线（Main Axis）` 摆放，我们可以用 `justifyContent` 属性。`justifyContent` 有以下 5 个值来定义 `子元素` 应该如何沿着 `主轴线（Main Axis）` 摆放

- `flex-start`
- `center`
- `flex-end`
- `space-around`
- `space-between`

一下子扔出了所有的值，可能有点懵，但不用担心，接下来我们会一个个地介绍的 💃🏽

如果想深入理解，最好是创建一个项目，然后一步步地跟下来

以下用 `微信小程序` 的代码格式来举例，其它框架的代码也是同理的

```html
<!--index.wxml-->
<view class="container">
  <view class="box"></view>
  <view class="box"></view>
  <view class="box"></view>
</view>
```

```css
  page {
	height: 100%;
  }

  .container {
    height: 100%; 
	flex: 1;
  }

  .box {
	height: 50px;
	width: 50px;
	background-color: red;
	margin: 10px;
  }
```


上面的代码，就是简单地在页面上创建 3 个格子，忽略 `flex: 1` 先，后面会解释它的意义的

### Justify Content: Flex-Start

![justifyContent: flex-start makes flex items appear at the beginning of the Main Axi](https://d17h27t6h515a5.cloudfront.net/topher/2017/September/59b84595_nd019-c1-l3-flexbox-3/nd019-c1-l3-flexbox-3.jpg "justifyContent: flex-start makes flex items appear at the beginning of the Main Axi")

`justify-content: flex-start;` 能让 `子元素` 摆放在 `主轴（Main Axis）`  **开头**

```css
  .container {
    height: 100%;
	flex: 1;
	justify-content: flex-start;
  }
```

### Justify Content: Center

![justifyContent: center makes flex items appear in the center of the Main Axis.](https://d17h27t6h515a5.cloudfront.net/topher/2017/September/59b845cb_nd019-c1-l3-flexbox-4/nd019-c1-l3-flexbox-4.jpg "justifyContent: center makes flex items appear in the center of the Main Axis.")

`justify-content: center;` 让 `子元素` 沿着  `主轴（Main Axis）` **居中**

```css
  .container {
	height: 100%;
    flex: 1;
	justify-content: center;
  }
```

### Justify Content: Flex-End

![](https://d17h27t6h515a5.cloudfront.net/topher/2017/September/59b845f0_nd019-c1-l3-flexbox-5/nd019-c1-l3-flexbox-5.jpg)

`justify-content: flex-end;` 让 `子元素` 放在  `主轴（Main Axis）` **结尾**

```css
  .container {
	height: 100%;
	flex: 1;
	justify-content: flex-end;
  }
```

### Justify Content: Space-Between

![](https://d17h27t6h515a5.cloudfront.net/topher/2017/September/59b84617_nd019-c1-l3-flexbox-6/nd019-c1-l3-flexbox-6.jpg)

`justify-content: space-between;` 依然让  `子元素` 沿着  `主轴（Main Axis）` 摆放, 且 \*\*轴的首尾\*\* 都放上格子，并且格子之间 \*\*添加空白\*\*

```css
  .container {
	height: 100%;
	flex: 1;
	justify-content: space-between;
  }
```


### Justify Content: Space-Around

![justifyContent: space-around flex items are spaced equidistant along the Main Axis.](https://d17h27t6h515a5.cloudfront.net/topher/2017/September/59b8463e_nd019-c1-l3-flexbox-7/nd019-c1-l3-flexbox-7.jpg "justifyContent: space-around flex items are spaced equidistant along the Main Axis.")

`justify-content: space-around;` 让  `子元素` 沿着  `主轴（Main Axis）` 摆放, 且在 *格子的首尾*  **添加相等的空白**

```css
  .container {
	height: 100%;
	flex: 1;
	justify-content: space-around;
  }
```

现在如果我们设置  `flex-direction` 为 `row` 而不是 `column`, 那么结果会是怎样？

答案是：`主轴 （Main Axis）` 不再是垂直的，而是变为 **水平横着**

效果如下：

```css
  .container {
	height: 100%;
	flex: 1;
    flex-direction: row;
	justify-content: space-around;
  }
```

![](https://d17h27t6h515a5.cloudfront.net/topher/2017/September/59b8466a_nd019-c1-l3-flexbox-8/nd019-c1-l3-flexbox-8.jpg)

注意：我们只是改变了 `flex-direction` 的值，就能在布局引起天翻地覆的变化。现在我们是时候展现 `flexbox` 真正的力量了

## Align Items (The Cross Axis)

那么现在开始研究 `十字轴（Cross Axis）` 的做法。为了让 `子元素` 沿着 `十字轴（Cross Axis）` 进行设置，我们设置 `align-items` 属性

你可能直觉上，觉得 `align-items` 的值和 `justify-content ` 的值是对应的, 一样的。那你可猜错了。它有着完全不一样的 4 个值：

- `flex-start`
- `center`
- `flex-end`
- `stretch`

### Align Items - Flex-Start


![alignItems: flex-start causes flex items to appear at the beginning of the Cross Axis.](https://d17h27t6h515a5.cloudfront.net/topher/2017/September/59b84696_nd019-c1-l3-flexbox-9/nd019-c1-l3-flexbox-9.jpg "alignItems: flex-start causes flex items to appear at the beginning of the Cross Axis.")

`align-items: flex-start;` 能让 `子元素` 摆放在 `十字轴（Cross Axis）`  **开头**

```css
  .container {
	height: 100%;
	flex: 1;
	align-items: flex-start;
  }
```

### Align Items: Center

![alignItems: center causes flex items to appear in the middle of the Cross Axis.](https://d17h27t6h515a5.cloudfront.net/topher/2017/September/59b846c3_nd019-c1-l3-flexbox-10/nd019-c1-l3-flexbox-10.jpg "alignItems: center causes flex items to appear in the middle of the Cross Axis.")

`align-items: center;` 能让 `子元素` 沿着  `十字轴（Cross Axis）`  **居中**

```css
  .container {
	height: 100%;
	flex: 1;
	align-items: center;
  }
```


### Align Items: Flex-End

 ![](https://d17h27t6h515a5.cloudfront.net/topher/2017/September/59b846fe_nd019-c1-l3-flexbox-11/nd019-c1-l3-flexbox-11.jpg)

`align-items: flex-end;` 能让 `子元素` 摆在  `十字轴（Cross Axis）`  **结尾**

```css
  .container {
	height: 100%;
	flex: 1;
	align-items: flex-end;
  }
```


### Align Items: Stretch

![alignItems: stretch causes flex items to take up the full width of the Cross Axis.](https://d17h27t6h515a5.cloudfront.net/topher/2017/September/59b8473d_nd019-c1-l3-flexbox-12/nd019-c1-l3-flexbox-12.jpg "alignItems: stretch causes flex items to take up the full width of the Cross Axis.")

`align-items: stretch;` 会使 `子元素` 沿着 `十字轴（Cross Axis）` 拉伸到最大，只要 `子元素` 没有设置高度（`flex-direction: row`）或者宽度（`flex-direction: column`）

```css
  .container {
	height: 100%;
	flex: 1;
	align-items: stretch;
  }

  .box {
	height: 50px;
	background-color: red;
	margin: 10px;
  }
```

为了巩固一下知识，试想一下，下面的 CSS 代码会呈现出怎样的 UI：

```css
  .container {
	height: 100%;
	flex: 1;
	align-items: stretch;
	flex-direction: row;
  }

  .box {
	width: 50px;
	background-color: red;
	margin: 10px;
  }
```

注意⚠️：上面的代码添加了 `flex-direction: row;` 和将 `height` 变为 `width`

![](https://d17h27t6h515a5.cloudfront.net/topher/2017/September/59b84763_nd019-c1-l3-flexbox-13/nd019-c1-l3-flexbox-13.png)

### Centering Content

![](https://d17h27t6h515a5.cloudfront.net/topher/2017/September/59b847b5_nd019-c1-l3-flexbox-14/nd019-c1-l3-flexbox-14.jpg)


要达到上面的效果：将格子居中于屏幕。

我们一步步来完成：
1. 因为上面的 `主轴（Main Axis）` 是横着的，使用 `flex-direction: row;`
2. 看到格子沿着 `主轴（Main Axis）`  居中，使用 `justify-content: center;`
3. 格子也沿着 `十字轴（Cross Axis）` 居中，使用 `align-items: center;`

```css
  .container {
	height: 100%;
	flex: 1;
	align-items: center;
	justify-content: center;
	flex-direction: row;
  }

  .box {
	width: 50px;
	height: 50px;
	background-color: red;
	margin: 10px;
  }
```

### The Flex Property

但是，万一我们想完成下图的效果呢？

![Using the flex property to change the rate at which a flex items increases its size comparable to other flex items.](https://d17h27t6h515a5.cloudfront.net/topher/2017/September/59b847ee_nd019-c1-l3-flexbox-15/nd019-c1-l3-flexbox-15.jpg "Using the flex property to change the rate at which a flex items increases its size comparable to other flex items.")

上图可见：中间的格子是其它两边格子 **宽度** 的两倍。可以使用 `flex` 属性来进行设置：

```html
<!--index.wxml-->
<view class="container">
  <view class="box" style='flex: 1'></view>
  <view class="box" style='flex: 2'></view>
  <view class="box" style='flex: 1'></view>
</view>
```

```css
  .container {
	height: 100%;
	flex: 1;
	align-items: center;
	justify-content: center;
	flex-direction: row;
  }

  .box {
	width: 50px;
	height: 50px;
	background-color: red;
	margin: 10px;
  }
```

注意⚠️: 这里没有添加任何样式; 只是让中间的格子为 `flex: 2` ，而其他的格子为 `flex: 1`。这就等于说 **“确保中间格子的长度（沿着主轴方向）是第 1 和第 3 个格子的 2 倍大”**

这就是为什么 `flex` 可以替换百分比的原因，因为通常基于百分比的布局只是特定元素相对于其他元素的布局，就像我们上面所做的那样。

同样重要的是要注意: 如果在元素上设置 `flex：1`，该元素将占用与 `父元素` 占用的空间 **一样多** 的空间。 这就我们上面的大多数例子中设置它的原因，因为我们希望我们的 “布局区域” 是 `父元素` 的大小，即是整个屏幕的大小

### Aligning Individual Flex Items

如果我们想做成下面的布局呢？

![alignSelf: flex-end changes the flex item it targets to appear at the end of the Cross Axis.](https://d17h27t6h515a5.cloudfront.net/topher/2017/September/59b8481d_nd019-c1-l3-flexbox-16/nd019-c1-l3-flexbox-16.jpg "alignSelf: flex-end changes the flex item it targets to appear at the end of the Cross Axis.")

第 1 个和第 3 个格子在垂直和水平方向都居中，第 2 个格子却特立独行，沿着 `十字轴（Cross Axis）` 使用 `flex-end`

为了实现这一点，我们需要一种方法让 `子元素` 覆盖从 `父元素` 接收的特定定位。 **好消息：** 这正是 `align-self` 做的事情！ 注意它以 `align` 开头，所以就像 `align-items` 一样，它将沿着 `十字轴（Cross Axis）` 定位。 它还具有与 `align-items`（`flex-start`，`flex-end`，`center`，`stretch`）完全相同的值

```html
<!--index.wxml-->
<view class="container">
  <view class="box"></view>
  <view class="box" style='align-self: flex-end'></view>
  <view class="box"></view>
</view>
```

```css
  .container {
	height: 100%;
	flex: 1;
	align-items: center;
	justify-content: center;
	flex-direction: row;
  }

  .box {
	width: 50px;
	height: 50px;
	background-color: red;
	margin: 10px;
  }
```


请注意⚠️: 我们所做的只是将 `align-self：flex-end` 添加到第 2 个子元素，让它覆盖 `父元素` 指示它的操作（`align-items：center`）

那么到这里，基本上布局的基本用法已经介绍完毕了，看别人锻炼不会使你减重，赶紧试试看吧！

## 参考链接

- [ A Complete Guide to Flexbox ](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [ Flexbox Froggy ](http://flexboxfroggy.com/) （30 分钟左右就能通关了的布局游戏，有中文）up 主推荐！！
