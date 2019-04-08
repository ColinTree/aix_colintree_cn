# 下拉刷新 - SwipeRefresh

---

下拉，刷新，如此简单。

## 事件

* 下拉刷新被触发
  {% Ai2Event %}{"name":"Refresh", "componentName":"SwipeRefresh1"}{% endAi2Event %}

## 方法

* 取消刷新
  {% Ai2Method %}{"name":"CancelRefreshing"}{% endAi2Method %}
* 将下拉刷新注册到布局（仅限滚动布局）
  {% Ai2Method %}{"name":"RegisterArrangement", "param":["arrangement"]}{% endAi2Method %}
* 讲下拉刷新注册到列表
  {% Ai2Method %}{"name":"RegisterListView", "param":["listView"]}{% endAi2Method %}

  P.S. 对于任何一个下拉刷新组件，在两个注册方法中，只选择一个。一旦注册成功，之后调用的注册方法都会被无视。

* Material Design所推荐使用的颜色

  {% Ai2Method %}{"name":"_Color_holo_blue_bright ", "output":true}{% endAi2Method %}
  {% Ai2Method %}{"name":"_Color_holo_blue_dark ", "output":true}{% endAi2Method %}
  {% Ai2Method %}{"name":"_Color_holo_blue_light ", "output":true}{% endAi2Method %}
  {% Ai2Method %}{"name":"_Color_holo_green_dark ", "output":true}{% endAi2Method %}
  {% Ai2Method %}{"name":"_Color_holo_green_light ", "output":true}{% endAi2Method %}
  {% Ai2Method %}{"name":"_Color_holo_orange_dark ", "output":true}{% endAi2Method %}
  {% Ai2Method %}{"name":"_Color_holo_orange_light ", "output":true}{% endAi2Method %}
  {% Ai2Method %}{"name":"_Color_holo_purple ", "output":true}{% endAi2Method %}
  {% Ai2Method %}{"name":"_Color_holo_red_dark ", "output":true}{% endAi2Method %}
  {% Ai2Method %}{"name":"_Color_holo_red_light ", "output":true}{% endAi2Method %}

## 属性

* 背景颜色（下拉显示的圆圈背景的颜色，如果在Appinventor中使用，圆圈周围将不会有立体阴影）
  {% Ai2Property %}{"name":"BackgroundColor"}{% endAi2Property %}
  {% Ai2Property %}{"name":"BackgroundColor", "getter":false}{% endAi2Property %}
* 颜色列表（一个包含一个或以上的颜色的列表，在下拉过程中，所有颜色会按顺序显示在下拉显示的转圈动画中）
  {% Ai2Property %}{"name":"ColorList"}{% endAi2Property %}
  {% Ai2Property %}{"name":"ColorList", "getter":false}{% endAi2Property %}
* 拖动结束点 - 拖动动画的结束点，下拉达到这个点的下拉操作都视为成功的下拉刷新
  {% Ai2Property %}{"name":"DragEnd"}{% endAi2Property %}
  {% Ai2Property %}{"name":"DragEnd", "getter":false}{% endAi2Property %}
* 拖动放大 - 将此项设为真时，下拉圆圈将用逐渐放大的动画代替平滑的滑出
  {% Ai2Property %}{"name":"DragScale"}{% endAi2Property %}
  {% Ai2Property %}{"name":"DragScale", "getter":false}{% endAi2Property %}
* 拖动开始点 - 拖动动画的开始点，拖动开始时圆圈的出现地点
  {% Ai2Property %}{"name":"DragStart"}{% endAi2Property %}
  {% Ai2Property %}{"name":"DragStart", "getter":false}{% endAi2Property %}
* 启用
  {% Ai2Property %}{"name":"Enabled"}{% endAi2Property %}
  {% Ai2Property %}{"name":"Enabled", "getter":false}{% endAi2Property %}
* 启动嵌套滑动
  {% Ai2Property %}{"name":"NestedScrollingEnabled"}{% endAi2Property %}
  {% Ai2Property %}{"name":"NestedScrollingEnabled", "getter":false}{% endAi2Property %}
* 刷新状态
  {% Ai2Property %}{"name":"Refreshing"}{% endAi2Property %}
  {% Ai2Property %}{"name":"Refreshing", "getter":false}{% endAi2Property %}
* 加大圆圈
  {% Ai2Property %}{"name":"SizeLarge"}{% endAi2Property %}
  {% Ai2Property %}{"name":"SizeLarge", "getter":false}{% endAi2Property %}

## 下载地址

* 最后更新 2018.7.28 (v2)
* <a href="/aix/cn.colintree.aix.SwipeRefresh.aix" target="_blank">下载1(本站)</a>
* [下载2(Github release)](https://github.com/OpenSourceAIX/SwipeRefresh/releases)
* [源码](https://github.com/OpenSourceAIX/SwipeRefresh)

## 样例

* [样例aia](https://github.com/ColinTree/aix_colintree_cn/releases/download/SwipeRefreshTest/SwipeRefreshTest_zh.aia)   
* [样例apk](https://github.com/ColinTree/aix_colintree_cn/releases/download/SwipeRefreshTest/SwipeRefreshTest_zh.apk)

![](../images/SwipeRefresh/Screenshot.png)