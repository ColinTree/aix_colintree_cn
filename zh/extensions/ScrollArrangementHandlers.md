# 滚动布局管理器 - ScrollArrangementHandlers (v2+)

---

这个拓展包内包含了两个拓展，水平滚动布局管理器HorizontalScrollHandler，和垂直滚动管理器VerticalScrollHandler

* 2017.12.25更新：
  * 修复了VerticalScrollHandler的事件无法触发的问题
  * 修复了ScrollChanged返回错误的数据的问题
  * 修复了ScrollPosition，MaxScrollPosition的单位错乱问题（我弄混了安卓像素单位和ai像素单位），现在相关的事件应该也工作正常了
  * 修复了OverScrollMode修改无效的问题
  * 增加了过度滚动的事件 - Overscroll
  * 圣诞快乐！

* 2017.9.29更新：
  * 修复了大部分方法的命名问题（并重命名组件以避免错误）
  * 加了个组件图标
  * 增加了“显示渐变边缘”属性 - FadingEdgeEnabled
  * 增加了“过度滚动动画样式”属性 - OverScrollMode
  * 增加了“显示滚动条”属性 - ScrollBarEnabled
  * 增加了“允许用户操作滚动布局”属性 - UserControl
  * 增加了“最大滚动位置”属性 - MaxScrollPosition
  * 增加了“滚动位置”属性 - ScrollPosition

* 2017.8.26更新：
  * 增加了布局被松开事件 - TouchUp


## 水平滚动布局管理器 HorizontalScrollHandler

### 事件（水平）

* 向左过度拖动
  {% Ai2Event %}{"name":"OverScrollLeft", "param":["displacement"], "componentName":"HorizontalScrollHandler1"}{% endAi2Event %}
* 向右过度拖动
  {% Ai2Event %}{"name":"OverScrollRight", "param":["displacement"]}{% endAi2Event %}
* 布局滚动到最左端
  {% Ai2Event %}{"name":"ReachLeftEnd"}{% endAi2Event %}
* 布局滚动到最右端
  {% Ai2Event %}{"name":"ReachRightEnd"}{% endAi2Event %}
* 布局发生滚动
  {% Ai2Event %}{"name":"ScrollChanged", "param":["scrollX"]}{% endAi2Event %}
* 布局被按下
  {% Ai2Event %}{"name":"TouchDown"}{% endAi2Event %}
* 布局被松开
  {% Ai2Event %}{"name":"TouchDown"}{% endAi2Event %}

### 方法（水平）

* 向左半页滚动
  {% Ai2Method %}{"name":"ArrowScrollLeftward"}{% endAi2Method %}
* 向右半页滚动
  {% Ai2Method %}{"name":"ArrowScrollRightward"}{% endAi2Method %}
* 向左整页滚动
  {% Ai2Method %}{"name":"PageScrollLeftward"}{% endAi2Method %}
* 向右整页滚动
  {% Ai2Method %}{"name":"PageScrollRightward"}{% endAi2Method %}
* 绑定水平滚动布局
  {% Ai2Method %}{"name":"RegisterScrollView", "param":["horizontalScrollArrangement"]}{% endAi2Method %}
* 滚动一段距离
  {% Ai2Method %}{"name":"ScrollBy", "param":["px"]}{% endAi2Method %}
* 滚动到最左
  {% Ai2Method %}{"name":"ScrollLeftEnd"}{% endAi2Method %}
* 滚动到最右
  {% Ai2Method %}{"name":"ScrollRightEnd"}{% endAi2Method %}
* 滚动到指定位置
  {% Ai2Method %}{"name":"ScrollTo", "param":["px"]}{% endAi2Method %}
* 平滑的滚动一段距离
  {% Ai2Method %}{"name":"SmoothScrollBy", "param":["px"]}{% endAi2Method %}
* 平滑的滚动到指定位置
  {% Ai2Method %}{"name":"SmoothScrollTo", "param":["px"]}{% endAi2Method %}
* ** 参数解释： **
  * px - 滚动的距离。向右为正，向左为负

### 属性（水平）

* 显示渐变边缘
  {% Ai2Property %}{"name":"FadingEdgeEnabled"}{% endAi2Property %}
  {% Ai2Property %}{"name":"FadingEdgeEnabled", "getter":false}{% endAi2Property %}
* 最大滚动位置
  {% Ai2Property %}{"name":"MaxScrollPosition"}{% endAi2Property %}
* 过度滚动动画样式
  * 0 - 总是允许过度滚动
  * 1（默认） - 当布局可以被有效滚动时才允许过度滚动
  * 2 - 禁止过度滚动
  * **（在不同版本的系统中过度滚动动画看起来可能会不太一样**
  {% Ai2Property %}{"name":"OverScrollMode"}{% endAi2Property %}
  {% Ai2Property %}{"name":"OverScrollMode", "getter":false}{% endAi2Property %}
