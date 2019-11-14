# 前端面试题--js篇

## 1. JavaScript的数据类型以及在内存中的存放位置？

选择符类别如下：

   1.id选择器（ # myid）

   2.类选择器（.myclassname）

   3.标签选择器（div, h1, p）

   4.相邻选择器（h1 + p）

   5.子选择器（ul < li）

   6.后代选择器（li a）

   7.通配符选择器（ * ）

   8.属性选择器（a[rel = "external"]）

   9.伪类选择器（a: hover, li: nth - child）

​    *   可继承： font-size font-family color, UL LI DL DD DT;

​    *   不可继承 ：border padding margin width height ;

​    *   优先级就近原则，样式定义最近者为准;

​    *   载入样式以最后载入的定位为准;

优先级为:

​       !important >  id > class > tag  

​       important 比 内联优先级高

CSS3新增伪类举例：

​    p:first-of-type 选择属于其父元素的首个 <p> 元素的每个 <p> 元素。

​    p:last-of-type  选择属于其父元素的最后 <p> 元素的每个 <p> 元素。

​    p:only-of-type  选择属于其父元素唯一的 <p> 元素的每个 <p> 元素。

​    p:only-child    选择属于其父元素的唯一子元素的每个 <p> 元素。

​    p:nth-child(2)  选择属于其父元素的第二个子元素的每个 <p> 元素。

​    :enabled、:disabled 控制表单控件的禁用状态。

​    :checked，单选框或复选框被选中。

## 2. 下面代码的执行结果？

针对不同的浏览器写不同的CSS code的过程，就是CSS hack。示例如下：

```
var a = 20;
function () {
    console.log(a);
}
```

## 3. **请用Css写一个简单的幻灯片效果页面**

​	知道是要用css3。使用animation动画实现一个简单的幻灯片效果。

```
/**HTML**/
   div.ani
/**css**/
.ani{
	width:480px;
    height:320px;
    margin:50px auto;
    overflow: hidden;
    box-shadow:0 0 5px rgba(0,0,0,1);
    background-size: cover;
    background-position: center;
    -webkit-animation-name: "loops";
    -webkit-animation-duration: 20s;
    -webkit-animation-iteration-count: infinite;
}
@-webkit-keyframes "loops" {
            0% {
                background:url(http://d.hiphotos.baidu.com/image/w%3D400/sign=c01e6adca964034f0fcdc3069fc27980/e824b899a9014c08e5e38ca4087b02087af4f4d3.jpg) no-repeat;             
            }
            25% {
                background:url(http://b.hiphotos.baidu.com/image/w%3D400/sign=edee1572e9f81a4c2632edc9e72b6029/30adcbef76094b364d72bceba1cc7cd98c109dd0.jpg) no-repeat;
            }
            50% {
                background:url(http://b.hiphotos.baidu.com/image/w%3D400/sign=937dace2552c11dfded1be2353266255/d8f9d72a6059252d258e7605369b033b5bb5b912.jpg) no-repeat;
            }
            75% {
                background:url(http://g.hiphotos.baidu.com/image/w%3D400/sign=7d37500b8544ebf86d71653fe9f9d736/0df431adcbef76095d61f0972cdda3cc7cd99e4b.jpg) no-repeat;
            }
            100% {
                background:url(http://c.hiphotos.baidu.com/image/w%3D400/sign=cfb239ceb0fb43161a1f7b7a10a54642/3b87e950352ac65ce2e73f76f9f2b21192138ad1.jpg) no-repeat;
            }
}
```



## 4. 如何垂直居中一个浮动元素？

```
// 方法一：已知元素的高宽
#div1{
    background-color:#6699FF;
    width:200px;
    height:200px;
    position: absolute;        //父元素需要相对定位
    top: 50%;
    left: 50%;
    margin-top:-100px ;   //二分之一的height，width
    margin-left: -100px;
}
 
//方法二:未知元素的高宽
#div1{
    width: 200px;
    height: 200px;
    background-color: #6699FF;
    margin:auto;
    position: absolute;        //父元素需要相对定位
    left: 0;
    top: 0;
    right: 0;
    bottom: 0;
}
```

