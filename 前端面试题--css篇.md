# 前端面试题--css篇

## 1. CSS 选择符有哪些？哪些属性可以继承？优先级算法如何计算？ CSS3新增伪类有那些？

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

## 2. 什么是Css Hack？ie6,7,8的hack分别是什么？

针对不同的浏览器写不同的CSS code的过程，就是CSS hack。示例如下：

```
#test {   
        width:300px;   
        height:300px;   
        background-color:blue;      /*firefox*/
        background-color:red\9;      /*all ie*/
        background-color:yellow;    /*ie8*/
        +background-color:pink;        /*ie7*/
        _background-color:orange;       /*ie6*/   
     }  
:root #test { background-color:purple\9; }  /*ie9*/
@media all and (min-width:0px){ 
 	#test {background-color:black;} 
}  /*opera*/
@media screen and (-webkit-min-device-pixel-ratio:0){
	#test {background-color:gray;} 
}   /*chrome and safari*/

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



## 5.display:none、visibility:hidden和opacity:0之间的区别

1. display: none (不占空间，不能点击)（场景，显示出原来这里不存在的结构）
2. visibility: hidden（占据空间，不能点击）（场景：显示不会导致页面结构发生变动，不会撑开）
3. opacity: 0（占据空间，可以点击）（场景：可以跟transition搭配）

- **空间占据** 

  display:none隐藏后不占据额外空间，它会产生回流和重绘，而visibility:hidden和opacity:0元素虽然隐藏了，但它们仍然占据着空间，它们俩只会引起页面重绘。  

- **子元素继承** 

  display:none不会被子元素继承，但是父元素都不在了，子元素自然也就不会显示了，皮之不存，毛之安附~~

  visibility:hidden 会被子元素继承，可以通过设置子元素visibility:visible 使子元素显示出来

  opacity: 0 也会被子元素继承，但是不能通过设置子元素opacity: 0使其重新显示。

- **事件绑定**

  display:none 的元素都已经不再页面存在了，因此肯定也无法触发它上面绑定的事件；

  visibility:hidden 元素上绑定的事件也无法触发；

  opacity: 0元素上面绑定的事件是可以触发的。

- **过度动画**

  transition对于display肯定是无效的，大家应该都知道；

  transition对于visibility也是无效的；

  transition对于opacity是有效。

  

  1. 