* 显示滚动条
  {% Ai2Property %}{"name":"ScrollBarEnabled"}{% endAi2Property %}
  {% Ai2Property %}{"name":"ScrollBarEnabled", "getter":false}{% endAi2Property %}
* 滚动位置
  {% Ai2Property %}{"name":"ScrollPosition"}{% endAi2Property %}
* 允许用户操作滚动布局
  {% Ai2Property %}{"name":"UserControl"}{% endAi2Property %}
  {% Ai2Property %}{"name":"UserControl", "getter":false}{% endAi2Property %}

## 垂直滚动布局管理器 VerticalScrollHandler

### 事件（垂直）

* 向下过度拖动
  {% Ai2Event %}{"name":"OverScrollDown", "param":["displacement"], "componentName":"VerticalScrollHandler1"}{% endAi2Event %}
* 向上过度拖动
  {% Ai2Event %}{"name":"OverScrollUp", "param":["displacement"]}{% endAi2Event %}
* 布局滚动到最底端
  {% Ai2Event %}{"name":"ReachBottom"}{% endAi2Event %}
* 布局滚动到最顶端
  {% Ai2Event %}{"name":"ReachTop"}{% endAi2Event %}
* 布局发生滚动
  {% Ai2Event %}{"name":"ScrollChanged", "param":["scrollY"]}{% endAi2Event %}
* 布局被按下
  {% Ai2Event %}{"name":"TouchDown"}{% endAi2Event %}
* 布局被松开
  {% Ai2Event %}{"name":"TouchUp"}{% endAi2Event %}

### 方法（垂直）

* 向上进行半页滚动
  {% Ai2Method %}{"name":"ArrowScrollDownward"}{% endAi2Method %}
* 向右进行半页滚动
  {% Ai2Method %}{"name":"ArrowScrollUpward"}{% endAi2Method %}
* 向上进行整页滚动
  {% Ai2Method %}{"name":"PageScrollDownward"}{% endAi2Method %}
* 向下进行整页滚动
  {% Ai2Method %}{"name":"PageScrollUpward"}{% endAi2Method %}
* 绑定垂直滚动布局
  {% Ai2Method %}{"name":"RegisterScrollView", "param":["verticalScrollArrangement"]}{% endAi2Method %}
* 滚动到最低端
  {% Ai2Method %}{"name":"ScrollBottom"}{% endAi2Method %}
* 滚动一段距离
  {% Ai2Method %}{"name":"ScrollBy", "param":["px"]}{% endAi2Method %}
* 滚动到指定位置
  {% Ai2Method %}{"name":"ScrollTo", "param":["px"]}{% endAi2Method %}
* 滚动到最顶端
  {% Ai2Method %}{"name":"ScrollTop"}{% endAi2Method %}
* 平滑的滚动一段距离
  {% Ai2Method %}{"name":"SmoothScrollBy", "param":["px"]}{% endAi2Method %}
* 平滑的滚动到指定位置
  {% Ai2Method %}{"name":"SmoothScrollTo", "param":["px"]}{% endAi2Method %}
* ** 参数解释： **
  * px - 滚动的距离。向下为正，向上为负

### 属性（垂直）

* 显示渐变边缘
  {% Ai2Property %}{"name":"FadingEdgeEnabled"}{% endAi2Property %}
  {% Ai2Property %}{"name":"FadingEdgeEnabled", "getter":false}{% endAi2Property %}
* 最大滚动位置 - MaxScrollPosition
  {% Ai2Property %}{"name":"MaxScrollPosition"}{% endAi2Property %}
* 过度滚动动画样式
  * 0 - 总是允许过度滚动
  * 1（默认） - 当布局可以被有效滚动时才允许过度滚动
  * 2 - 禁止过度滚动
  * **（在不同版本的系统中过度滚动动画看起来可能会不太一样）**
  {% Ai2Property %}{"name":"OverScrollMode"}{% endAi2Property %}
  {% Ai2Property %}{"name":"OverScrollMode", "getter":false}{% endAi2Property %}
* 显示滚动条 - ScrollBarEnabled
  {% Ai2Property %}{"name":"ScrollBarEnabled"}{% endAi2Property %}
  {% Ai2Property %}{"name":"ScrollBarEnabled", "getter":false}{% endAi2Property %}
* 当前滚动位置 - ScrollPosition
  {% Ai2Property %}{"name":"ScrollPosition"}{% endAi2Property %}
* 允许用户操作滚动布局 - UserControl
  {% Ai2Property %}{"name":"UserControl"}{% endAi2Property %}
  {% Ai2Property %}{"name":"UserControl", "getter":false}{% endAi2Property %}

### 下载地址

* 最后更新 2017.12.25 (v3)
* <a href="/aix/cn.colintree.aix.ScrollArrangementHandlers.aix" target="_blank">下载1(本站)</a>