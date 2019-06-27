持续更新中...
* _2019-6-27_

### Flex 布局

> Flex 是 Flexible Box的缩写，'弹性布局'提供最大的灵活性
任何一个容器都可以指定为Flex 布局；

````
 /* 块级元素 */
 div{
    display:flex;
 }
 /*  行内元素  */
 span{
    display:inline-flex;
 }
 /* 
 Webkit 内核的浏览器，必须加上 -webkit前缀  */
 
 .box{
    display:-webkit-flex; /*Safari */
    display:flex;
 }
````
*设为flex布局之后，子元素 float、clear、vertical-align属性失效*

* 容器默认有两根轴，水平的主轴(main axis)和垂直的交叉轴（cross axis）。

> _采用 flex 布局的元素，简称'容器'，它的所有子元素自动成为容器成员，
简称"项目"_

#### 容器的属性

> flex-direction属性 决定主轴的方向（项目的排列方向）
```
  .box{
    flex-direction:row | row-reverse | column | cloumn-reverse;
  }
  /* 
    row : 默认 水平方向，左端开始
    row-reverse :  水平方向，右端开始
    column ：垂直方向，起点在上沿
    column-reverse ：垂直方向 ，起点在下沿
  */
```
> flex-wrap属性，一条轴线排不下的时候，如何换行
```
 .box{
    flex-wrap : nowrap | wrap | wrap-reverse
 }
 /*
    nowrap : 默认 不换行
    wrap：换行 第一行在上方
    wrap-reverse：换行第一行在下方 
 */
```
> flex-flow 属性是 flex-direction 和 flex-wrap 的简写模式，默认值 row nowrap
```
 flex-flow: <flex-direction> | <flex-wrap>
```
> justify-content 属性定义了项目在主轴上的对齐方式

```
.div{
    justify-content :flex-start | flex-end | center | space-between | space-around;
}
/*
    flex-start : 左端对齐
    flex-end ： 右端对齐
    center：居中
    space-between: 两端对齐，项目之间的间隔都相等；
    space-around : 每个项目两侧的间隔相等；
    
*/
```

> align-items属性定义了在交叉轴上如何对齐

```
.div{
    align-items:flex-start | flex-end | center | baseline | stretch;
}
/*
flex-start : 交叉轴的起点对齐；
flex-end ： 交叉轴的终点对齐；
center ： 交叉点的中点对齐；
baseline ： 项目的第一行文字的基线对齐
stretch ：未设置高度或auto，占满容器的高度
*/
```
> align-content 属性定义了多根轴线的对齐方式，如果项目只有一条轴线，该属性不起作用；
```
   .box{
      align-content: flex-start | flex-end | center | space-between | space-around | stretch;
   }
   /*
    flex-start: 交叉轴的起点对齐
    flex-end：交叉轴的终点对齐
    center：交叉轴的中点对齐
    space-between: 交叉轴两端对齐，轴线之间的间隔平均分布
    space-around ： 没跟轴线两侧的间隔都相等。所以，轴线之间的间隔比轴线与边框的间隔大一倍
    stretch：轴线占满挣个交叉轴
   */
```
[参考阮一峰老师](http://www.ruanyifeng.com/blog/2015/07/flex-grammar.html?utm_source=tuicool)





























