## [多列布局](https://bubblem.github.io/blog/CSS/layout/multiple_columns_layout/index.html)
> 在CSS3中，能够创建多个列来对文本进行布局 - 就像报纸那样！

**有如下多列属性：**
- column-count 规定元素应该被分隔的列数
- column-gap 规定列之间的间隔
- column-rule 设置列之间的宽度、样式和颜色规则

## [瀑布流布局](https://bubblem.github.io/blog/CSS/layout/waterfalls_flow/index_css.html)
> CSS3多列实现的瀑布流布局是将内容纵向排序 即第一列排满后才排第二列；而普通的布局是横向排列

## [圣杯布局](https://bubblem.github.io/blog/CSS/layout/holy_grail_layout/index.html)
> 一种常用的网页布局，可以又现有的技术(无一没有缺点)来实现。

>圣杯布局和双飞翼布局基本上是一致的，都是两边固定宽度，中间自适应的三栏布局，其中，中间栏放到文档流前面，保证先行渲染。解决方案大体相同，都是三栏全部float:left浮动，区别在于解决中间栏div的内容不被遮挡上，圣杯布局是中间栏在添加相对定位，并配合left和right属性，效果上表现为三栏是单独分开的（如果可以看到空隙的话），而双飞翼布局是在中间栏的div中嵌套一个div，内容写在嵌套的div里，然后对嵌套的div设置margin-left和margin-right，效果上表现为左右两栏在中间栏的上面，中间栏还是100%宽度，只不过中间栏的内容通过margin的值显示在中间。
![圣杯布局与双飞翼布局的区别](http://img.blog.csdn.net/20170523212056743?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQnViYmxlTQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

## [双飞翼布局](https://bubblem.github.io/blog/CSS/layout/flying_wing_layout/index.html)
> 是一种灵活的布局，始于淘宝UED。如果把三栏布局比作一只大鸟，可以把min看成鸟的身体，sub和extra则是鸟的翅膀。这个布局的实现思路是，先把最重要的身体部分放好，然后再将翅膀移动到适当的地方。是对圣杯布局的一种改良。

## Table布局
> 现在很少用Table布局。是因为Table一定要等到当前页面加载完成之后才能进行渲染，而且table写起来的代码比较大，样式不好控制。但是在一些情况下Table还是很需要的。
