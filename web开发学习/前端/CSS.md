### 小细节知识点
margin-bottom: 10px 外部间距 10px
p标签自带外边距，div标签不带
* 长度单位
```
px是设备上的像素点
% 相对于父元素的百分比
em相对于当前元素字体大小的长度，没有父元素就相当于当前自己的大小、
这个的用法就可以根据当前的大小来相对于之前的进行等比例放大。
rem 相对于根元素的字体大小，相对于根元素的绝对值大小。
vw 相对于视窗宽度的百分比
vh 相对于视窗高度的百分比

```
* 边距
包括内边距和外边距
内边距 padding
外边距 margin

target：_blank 就是在新的标签页面进行重新打开界面

text-overflow 只对横向超出长度的时候有作用，在纵向长度超出的时候是没有作用的

实现居中，可以使用行高等于元素高度。

鼠标放上去可以变成小手的形式是 cursor : pointer一般是放在button上。
渐变效果，transition： 300ms，后面直接加时间单位。

![[Pasted image 20231027183728.png]]
增加padding不会增加高度，就是使用border-box
## 第一次css课程
### 样式表
层叠样式表，包括内部样式表和外部样式表
内部样式表：只对当前一个文件的css作用
```
<ins></ins> 是下划线
<del></del> 是删除线
alt属性进行描述图片等信息时会难以置信的有用

```
border-radius: 50% 修改图片或属性为圆形
```
<link rel = "stylesheet" href="">
```
外部样式表：作用于外部文件中，可以复用，范围，多个文件

### 选择器
#### 标签选择器
```
div{
width:
height:
}
```
#### id选择器
```
#{id}{

}
```
#### 类选择器
```
class 可以存若干个用空格隔开的类标签，
		多个标签可以用同一个class
		一个标签也可以使用多个class
```
#### 伪类选择器
.{classs}：hover{//鼠标悬停的时候的效果
transform: scale(1.1); // 放大的效果
background-color: //改变颜色的效果
transition: 200ms //渐变的效果，用多长时间进行变化
}

a: link{//超链接在没有点击的颜色
	color: red //没有点击之前时红色
	background-color: //颜色和背景颜色之间还是有一定的区别的。
}

a:visited{//超链接点击之后的状态

}

a:hover {//鼠标哦悬浮之后的状态

}

a: active{//鼠标按住不放大状态

}

input: focus{//聚焦之后的状态
默认会变黑边框
}

#### 位置伪类选择器
:nth-child(n) ：选择了父标签第n个子元素的所有元素##
#### 目标伪类选择器
:target : 用于当链接被触发的时候执行效果

#### 复合选择器
div + p 只有紧跟在div后面的p才能触发，改变大小颜色等
p + p 只有紧跟在p后面的p标签才能触发，改变大小颜色等
也可以接id

空格隔开
ele1 ele2选择摸一个标签的内部标签进行改变样式
ele1 > ele2 选择的ele1必须时ele2的父节点

#### 通配选择器
\*{
选择所有标签
}
\[type=text]  选择具有某一个属性的标签

#### 伪元素选择器
:: first-line 选中第一行
:: selection 选中的
{color:
background-color:
}
:: before 在元素的前面添加
:: after 在元素的后面添加

#### 优先级
谁更具体，谁的优先级最高。
开挂调整优先级，!important,将优先级调整到了最高。
id>class>行内样式表

### 颜色
background-color:
rgb 三色组合
rgba 最后一个维度时透明度，a的取值范围为0-1

## 第二次css课程

### 文字对齐
text-align ： 左对齐，右对齐，居中对齐
父标签对齐的话子标签同样可以对齐

font-size： 表示字体的大小

*line-height*: 行高
![[Pasted image 20231024162157.png]]
可以使用行高来实现居中功能。

letter-spacing: 字间距，一般是em作为单位

text-indent: 3em 所进的意思，1个em一般指1个字的距离

text-decoration 修饰

text-shadow  字体的偏移属性，左右方向，上下方向，偏移半径，偏移颜色

font-style:italic 将第一行配置成斜体 

font-weight 加粗效果，这个参数没有单位，border

font-family 进行设置草书字体

、

### 背景
![[Pasted image 20231025140105.png]]
设这背景图片的一些参数，
background-image 的优先级越靠前的优先级越高。
background-position: right bottom ,right top
左下角，右下角
后面接 x,y想左右移动

设置多张图片的时候可以链接多张图片，然后再background-size,和backgrond-poisition都可以放置两对参数，然后用逗号隔开。

### 边框
关于边框的设置
border-style： 上右下左四个方向，分别右1，2，3，4个参数，分别设置不同方向的边框
border-width用于调整边框的粗细程度。
border-color 调整颜色也是上右下左。
border-radius 调整边框角角的小圆的半径， 同样也有4个参数，
border-radius: 50% 20% / 10% 40%; 进行设计边框的外形，有一些比较逆天的外形
border-collapse: 将边框重合再一起

### 展示风格
#### display
* block , 块状标签，div
* inline ，行内标签，可以攻占一行，宽度于高度无效，水平方向的margin和padding有效， span
* inline-block, 行内块状标签,对于宽度和高度都是可以进行调节的
![[Pasted image 20231025162033.png]]
div 变成了span ，span变成了div--display: block 

`white-space`属性值包括：
1. `normal`（默认值）：文本在遇到空格和换行符时自动换行。
2. `nowrap`：文本不自动换行，而是保持在同一行上，直到遇到强制换行或容器边界。
3. `pre`：保留所有空格和换行符，文本将按原样显示。
4. `pre-line`：保留换行符，但合并连续的空格，并根据容器宽度进行换行。
5. `pre-wrap`：保留所有空格和换行符，但根据容器宽度进行换行。

