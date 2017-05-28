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

## 为什么利用多个域名来存储网站资源会更有效
- CDN缓存更方便
- 突破浏览器并发限制
- 节约cookie带宽
- 节约主域名的连接数，优化页面响应速度
- 防止不必要的安全问题

## Form中input设置readonly和disabled的区别
- readonly只针对text/password和textarea有效
- disabled对所有表单元素都有效 包括select\radio\checkbox\button等

### 给文字加粗
1. b标签
2. strong 

## 标签alt与title
- alt是给搜索引擎识别的  在图像无法显示时的替代文本；
- title是关于元素的注释信息，主要是给用户解读的。当鼠标放到文字或图片上时，有title文字显示。


## 其他
1. border-top-width:设置上边框的宽度
2. 一个表格可以包含多个tbody，但只能有一个thead和一个tfoot
3. white-space:nowrap;overflow:hidden; 文字强制一行显示，超出的部分隐藏
4. 首行缩进两个字符 text-indent:2em;
5. 去掉链接的虚线框 outline:none;
6. 链接到电子邮箱 <A href="mailto://123@abcd.com">邮箱</A>

