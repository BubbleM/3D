### 居中一个元素
```CSS
  width:500px; /*设置元素的宽度和高度，这里宽度必须设置*/
  margin-left:50%; /*浮动元素左边正好位于文档中间*/
  position:relative;
  left:-250px;/*左移宽度的二分之一，实现元素居中*/
```
### 实现一个左右布局的结构，左侧自适应，右侧宽280px
```css
<style>
#wrap {
 position: relative;
}
#left {
 margin-right: 280px;
}
#right {
 position: absolute;
 right: 0;
 top:0;
}
</style>
<div id="wrap">
 <div id="left" style="height: 100px">左侧</div>
 <div id="right" style="height: 100px;width: 280px;">右侧</div>
</div>
```
### 返回顶部的悬浮效果
```css
<div style="position: fixed;top: 50%;left:50%;margin:-250px 0 0 -250px;width: 500px;height: 500px;z-index: 999;">
	<a href="">
		<img src="" alt="弹出广告图"/>
	</a>
</div>
```