![[Pasted image 20231025165641.png]]
以省略号的形式来代替超出的部分。

![[Pasted image 20231025165042.png]]
overflow: auto在超出文本限制的时候会添加滚轮。

overflow: scroll 好多出都有滚轮，没有指定的状态
overflow-x: scroll;在x方向添加滚轮
overflow-y: scroll;在y方向添加滚轮
同时我们在另一个方向上应该加上overflow-x:hidden


## 第三次css课程

### 内边距与外边距

这就决定了一个元素的大小是内容+
内边距+边界+外边距

* **子类元素设置margin-top，父类元素一起移动的原因以及解决思路**
原因是：边距重叠，一个盒子和其子孙的边距重叠。根据规范，一个盒子如果没有上补白和上边框，那么它的上边距应该和其文档流中的第一个孩子元素的上边距重叠。
解决方案： 为父元素添加上边框或内边距，最低放在1px的距离，
或者时使用overflow： hidden // 当我们希望内部元素可以显示在父亲div外部的时候不要使用这个方法
也可以在父元素的前面添加一个隐藏的元素，
.div-outer:: before{
content:"",
display: table;
}

当存在上边距和下边距的时候，我们取两个边距中较大的一个边距。
外边距只有在上下边距的时候存在重叠，左右方向没有重叠方式。

内边距padding 也是上右下左的方向，同时百分比也是相对于父元素的白分比

### 盒子模型
增加内边距和边开给你的时候会使元素变大
因为在默认情况下，参数为 box-sizing: content
与之相对的是box-sizing: border-box;
这是一个盒子的大小进行完全固定住，如果增加内边距和边界的话是向内进行压缩

### 位置
position
默认的展示方式是static，流展示方式，从上向下正常摆放
display inline-block 摆成一行，摆不下之后进行换行操作
#### *relative*
position: relative;
top：30px，
这样是以自己原来所在的位置，进行上下左右的偏移，right 100 和 left -100是相同的操作

z-index 对于static是没有意义的,对于relativ是有效的，对于除了static都是有效的
#### *absolute*
相对于第一个能够定位元素块进行定位，而不一定是相对于父节点，相当于一个递归的过程

absolute，absolute，fixed（固定定位） 都可以进行定位，除了static都可以定位
绝对定位会将当前元素的原本的位置剔除出去。

#### *fixed*
也是想上找，找到第一个可以定位的位置。
固定定位，会使当前标签相对于浏览器的视窗进行固定定位，不会因为滚动而发生位置的改变
应用方法，就比如是回到顶部这一功能。

#### *sticky*
滑倒指定的位置的时候，他才会移动，实用是某些滑动广告。
就是超出某一个位置的时候会进行粘性布局到指定位置，相当于半fixed
sticky： 元素根据正常文档进行定位，然后相对它的最近滚动祖先和最近块级祖先，包括table-related元素，居于top，right，bottom，和left的值进行偏移，不会影响其他因素。







### 浮动float
一：浮动元素会脱离标准流  
1. 脱离标准普通流的控制（浮）移动到指定位置（动）  
2. 浮动的盒子不再保留原先的位置
所以要消除浮动的影响的时候需要，clear： left，right, both

## 第四次css课程
### 响应式布局
为了在不同分辨率的屏幕上进行合理显示

### flex
是css简写属性设置了弹性项目如何增大缩小以适应其弹性容器中可用的空间
#### 定义在父结点上
flex-direction 来确定排布的方向
**flex-wrap** 来表示是否进行换行
![[Pasted image 20231102101132.png]]
justify-content 的一些参数
![[Pasted image 20231102101145.png]]
align-items
![[Pasted image 20231102101242.png]]在没有规定长度和宽度的情况下，，这里面的strech进行铺满整个页面，
#### 关于flex中的align-items和align-content区别
![[Pasted image 20231102103504.png]]
结论：从上表可知，对于align-items和align-content的区别，我们只需要记住以下两点，

align-items属性是针对单独的每一个flex子项起作用，它的基本单位是每一个子项，在所有情况下都有效果（当然要看具体的属性值）。
align-content属性是将flex子项作为一个整体起作用，它的基本单位是子项构成的行，只在两种情况下有效果：
①子项多行且flex容器高度固定
②子项单行，flex容器高度固定且设置了flex-wrap:wrap;


flex-wrap
CSS 的 flex-wrap 属性指定 flex 元素单行显示还是多行显示。如果允许换行，这个属性允许你控制行的堆叠方向。

取值：
nowrap：默认值。不换行。
wrap：换行，第一行在上方。
wrap-reverse：换行，第一行在下方。
这个换行大有讲究哦，在顺序上。
#### 定义在子节点上
order
定义flex项目的顺序，值越小越靠前。

flex-grow
CSS 属性 flex-grow CSS 设置 flex 项主尺寸 的 flex 增长系数。

负值无效，默认为 0。

flex-shrink
CSS flex-shrink 属性指定了 flex 元素的收缩规则。flex 元素仅在默认宽度之和大于容器的时候才会发生收缩，其收缩的大小是依据 flex-shrink 的值。

负值无效，默认为1。

flex-basis
CSS 属性 flex-basis 指定了 flex 元素在主轴方向上的初始大小。

取值：
width 值可以是 <\length>; 该值也可以是一个相对于其父弹性盒容器主轴尺寸的百分数 。负值是不被允许的。默认为 auto。

flex
flex-grow、flex-shrink、flex-basis的缩写。

常用取值：
auto：flex: 1 1 auto
none：flex: 0 0 auto