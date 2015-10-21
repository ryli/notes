CSS 收集
---
###1.帮助移动设备显示网页
```
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta http-equiv="X-UA-Compatible" content="IE=Edge">
```

###2.帮助ie低版本使用html5标签
```
 <!--[if lt IE 9]>
<script src="http://html5shim.googlecode.com/svn/trunk/html5.js"></script>
<!--[end if]--> 
}
```

### 3.一些样式
```
font-family:"Century Gothic","Microsoft yahei";
color: #323232;
line-height: 1.8;
```
###4.响应布局
```
@media (max-width: 767px) { body {background:#f00; ... }}    当浏览器宽度小于767像素时应用的样式
@media (min-width: 767px) { body {background:#f00; ... }}     当浏览器宽度大于767像素时应用的样式
@media (min-width: 767px) and (max-width: 979px)  {...}        当浏览器宽度大于767像素且小于979像素时应用的样式

@media (max-width: 320px) { }
@media (min-width: 320px) and (max-width: 375px) {}
@media (min-width: 375px) and (max-width: 414px) {}
@media (max-width: 414px) { }

```

###5.文字超出之后用...隐藏超出部分
```
p {text-overflow:ellipsis; white-space:nowrap; overflow:hidden;}
text-overflow:clip 直接剪切
p:hover {white-space: normal; overflow: visible; text-overflow: inherit; cursor: hand; cursor:pointer}
/* 多行 */
p { 
    width: 200px;
    height: 49px;
    overflow: hidden;
    -webkit-box-orient: vertical; /* 必须结合的属性 ，设置或检索伸缩盒对象的子元素的排列方式 。*/
    display: -webkit-box; /*  必须结合的属性 ，将对象作为弹性伸缩盒子模型显示 。*/
    -webkit-line-clamp: 2; /* 用来限制在一个块元素显示的文本的行数。 为了实现该效果，它需要组合其他的WebKit属性。*/
    text-overflow: ellipsis;
}

```

###6.标点符号悬挂
```
&ldquo; &rsquo; &rdquo;
p {text-indent: -0.3em}
```

###7.分栏
```
column-count:2;
column-gap:20px;
column-rule:1px solid #ccc;    边框
```

###8. 输入自动转大写
```
text-transform: uppercase;
```

###9.透明度
```
opacity: 0.35;
```

###10.图片边框: 自动把图片的每个部分用于对应的边框
```
border-image: url( img/c.gif) 25% 25% 25% 25% / 25px round round;
```

###11.投影
box-shadow: 3px 3px 6px #666;

###12.换行
```
.wrap { table-layout: fixed; word-break: break-all; overflow: hidden}
.wrap { word-wrap: break-word;}
```
 
###13.增强focus定义
```
a:focus{
    outline: 1px solid red;
    background: yellow;
}
```

###14.添加基本的Landmarks
ARIA Landmark是W3C定义的一套网站可用性规则，对于网站不同的模块添加描述性的Landmark——或者直接叫role，有利于读屏软件更好的理解你的网页，从而让视障用户更好的使用你的网站。
```
<navrole="navigation">
<divid="maincontent"role="main">
<formaction="search.php"role="search">
```

###15.几款浏览器对透明度的支持方式各不相同，为了保证在IE, Firefox, Chrome, Safari等主流浏览器下都能正常显示透明度的效果，我们可以定义一个透明度的class，因为一写就要写3条，省的每次都复制来复制去了。
具体代码如下：

```
.transparent {
    filter:alpha(opacity=60 ); /*支持 IE 浏览器*/    
    -moz-opacity:0.60 ; /*支持 FireFox 浏览器*/
    opacity:0.60 ; /*支持 Chrome, Opera, Safari 等浏览器*/
}
```

###16.选中背景
```
    ::selection {background:#073642; color:#D84D2D;}
    ::-moz-selection {background:#073642; color:#D84D2D;}
    ::-webkit-selection {background:#073642; color:#D84D2D;}
```

###17. 清除浮动
```
    .clearfix:after {content:"."; display:block; height:0; visibility:hidden; clear:both; }
    .clearfix:after {content:"\200B"; display:block; height:0; clear:both; }
    .cf:before, .cf:after {content:""; display:table;}
    .clearfix { *zoom:1; }
```

###18. reset
```
    html,body,div,span,applet,object,iframe,h1,h2,h3,h4,h5,h6,p,blockquote,pre,a,abbr,acronym,address,big,cite,code,del,dfn,em,img,ins,kbd,q,s,samp,small,strike,strong,sub,sup,tt,var,b,u,i,center,dl,dt,dd,ol,ul,li,fieldset,form,label,legend,table,caption,tbody,tfoot,thead,tr,th,td,article,aside,canvas,details,embed,figure,figcaption,footer,header,hgroup,menu,nav,output,ruby,section,summary,time,mark,audio,video{margin:0;padding:0;border:0;font-size:100%;font:inherit;vertical-align:baseline}
article,aside,details,figcaption,figure,footer,header,hgroup,menu,nav,section{display:block}body{line-height:1}
    ol,ul{list-style:none}
    blockquote,q{quotes:none}
    blockquote:before,blockquote:after,q:before,q:after{content:'';content:none}
    table{border-collapse:collapse;border-spacing:0}
```
###19. animate
```
@-webkit-keyframes scroll {    
    0% {    
        -webkit-transform: translateX(0) translateY(0px) translateZ(0) rotateX(0deg) rotateY(0deg) rotateZ(0deg) scaleX(1) scaleY(1) scaleZ(1);    
        -moz-transform: translateX(0) translateY(0px) translateZ(0) rotateX(0deg) rotateY(0deg) rotateZ(0deg) scaleX(1) scaleY(1) scaleZ(1);    
        -ms-transform: translateX(0) translateY(0px) translateZ(0) rotateX(0deg) rotateY(0deg) rotateZ(0deg) scaleX(1) scaleY(1) scaleZ(1);    
        transform: translateX(0) translateY(0px) translateZ(0) rotateX(0deg) rotateY(0deg) rotateZ(0deg) scaleX(1) scaleY(1) scaleZ(1);    
    } 
}   
p {

    -webkit-animation: scroll 2s infinite;  
}  

```
###20. overflow:auto
```
overflow:auto;/* winphone8和android4+ */
-webkit-overflow-scrolling: touch; /* ios5+ */
```
### 21 颜色反转
```
    filter: invert(100%); /* 0%正常显示，100%完全反色 */
   -webkit-filter: invert(100%);
```
