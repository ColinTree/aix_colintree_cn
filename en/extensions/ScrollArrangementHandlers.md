# Scroll Arrangement Handlers (v2+)

---

This extension package included two extensions. Horizontal Scroll Arrangement Handler(HorizontalScrollHandler) AND Vertical Scroll Arrangement Handler(VerticalScrollHandler).

* Update on 2017.12.25 (Version 3)
  * Fixed that the events of VerticalScrollHandler are not called when it should be called.
  * Fixed that event ScrollChanged of VerticalScrollHandler provides a incorrect data
  * Fixed that ScrollPosition, MaxScrollPosition in different unit (i mess up android dx & appinventor px before)  
    and related events should works well now (like ReachBottom)
  * Fixed that OverScrollMode does not affect the actual behaviour (for both Vertical and Horizontal)
  * Added Overscroll events
  * Merry Christmas!

* Update on 2017.9.29 (Version 2)
  * Fixed problem that names of methods & events not match the standard. (Extension renamed to avoid confusing)
  * Component icons added
  * FadingEdgeEnabled (Property)
  * OverScrollMode (Property)
  * ScrollBarEnabled (Property)
  * UserControl (Property)
  * MaxScrollPosition (Property)
  * ScrollPosition (Property)

* Update on 2017.8.26:
  * Added TouchUp (Event)

## Horizontal Scroll Arrangement Handler (HorizontalScrollHandler)

### h-Events

* OverScrollLeft (dragged leftward)
  {% Ai2Event %}{"name":"OverScrollLeft", "param":["displacement"], "componentName":"HorizontalScrollHandler1"}{% endAi2Event %}
* OverScrollRight (dragged rightward)
  {% Ai2Event %}{"name":"OverScrollRight", "param":["displacement"]}{% endAi2Event %}
* ReachLeftEnd
  {% Ai2Event %}{"name":"ReachLeftEnd"}{% endAi2Event %}
* ReachRightEnd
  {% Ai2Event %}{"name":"ReachRightEnd"}{% endAi2Event %}
* ScrollChanged
  {% Ai2Event %}{"name":"ScrollChanged", "param":["scrollX"]}{% endAi2Event %}
* TouchDown
  {% Ai2Event %}{"name":"TouchDown"}{% endAi2Event %}
* TouchUp
  {% Ai2Event %}{"name":"TouchUp"}{% endAi2Event %}

### h-Methods

* ArrowScrollLeftward (half-width)
  {% Ai2Method %}{"name":"ArrowScrollLeftward"}{% endAi2Method %}
* ArrowScrollRightward (half-width)
  {% Ai2Method %}{"name":"ArrowScrollRightward"}{% endAi2Method %}
* PageScrollLeftward (full-width)
  {% Ai2Method %}{"name":"PageScrollLeftward"}{% endAi2Method %}
* PageScrollRightward (full-width)
  {% Ai2Method %}{"name":"PageScrollRightward"}{% endAi2Method %}
* RegisterScrollView
  {% Ai2Method %}{"name":"RegisterScrollView", "param":["horizontalScrollArrangement"]}{% endAi2Method %}
* ScrollBy
  {% Ai2Method %}{"name":"ScrollBy", "param":["px"]}{% endAi2Method %}
* ScrollLeftEnd
  {% Ai2Method %}{"name":"ScrollLeftEnd"}{% endAi2Method %}
* ScrollRightEnd
  {% Ai2Method %}{"name":"ScrollRightEnd"}{% endAi2Method %}
* ScrollTo
  {% Ai2Method %}{"name":"ScrollTo", "param":["px"]}{% endAi2Method %}
* SmoothScrollBy
  {% Ai2Method %}{"name":"SmoothScrollBy", "param":["px"]}{% endAi2Method %}
* SmoothScrollTo
  {% Ai2Method %}{"name":"SmoothScrollTo", "param":["px"]}{% endAi2Method %}
* ** parameters: **
  * px - the displacement of scrolling. positive if scrolling rightward, and negative if scrolling leftward

### h-Properties

* FadingEdgeEnabled
  {% Ai2Property %}{"name":"FadingEdgeEnabled"}{% endAi2Property %}
  {% Ai2Property %}{"name":"FadingEdgeEnabled", "getter":false}{% endAi2Property %}
* MaxScrollPosition
  {% Ai2Property %}{"name":"MaxScrollPosition"}{% endAi2Property %}
* OverScrollMode
  * 0 - Always allow a user to over-scroll this view, provided it is a view that can scroll.
  * 1 (default) - Allow a user to over-scroll this view only if the content is large enough to meaningfully scroll, provided it is a view that can scroll.
  * 2 - Never allow a user to over-scroll this view.
  * **(This may looks different in different version of system)**
  {% Ai2Property %}{"name":"OverScrollMode"}{% endAi2Property %}
  {% Ai2Property %}{"name":"OverScrollMode", "getter":false}{% endAi2Property %}
