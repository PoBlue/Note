# Learning CSS Layout (基本知识)

布局的笔记 📔

## display

首先要了解的属性 `display` 

对于大多数元素它们的 **默认值** 通常是 `block` 或 `inline` 。一个 `block` 元素通常被叫做块级元素。一个 `inline` 元素通常被叫做行内元素

### block

`div` 是一个标准的块级元素。一个块级元素会新开始一行并且尽可能撑满容器。其他常用的块级元素包括:  `p` 、 `form` 和HTML5中的新元素： `header` 、 `footer` 、 `section` 等等

### inline

`span` 是一个标准的行内元素。一个行内元素可以在段落包裹一些文字, 而不会打乱段落的布局。`a` 元素是最常用的行内元素，它可以被用作链接。

### none

另一个常用的 `display` 值是 `none` 。一些特殊元素的默认 `display` 值是它，例如 `<script>` 。 `display:none` 通常被 JavaScript 用来在不删除元素的情况下隐藏或显示元素

它和 `visibility` 属性不一样。把 `display` 设置成 `none` 元素 **不会占据** 它本来应该显示的空间，但是设置成 `visibility: hidden;` **还会占据** 空间。

### 其它的 display 值

还有很多的更有意思的 `display` 值，例如 `list-item` 和 `table` 。这里有一份[详细的列表](https://developer.mozilla.org/en-US/docs/Web/CSS/display)。之后我们还会讨论到 `inline-block` 和 `flex` 

### tips

每个元素都有一个默认的 **display** 类型。不过你可以随时随地的**重写它！** 可以把有特定语义的元素改成 *行内元素* 。常见的例子是：把 `li` 元素修改成 `inline`，制作成水平菜单。


## box-sizing

设置 `box-sizing: border-box;` 时，元素的内边距和边框不再会增加它的宽度

## position（重头戏）

为了做出复杂的布局，我们需要 `position`, 它有很多的值，而且名字和意义是没有关联的，非常难记，建议是把这页 BookMark 一下

### static

`static` 是一个默认值。一个元素设置为 `static` 它是不会被 `定位（positioned）` 的，如果是其它值，那么该元素就是能被 `定位（positioned）` 的

### relative

如果不添加其它的设置，`relative` 和 `static` 的效果一样

设置 `top`, `right `, `bottom `, `left` 属性，会让 `relative` 的元素，相对它原来的位置进行定位

### fixed

`fixed` 的元素是相对于 `viewport` 定位的。当设置 `top`, `right `, `bottom `, `left` 属性 ,它会保持在同一个地方，即使页面滚动

### absolute

`absolute` 和 `fixed` 的效果差不多，只不过 `absolute` 是相对 **父 `positioned` 元素** （即父元素设置了非  `static` 的值）定位的


## float

用来控制被文字包围的 `图片`

### clear

使用 `clear` 让元素可以摆脱围绕着 `float` ，进行换行

### overflow: auto;

使用 `overflow: auto;` 使得容器能够包围 `float` 元素


