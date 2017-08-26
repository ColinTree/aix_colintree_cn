# Scroll Arrangement Handler

---

This extension package included two extensions. Horizontal Scroll Arrangement Handler(HorizontalScrollArrHandler) AND Vertical Scroll Arrangement Handler(VerticalScrollArrHandler).

Update on 2017.8.26:
* added TouchUp event


## Horizontal Scroll Arrangement Handler (HorizontalScrollArrHandler)

* Events
  * onScrollChanged
  * onScrollLeftEnd
  * onScrollRightEnd
  * TouchUp

  ![](/images/ScrollArrangementHandler/HorizontalScrollArrHandler.events.png)

* Method
  * registerScrollView
  * arrowScrollLeftward (half-width)
  * arrowScrollRightward (half-width)
  * pageScrollLeftward (full-width)
  * pageScrollRightward (full-width)
  * scrollLeftEnd
  * scrollRightEnd
  * scrollBy
  * smoothScrollBy
  * scrollTo
  * smoothScrollTo
  * ** parameters: **
    * px - the displacement of scrolling. positive if scrolling rightward, and negative if scrolling leftward

  ![](/images/ScrollArrangementHandler/HorizontalScrollArrHandler.methods.png)


## Vertical Scroll Arrangement Handler (VerticalScrollArrHandler)

* Events
  * onScrollBottom
  * onScrollChanged
  * onScrollTop
  * TouchUp

  ![](/images/ScrollArrangementHandler/VerticalScrollArrHandler.events.png)

* Method
  * registerScrollView
  * arrowScrollUpward
  * arrowScrollDownward
  * pageScrollUpward
  * pageScrollDownward
  * scrollTop
  * scrollBottom
  * scrollBy
  * smoothScrollBy
  * scrollTo
  * smoothScrollTo
  * ** parameters: **
    * px - the displacement of scrolling. positive if scrolling downward, and negative if scrolling upward

  ![](/images/ScrollArrangementHandler/VerticalScrollArrHandler.methods.png)

### {{ book.lang.Download }}
* {{ book.lang.LastUpdate }} 2017.8.26
* <a href="/aix/cn.colintree.aix.ScrollArrangementHandler.aix" target="_blank">{{ book.lang.Mirror1 }}</a>