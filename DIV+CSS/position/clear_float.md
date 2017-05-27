## 浮动的原理
>  浮动是脱离文档的普通流存在的（可以看作是漂浮在普通流上），它可以左右浮动，直到它的外边缘遇到包含框或者另一个浮动框为止（即浮动框不在文档普通流中，所以在布局的时候文档中的普通流就会表现得和浮动框不存在一样，当浮动框高度超出包含框的时候，也就会出现包含框不会自动伸高来闭合浮动元素）。

>  正是因为这种浮动的这种特性，所以本该属于普通流中的元素浮动之后，包含框的高度就可能会发生变化（包含框内部由于不存在其他普通流元素了，表现出的高度就为0），在实际应用中，这会严重影响到我们布局，所以我们需要闭合浮动，使其包含框表现出正常的高度。

## 为什么需要清除浮动？
>一般是一个盒子里使用了CSS float浮动属性，导致父级对象盒子不能被撑开，这样清除浮动就有必要了。

![这里写图片描述](http://img.blog.csdn.net/20170527130000057?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQnViYmxlTQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

>如果给上面大盒子内部的两个div同时添加float:left属性 就会变成下面的情况
本来两个黑色对象盒子是在红色盒子内，因为对两个黑色盒子使用了float浮动，所以两个黑色盒子产生了浮动，导致红色盒子不能撑开，这样浮动就产生了。
![这里写图片描述](http://img.blog.csdn.net/20170527130320358?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQnViYmxlTQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

## 浮动产生的副作用：
1. 背景不能显示
由于浮动产生，如果对父级设置了（CSS background背景）CSS背景颜色或CSS背景图片，而父级不能被撑开，所以导致CSS背景不能显示。
2. 边框不能撑开
如上图中，如果父级设置了CSS边框属性（css border），由于子级里使用了float属性，产生浮动，父级不能被撑开，导致边框不能随内容而被撑开。
3. margin padding设置值不能正确显示
由于浮动导致父级子级之间设置了css padding、css margin属性的值不能正确表达。特别是上下边的padding和margin不能正确显示。
4. 影响它的兄弟元素的位置
一个元素设置了浮动样式后，会影响它的兄弟元素，至于如何影响，要看它的兄弟元素是块级元素还是内联元素。如果兄弟元素是块级元素，会无视这个浮动元素，即兄弟元素和浮动元素共处同行，浮动元素会覆盖兄弟元素。除非这些 div 设置了宽度，并且父元素的宽度不足以包含它们，这样兄弟元素才会被强制换行；如果兄弟元素是内联元素，则会尽可能围绕浮动元素。
5. 会导致父元素高度自动清零
浮动元素脱离了普通流，导致父元素高度塌陷。
闭合浮动：使浮动元素闭合，从而减少浮动带来的影响。

## 闭合浮动的方法：
1. 为父盒子设置合适的内容高度。
```css
#container {
	border:1px solid red;
	height: 102px; /*我们可以计算这里内容是 子盒子100px高+2px的上下边框*/
}
```
2.clear:both清除浮动
>为了统一样式，我们新建一个样式选择器CSS命名为“.clear”，并且对应选择器样式为“clear:both”，然后我们在父级“</div>”结束前加此div引入“class="clear"”样式。这样即可清除浮动。
> clear只对块级元素有用，经常会因为忽略这点导致清除效果失败。
```css
.clear {
	clear: both;  /*设置CSS样式*/
}
<div id="container">
	<div id="div1"></div>
	<div id="div2"></div>
	<div class="clear"></div> /*在容器标签结束前加一空标签，给空标签设置样式*/
</div>
```
优点：通俗易懂，容易掌握
缺点：会添加大量无语义的空标签，导致页面空标签迅速堆积，且在页面中无上下文内容，结构与表现未分离，不利于维护。

3.父元素设置overflow:hidden;
>对父级CSS选择器加overflow:hidden样式，可以清除父级内使用float产生浮动。因为overflow:hidden属性相当于是让父级紧贴内容，这样即可紧贴其对象内内容（包括使用float的div盒子），从而实现了清除浮动。
```css
#container {
	border:1px solid red;
	overflow:hidden;   /**/	
}
```
优点：不存在结构和语义化问题，代码量少
缺点：内容增多时容易造成不会自动换行的后果，导致内容被隐藏，无法显示需要溢出的元素。IE需要触发haslayout。

4.父元素设置overflow:auto;
>在具有浮动元素的容器中设置overflow属性值为auto,这样父容器就有一高度，背景就出来了。在IE6下回给元素添加滚动条，故最好使用overflow:hidden;

5.父元素浮动
>不推荐使用，与父元素相邻的元素的布局会受到影响，不可能一直浮动到body。

6.使用:after伪元素（不是伪类）
```css
#container:after {
	content: "."; /*通过 content:"."生成内容作为最后一个元素*/
	display: block; /*使生成的元素以块级元素显示,占满剩余空间;*/
	height: 0; /*避免生成内容破坏原有布局的高度*/
	clear: both;
	visibility:hidden;  /*使生成的内容不可见，并允许可能被生成内容盖住的内容可以进行点击和交互*/
}
```
优点：结构语义化完全正确，代码量居中
缺点：复用方式不当会造成代码量增加。由于IE6和IE7不支持:after，使用zoom:1触发haslayout

## 总结
通过对比，我们不难发现，其实以上列举的方法，无非有两类：
1. 通过在浮动元素的末尾添加一个空元素，设置 clear：both属性，after伪元素其实也是通过 content 在元素的后面生成了内容为一个点的块级元素；
2. 通过设置父元素 overflow 或者display：table 属性来闭合浮动。

## BFC
> 在CSS2.1里面有一个很重要的概念Block formatting contexts （块级格式化上下文），以下简称 BFC。
CSS3里面对这个规范做了改动，称之为：flow root，并且对触发条件进行了进一步说明。


清除浮动的效果
![这里写图片描述](http://img.blog.csdn.net/20170527133312946?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQnViYmxlTQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

**清除浮动和闭合浮动的区别：**

清除浮动：清除对应的单词是 clear，对应CSS中的属性是 clear：left | right | both | none；
clear只对块级元素有用，经常会因为忽略这点导致清除效果失败。

闭合浮动：更确切的含义是使浮动元素闭合，从而减少浮动带来的影响。
>结论：用闭合浮动比清除浮动更加严谨，所以后文中统一称之为：闭合浮动。

推荐好文章：http://www.iyunlu.com/view/css-xhtml/55.html


