# 浮动
## 1.float属性
- left
- right
- none 元素不浮动
- inherit 从父级继承浮动属性

## 2.clear属性
去除浮动属性（包括继承来的属性）
- left 、right 去掉元素向左、向右浮动
- both 左右两侧均去掉浮动
- inherit 去除从父级继承来的clear的值

## 效果
原始效果 红色1 蓝色2 绿色3

![这里写图片描述](http://img.blog.csdn.net/20170525191221340?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQnViYmxlTQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

给fd 即第一个红色div  添加左浮动

蓝色（第二个div）看不见了  其实是被红色（第一个div）挡住了 

给红色添加左浮动，脱离文档流，红色已经不占浏览器位置了 蓝色充当它的位置过去了 加宽蓝色的宽度即可看出

![这里写图片描述](http://img.blog.csdn.net/20170525191416389?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQnViYmxlTQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)
![这里写图片描述](http://img.blog.csdn.net/20170525192025412?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQnViYmxlTQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

如果每个div都左浮动

![这里写图片描述](http://img.blog.csdn.net/20170525192321648?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQnViYmxlTQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)
