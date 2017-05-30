## viewport
是用户的网页可见区域.随设备的不同而不同，在手机上比在电脑屏幕上更小．HTML5引入了一种方法，让网页设计师通过```<meta>```标签来控制视口 。
```html
 <meta name="viewport"  content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
```
- 一个```<meta>```是元素对如何控制网页的尺寸和缩放浏览器的说明。
- width属性控制视口的宽度。可以像width=600这样设为确切的像素数，或者设为device-width这一特殊值来指代比例为100%时屏幕宽度的CSS像素数值。（相应有height及device-height属性，可能对包含基于视口高度调整大小及位置的元素的页面有用。）
- initial-scale属性控制页面最初加载时的缩放等级。maximum-scale、minimum-scale及user-scalable属性控制允许用户以怎样的方式放大或缩小页面。

## 加和不加meta的viewport有什么区别？
加上viewport
![这里写图片描述](http://img.blog.csdn.net/20170529170351360?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQnViYmxlTQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)
去掉viewport
![这里写图片描述](http://img.blog.csdn.net/20170529170736034?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQnViYmxlTQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

参考
１．https://developer.mozilla.org/zh-CN/docs/Mobile/Viewport_meta_tag
２．https://www.quirksmode.org/mobile/viewports.html#link12
