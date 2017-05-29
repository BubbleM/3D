CSS中， Box Model叫盒子模型（或框模型），Box Model规定了元素框处理元素内容（element content）、内边距（padding）、边框（border） 和 外边距（margin） 的方式。
![这里写图片描述](http://img.blog.csdn.net/20170529160835254?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQnViYmxlTQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

内边距、边框和外边距可以应用于一个元素的所有边，也可以应用于单独的边。而且，外边距可以是负值，而且在很多情况下都要使用负值的外边距。

元素框的最内部分是实际的内容（element）；直接包围内容的是内边距（padding），内边距呈现了元 素的背景（background）；内边距的边缘是边框（border）；边框以外是外边距（margin），外边距默认是透明的，因此不会遮挡其后的任 何元素（其实元素的margin就是其所在父元素的padding）。元素的背景应用于由内容和内边距、边框组成的区域。

在 CSS 中，width 和 height 指的是内容区域（element）的宽度和高度。增加内边距、边框和外边距不会影响内容区域的尺寸，但是会增加元素框的总尺寸。假设框的每个边上有 10 个像素的外边距和 5 个像素的内边距。如果希望这个元素框达到 100 个像素，就需要将内容的宽度设置为 70 像素。
