###工作中遇到的千奇百怪的bug及解决方式

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
二者都不占文档流，运用插件时运用visibility属性是一个不错的选择
```
