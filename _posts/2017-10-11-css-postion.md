CSS定位 CSS定位 : 改变元素在页面上的位置 CSS定位机制： 普通流：元素按照HTML中的为主顺序决定排布的过程 浮动 绝对布局 CSS定位属性： position 属性

z-index // 标签相对于视线顺序
值	描述 absolute	生成绝对定位的元素，相对于 static 定位以外的第一个父元素进行定位。 元素的位置通过 "left", "top", "right" 以及 "bottom" 属性进行规定。 fixed	生成绝对定位的元素，相对于浏览器窗口进行定位。 元素的位置通过 "left", "top", "right" 以及 "bottom" 属性进行规定。 relative	生成相对定位的元素，相对于其正常位置进行定位。 因此，"left:20" 会向元素的 LEFT 位置添加 20 像素。 static	默认值。没有定位，元素出现在正常的流中（忽略 top, bottom, left, right 或者 z-index 声明）。 inherit	规定应该从父元素继承 position 属性的值。

CSS定位-浮动 float 属性 left	元素向左浮动。 right	元素向右浮动。 none	默认值。元素不浮动，并会显示在其在文本中出现的位置。 inherit	规定应该从父元素继承 float 属性的值。

clear 属性 值	描述 left	在左侧不允许浮动元素。 right	在右侧不允许浮动元素。 both	在左右两侧均不允许浮动元素。 none	默认值。允许浮动元素出现在两侧。 inherit	规定应该从父元素继承 clear 属性的值。

CSS定位-浮动的应用

{ margin: 0px; padding: 0px; } li { list-style: none; } #div1 { width: 950px; height: auto; margin: 20px auto; } ul { width: 250px; float: left; }
<body>









</body>