# 滚动布局管理器 - ScrollArrangementHandler

---

这个拓展包内包含了两个拓展，水平滚动布局管理器HorizontalScrollArrHandler，和垂直滚动管理器VerticalScrollArrHandler


## 水平滚动布局管理器 HorizontalScrollArrHandler

* 事件：
  * 列表发生滚动 - onScrollChanged
  * 列表滚动到最左端 - onScrollLeftEnd
  * 列表滚动到最右端 - onScrollRightEnd

  ![](/images/ScrollArrangementHandler/HorizontalScrollArrHandler/events.png)

* 方法：
  * 绑定水平滚动布局 - registerScrollView
  * 向左半页滚动 - arrowScrollLeftward
  * 向右半页滚动 - arrowScrollRightward
  * 向左整页滚动 - pageScrollLeftward
  * 向右整页滚动 - pageScrollRightward
  * 滚动到最左 - scrollLeftEnd
  * 滚动到最右 - scrollRightEnd
  * 滚动一段距离 - scrollBy
  * 平滑的滚动一段距离 - smoothScrollBy
  * 滚动到指定位置 - scrollTo
  * 平滑的滚动到指定位置 - smoothScrollTo
  * ** 参数解释： **
    * px - 滚动的距离。向右为正，向左为负

  ![](/images/ScrollArrangementHandler/HorizontalScrollArrHandler/methods.png)


## 垂直滚动布局管理器 VerticalScrollArrHandler

* 事件：
  * 列表滚动到最底端 - onScrollBottom
  * 列表发生滚动 - onScrollChanged
  * 列表滚动到最顶端 - onScrollTop

  ![](/images/ScrollArrangementHandler/VerticalScrollArrHandler/events.png)

* 方法：
  * 绑定垂直滚动布局 - registerScrollView
  * 向上进行半页滚动 - arrowScrollUpward
  * 向右进行半页滚动 - arrowScrollDownward
  * 向上进行整页滚动 - pageScrollUpward
  * 向下进行整页滚动 - pageScrollDownward
  * 滚动到最顶端 - scrollTop
  * 滚动到最低端 - scrollBottom
  * 滚动一段距离 - scrollBy
  * 平滑的滚动一段距离 - smoothScrollBy
  * 滚动到指定位置 - scrollTo
  * 平滑的滚动到指定位置 - smoothScrollTo
  * ** 参数解释： **
    * px - 滚动的距离。向下为正，向上为负

  ![](/images/ScrollArrangementHandler/VerticalScrollArrHandler/methods.png)

### {{ book.lang.Download }}
* {{ book.lang.LastUpdate }} 2017.8.25
* <a href="/aix/cn.colintree.aix.ScrollArrangementHandler.aix" target="_blank">{{ book.lang.Mirror1 }}</a>