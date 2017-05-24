# position
position属性规定元素的定位类型，该属性在将动画特效脚本化时尤其有用。

原始效果 没有添加任何position属性
![原始效果](http://img.blog.csdn.net/20170524123715603?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQnViYmxlTQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

**取值**
关键字值：static、sticky、relative、absolute、fixed
全局值：inherit、initial、unset

> 只有在元素设置position为relative、absolute、fixed时候top、left、right、bottom才会生效

## static
默认值，没有定位，元素出现在正常流中，按照所编写的HTML标签的顺序依次呈现（忽略top、bottom、left、right、z-index声明）

设置为static 静态的 偏移量不起作用了
![这里写图片描述](http://img.blog.csdn.net/20170524125141825?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQnViYmxlTQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)
## relative
相对定位，相对于其正常位置进行定位。具有和static相同的呈现方式，同样占有在文档流中的固定位置，后面的对象不会侵占或覆盖。与static不同的是，设置了relative的对象，可以通过top、left、right、bottom属性设定新的显示位置，这四个属性的取值是相对于文档流的前一个对象的

添加了relative相对布局，效果如原始效果
![添加relative](http://img.blog.csdn.net/20170524124118714?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQnViYmxlTQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

添加了偏移
![这里写图片描述](http://img.blog.csdn.net/20170524124658647?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQnViYmxlTQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)
## absolute
绝对定位，相对于static之外的第一个父元素进行定位。与relative不同，这个属性会将当前对象拖出文档流，后面的对象会占有原来的位置，top、left、right、bottom属性的指定是相对于浏览器的，和文档流无关。属性值为absolute对象的z-index属性可以设置层叠显示的次序，它是直接有效的。
>绝对定位position示范适用图、不规律布局。
>绝对定位与float浮动不能同时使用，比如一个大盒子里有的是绝对定位，有的是使用css float浮动定位，这样IE6浏览器将不会显示改大对象里的这些绝对定位与相对定位，这也算是IE6 CSS HACK吧，注意不要混用即可。

设置为absolute绝对布局 它好像不占位置了
![absolute](http://img.blog.csdn.net/20170524124417160?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQnViYmxlTQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)
> position:absolute；position:relative绝对定位使用通常是父级定义position:relative定位，子级定义position:absolute绝对定位属性，并且子级使用left或right和top或bottom进行绝对定位。

>绝对定位如果父级不使用position:relative，而直接使用position:absolute绝对定位，这个时候将会以body标签为父级，使用position:absolute定义对象无论位于DIV多少层结构，都将会被拖出以<body>为父级（参考级）进行绝对定位。

**z-index**： 默认值为0，也可取负值，无继承性。在IE下默认值为0，在Firefox下默认值为auto。z-index的数字越高越靠前，并且值必须为整数和正数（正数的整数）。

## fixed与absolute
**共同点**：改变行内元素的呈现方式，display设置为block，让元素脱离普通流，不占据空间；默认会覆盖到非定位元素。

**不同点**：absolute的根元素是可设置的，而fixed的根元素固定为浏览器窗口，当你滚动网页，fixed元素与浏览器窗口之间的距离是不变的。

设置fixed固定的 不管背景如何滚动 都在当前位置
![这里写图片描述](http://img.blog.csdn.net/20170524125004104?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQnViYmxlTQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)
## inherit
规定从父元素继承position属性的值
## sticky
粘性定位元素
