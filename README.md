```
<script src="http://api.html5media.info/1.1.4/html5media.min.js"></script>
```

###工作中遇到的千奇百怪的bug及解决方式
###正则表达示网站 http://leaverou.github.io/regexplained/
###### 最小宽度的感受

```
1 最小宽度不能随便设置，当分辨率小时，会出bug
2 在body里设置最小宽度  可以解决手机模式的不居中问题


```
###### ie的各种问题
```
1 border-radius ie8不兼容问题  用背景图片解决
2 console.log在ie会报错  js代码要将console.log去除
3 滚动事件时，ie8及ie8以下不支持document,所以用window对象，window对象兼容所有的浏览器
```

###### display:none和visibility:hidden
```
运用插件时，当用到display:block时，会出现获取不到的bug，就用visibility:visible的方法解决即可，
二者都不占文档流，运用插件时运用visibility属性是一个不错的选择,visibility在弹出层的时候比较适合使用
```

###### 多行隐藏，兼容ie（原生js）
```
推荐网址https://github.com/josephschmitt/Clamp.js

用法：

var header = document.getElementsByTagName('body')[0].getElementsByTagName('h1')[0],
            paragraph = document.getElementsByTagName('body')[0].getElementsByTagName('div')[0];
            paragraphp=paragraph.getElementsByTagName('p')[0];
            
$clamp(header, {clamp: 1, useNativeClamp: false});
$clamp(paragraphp, {clamp: 10, useNativeClamp: false, animate: true});
```
######开发html5页面时用rem去控制自适应，但当与后台结合时，后端录入内容，就用px，并引入mc-mobile.js，mc-mobile.css即可，源代码在百度云盘

######word-wrap:break-word和word-break;break-all的区别
```
word-wrap:break-word 例子与上面一样，但区别就是它会把congratulation整个单词看成一个整体，如果该行末端宽度不够显示整个单词，它会自动把整个单词放到下一行，而不会把单词截断掉的。
word-break;break-all 支持版本：IE5以上 该行为与亚洲语言的 normal 相同。也允许非亚洲语言文本行的任意字内断开。该值适合包含一些非亚洲文本的亚洲文本。 WORD-WRAP:break-word 支持版本：IE5.5以上 内容将在边界内换行。
```
######if(){}else{}和try(){}catch(e){}区别
```
if(){}else{}属于程序结构中的分支结构
try(){}catch(e){}属于程序结构的顺序结构
```
#####ES6语法思考
```
1、let和const命令
① let和var用法相似，但let所声明的变量只在let命令所在的代码块内有效，例如：
for (let i = 0; i < 10; i++) {}
console.log(i);
//ReferenceError: i is not defined;
var a = [];
for (var i = 0; i < 10; i++) {
  a[i] = function () {
    console.log(i);
  };
}
a[6](); // 10

var a = [];
for (let i = 0; i < 10; i++) {
  a[i] = function () {
    console.log(i);
  };
}
a[6](); // 6

②let和const不存在变量提升
③暂时性死区（块级区域存在let、const命令，他所声明的变量就绑定了这个区域，不再受外部的影响）
④let不允许在相同的作用域内，重复声明同一个变量

```
##图片的base64编码
########我们都知道，我们的网站采用的都是http协议，而http协议是一种无状态的连接，就是连接和传输后都会断开连接节省资源。此时解决的方法就是尽量的减少http请求，此时base64编码可以将图片添加到css中，实现请求css即可下载下来图片，减少了再次请求图片的请求。当然减少http请求次数的方法还有很多，如css sprite技术，将网页中的小图片拼在 一张大图中，下载时只需要一次完整的http请求就可以，减少了请求次数。