* ScrollBarEnabled
  {% Ai2Property %}{"name":"ScrollBarEnabled"}{% endAi2Property %}
  {% Ai2Property %}{"name":"ScrollBarEnabled", "getter":false}{% endAi2Property %}
* ScrollPosition - current scroll position
  {% Ai2Property %}{"name":"ScrollPosition"}{% endAi2Property %}
* UserControl - Allow user to drag the scroll arrangement (or not)
  {% Ai2Property %}{"name":"UserControl"}{% endAi2Property %}
  {% Ai2Property %}{"name":"UserControl", "getter":false}{% endAi2Property %}

## Vertical Scroll Arrangement Handler (VerticalScrollHandler)

### v-Events

* OverScrollDown (dragged downward)
  {% Ai2Event %}{"name":"OverScrollDown", "param":["displacement"], "componentName":"VerticalScrollHandler1"}{% endAi2Event %}
* OverScrollUp (dragged upward)
  {% Ai2Event %}{"name":"OverScrollUp", "param":["displacement"]}{% endAi2Event %}
* ReachBottom
  {% Ai2Event %}{"name":"ReachBottom"}{% endAi2Event %}
* ReachTop
  {% Ai2Event %}{"name":"ReachTop"}{% endAi2Event %}
* ScrollChanged
  {% Ai2Event %}{"name":"ScrollChanged", "param":["scrollY"]}{% endAi2Event %}
* TouchDown
  {% Ai2Event %}{"name":"TouchDown"}{% endAi2Event %}
* TouchUp
  {% Ai2Event %}{"name":"TouchUp"}{% endAi2Event %}

### v-Methods

* ArrowScrollDownward
  {% Ai2Method %}{"name":"ArrowScrollDownward"}{% endAi2Method %}
* ArrowScrollUpward
  {% Ai2Method %}{"name":"ArrowScrollUpward"}{% endAi2Method %}
* PageScrollDownward
  {% Ai2Method %}{"name":"PageScrollDownward"}{% endAi2Method %}
* PageScrollUpward
  {% Ai2Method %}{"name":"PageScrollUpward"}{% endAi2Method %}
* RegisterScrollView
  {% Ai2Method %}{"name":"RegisterScrollView", "param":["verticalScrollArrangement"]}{% endAi2Method %}
* ScrollBottom
  {% Ai2Method %}{"name":"ScrollBottom"}{% endAi2Method %}
* ScrollBy
  {% Ai2Method %}{"name":"ScrollBy", "param":["px"]}{% endAi2Method %}
* ScrollTo
  {% Ai2Method %}{"name":"ScrollTo", "param":["px"]}{% endAi2Method %}
* ScrollTop
  {% Ai2Method %}{"name":"ScrollTop"}{% endAi2Method %}
* SmoothScrollBy
  {% Ai2Method %}{"name":"SmoothScrollBy", "param":["px"]}{% endAi2Method %}
* SmoothScrollTo
  {% Ai2Method %}{"name":"SmoothScrollTo", "param":["px"]}{% endAi2Method %}
* ** parameters: **
  * px - the displacement of scrolling. positive if scrolling downward, and negative if scrolling upward

### v-Properties

* FadingEdgeEnabled
  {% Ai2Property %}{"name":"FadingEdgeEnabled"}{% endAi2Property %}
  {% Ai2Property %}{"name":"FadingEdgeEnabled", "getter":false}{% endAi2Property %}
* MaxScrollPosition
  {% Ai2Property %}{"name":"MaxScrollPosition"}{% endAi2Property %}
* OverScrollMode
  * 0 - Always allow a user to over-scroll this view, provided it is a view that can scroll.
  * 1 (default) - Allow a user to over-scroll this view only if the content is large enough to meaningfully scroll, provided it is a view that can scroll.
  * 2 - Never allow a user to over-scroll this view.
  * **(This may looks different in different version of system)**
  {% Ai2Property %}{"name":"OverScrollMode"}{% endAi2Property %}
  {% Ai2Property %}{"name":"OverScrollMode", "getter":false}{% endAi2Property %}
* ScrollBarEnabled
  {% Ai2Property %}{"name":"ScrollBarEnabled"}{% endAi2Property %}
  {% Ai2Property %}{"name":"ScrollBarEnabled", "getter":false}{% endAi2Property %}
* ScrollPosition
  {% Ai2Property %}{"name":"ScrollPosition"}{% endAi2Property %}
* UserControl - Allow user to drag the scroll arrangement (or not)
  {% Ai2Property %}{"name":"UserControl"}{% endAi2Property %}
  {% Ai2Property %}{"name":"UserControl", "getter":false}{% endAi2Property %}

## Download

* Last update 2017.12.25 (v3)
* <a href="/aix/cn.colintree.aix.ScrollArrangementHandlers.aix" target="_blank">Mirror 1 (This website)</a>