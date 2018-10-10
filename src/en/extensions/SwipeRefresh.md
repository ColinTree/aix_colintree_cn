# SwipeRefresh

---

Swipe it, and refresh it.

## Event

* Refresh
  {% Ai2Event %}{"name":"Refresh", "componentName":"SwipeRefresh1"}{% endAi2Event %}

## Methods

* CancelRefreshing
  {% Ai2Method %}{"name":"CancelRefreshing"}{% endAi2Method %}
* RegisterArrangement
  {% Ai2Method %}{"name":"RegisterArrangement", "param":["arrangement"]}{% endAi2Method %}
* RegisterListView
  {% Ai2Method %}{"name":"RegisterListView", "param":["listView"]}{% endAi2Method %}

  P.S. Choose only one register method for each SwipeRefresh component. Once an arrangement(or a listview) is successfully registered to a SwipeRefresh compoent, any other register called will be ignored.

* Recommended Colors, by Material Design

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

## Properties

* BackgroundColor - color of the process spinner
  {% Ai2Property %}{"name":"BackgroundColor"}{% endAi2Property %}
  {% Ai2Property %}{"name":"BackgroundColor", "getter":false}{% endAi2Property %}
* ColorList - for the refreshing animation, with a order of displaying.
  {% Ai2Property %}{"name":"ColorList"}{% endAi2Property %}
  {% Ai2Property %}{"name":"ColorList", "getter":false}{% endAi2Property %}
* DragEnd - The offset in pixels from the top of this view at which the progress spinner should come to rest after a successful swipe gesture.
  {% Ai2Property %}{"name":"DragEnd"}{% endAi2Property %}
  {% Ai2Property %}{"name":"DragEnd", "getter":false}{% endAi2Property %}
* DragScale - Setting it to true will cause indicator to be scaled up rather than clipped.
  {% Ai2Property %}{"name":"DragScale"}{% endAi2Property %}
  {% Ai2Property %}{"name":"DragScale", "getter":false}{% endAi2Property %}
* DragStart - The offset in pixels from the top of this view at which the progress spinner should appear.
  {% Ai2Property %}{"name":"DragStart"}{% endAi2Property %}
  {% Ai2Property %}{"name":"DragStart", "getter":false}{% endAi2Property %}
* Enabled
  {% Ai2Property %}{"name":"Enabled"}{% endAi2Property %}
  {% Ai2Property %}{"name":"Enabled", "getter":false}{% endAi2Property %}
* NestedScrollingEnabled
  {% Ai2Property %}{"name":"NestedScrollingEnabled"}{% endAi2Property %}
  {% Ai2Property %}{"name":"NestedScrollingEnabled", "getter":false}{% endAi2Property %}
* Refreshing
  {% Ai2Property %}{"name":"Refreshing"}{% endAi2Property %}
  {% Ai2Property %}{"name":"Refreshing", "getter":false}{% endAi2Property %}
* SizeLarge
  {% Ai2Property %}{"name":"SizeLarge"}{% endAi2Property %}
  {% Ai2Property %}{"name":"SizeLarge", "getter":false}{% endAi2Property %}

## Download

* Last update 2018.7.28 (v2)
* <a href="/aix/cn.colintree.aix.SwipeRefresh.aix" target="_blank">Mirror 1 (This website)</a>
* [Mirror 2 (Github release)](https://github.com/OpenSourceAIX/SwipeRefresh/releases)
* [Source Code](https://github.com/OpenSourceAIX/SwipeRefresh)

## Sample

* [Sample aia](https://github.com/ColinTree/aix_colintree_cn/releases/download/SwipeRefreshTest/SwipeRefreshTest_en.aia)   
* [Sample apk](https://github.com/ColinTree/aix_colintree_cn/releases/download/SwipeRefreshTest/SwipeRefreshTest_en_appinventor.apk) by AppInventor  
* [Sample apk](https://github.com/ColinTree/aix_colintree_cn/releases/download/SwipeRefreshTest/SwipeRefreshTest_en_thunkable.apk) by Thunkable  

![](../images/SwipeRefresh/Screenshot_appinventor.png)
![](../images/SwipeRefresh/Screenshot_thunkable.png)