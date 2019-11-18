# 前端面试题--js篇

## 1. nginx解决前端跨域的原理？

代理解决跨域原理：

通过一些方法设置代理，在请求发送(接收)之前加入中间层，

将不同的域名转换成相同的

就解决了跨域的问题

客户端发送请求时

不直接到服务器

而是先到代理的中间层

在这里将localhost：8088的这个域名装换为192.168.0.67:8061，

再将请求发送到服务器

这样在服务器端收到的请求就是使用的192.168.0.67:8061域名

同理，当服务器返回数据的时候，也是先到代理的中间层

将192.168.0.67:8061转换成localhos：8088；

这样在客户端也是在相同域名下访问的了。

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

