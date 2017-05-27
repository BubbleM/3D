## CSS引入方式：
1. 外部样式
`<link rel="stylesheet" href="my.css" type="text/css">`
- 优点：使用最多，不仅最能体现CSS的特点，而且也最能体现DIV+CSS中的内容与显示分离的思想，改版维护容易，代码美观。
2. 行内样式
`<div style="border:1px solid red;">参数</div>`
- 用的较少。比如通用性差，效果特殊，使用CSS命令较少，并且不常改动的地方，使用这种方法反而是很好的选择。
3. 内联样式
`<style type="text/css">
.clear {
	clear: none;
}
</style>`
常见于访问量大的门户网站。
- 优点：速度快，所有的CSS控制都是针对本页面标签的，没有多余命令。
- 缺点：改版麻烦，单个页面显得臃肿，CSS不能被其他HTML引用，造成代码量相对较多，维护也麻烦。
4. `<style type="text/css">
    @import url(my.css);
    @import "my.css";
</style>`

## 如何书写高效CSS
1. 不影响页面的布局
2. 去掉不必要的样式
3. 合并相同的样式
4. 尽可能缩小样式的大小
