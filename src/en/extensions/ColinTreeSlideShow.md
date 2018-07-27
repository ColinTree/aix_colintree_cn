# SlideShow (Carousel) - ColinTreeSlideShow

---

Using one extension component to finish this job!  

* Update on 2017.9.24 (Version 2)
  * Merged [AsyncImageLoader](AsyncImageLoader). No more stucking when load online image
  * [GitHub Release](https://github.com/ColinTree/aix_colintree_cn/releases/tag/ColinTreeSlideShow_v2)

* Release on 2017.9.17 (Version 1)
  [GitHub Release](https://github.com/ColinTree/aix_colintree_cn/releases/tag/ColinTreeSlideShow)

## How to use

1. Left a HorizontalScrollArrangement, set the width and the height as you like  
   (there is a known bug that when the arrangement's size changed, the slides are still that size, it causes problems)  

   Example: (The BG Color can be set here)  
   ![](../images/ColinTreeSlideShow/DesignPageScreenshot.png)

2. Register the horizontalScrollArrangement:
  {% Ai2Method %}{"name":"RegisterScrollView", "param":["horizontalScrollArrangement"], "componentName":"ColinTreeSlideShow1"}{% endAi2Method %}

3. Add photos:
  {% Ai2Method %}{"name":"AddPhoto", "param":["path"]}{% endAi2Method %}

## Events

* AutoSwipe (before scroll start)
  {% Ai2Event %}{"name":"AutoSwipe"}{% endAi2Event %}
* AutoSwiped (after scroll finished)
  {% Ai2Event %}{"name":"AutoSwiped"}{% endAi2Event %}
* SlideClick
  {% Ai2Event %}{"name":"SlideClick", "param":["slideIndex"]}{% endAi2Event %}
* Swipe (before scroll start)
  {% Ai2Event %}{"name":"Swipe"}{% endAi2Event %}
* Swiped (after scroll finished)
  {% Ai2Event %}{"name":"Swiped"}{% endAi2Event %}
* ImageLoaded (added in v2)
  {% Ai2Event %}{"name":"ImageLoaded"}{% endAi2Event %}
* ImageLoadFailed (added in v2)
  {% Ai2Event %}{"name":"ImageLoadFailed"}{% endAi2Event %}

## Methods

* AddPhoto
  {% Ai2Method %}{"name":"AddPhoto", "param":["path"]}{% endAi2Method %}
* AtFirstSlide
  {% Ai2Method %}{"name":"AtFirstSlide", "output":true}{% endAi2Method %}
* AtLastSlide
  {% Ai2Method %}{"name":"AtLastSlide", "output":true}{% endAi2Method %}
* ChangePhoto
  {% Ai2Method %}{"name":"ChangePhoto", "param":["slideIndex","path"]}{% endAi2Method %}
* GoFirstSlide
  {% Ai2Method %}{"name":"GoFirstSlide"}{% endAi2Method %}
* GoLastSlide
  {% Ai2Method %}{"name":"GoLastSlide"}{% endAi2Method %}
* GoNextSlide
  {% Ai2Method %}{"name":"GoNextSlide"}{% endAi2Method %}
* GoPrevSlide
  {% Ai2Method %}{"name":"GoPrevSlide"}{% endAi2Method %}
* RegisterScrollView
  {% Ai2Method %}{"name":"RegisterScrollView", "param":["horizontalScrollArrangement"]}{% endAi2Method %}

## Properties

* AutoScrollEnabled
  {% Ai2Property %}{"name":"AutoScrollEnabled", "getter":true, "componentName":"ColinTreeSlideShow1"}{% endAi2Property %}
  {% Ai2Property %}{"name":"AutoScrollEnabled", "getter":false}{% endAi2Property %}
* CurrentSlide
  {% Ai2Property %}{"name":"CurrentSlide"}{% endAi2Property %}
  {% Ai2Property %}{"name":"CurrentSlide", "getter":false}{% endAi2Property %}
* DragThreshold
  * The value is from 0~1, same as 0%~100%, default as 0.2. After user drag the slides, when the displacement is larger the threshold value (Width * DragThreshold), ColinTreeSlideShow will scroll to the intent slide automatically
  * Example
    * The arrangement of the slideshow is 300px, DragThreshold is 0.2. After user drag the slides rightward for 70px, as 70 > 300*0.2=60, the slideshow would scroll to the previous slide
  {% Ai2Property %}{"name":"DragThreshold"}{% endAi2Property %}
  {% Ai2Property %}{"name":"DragThreshold", "getter":false}{% endAi2Property %}
* ScrollRightward - (auto-Scroll rightward when checked, leftward when not checked)
  {% Ai2Property %}{"name":"ScrollRightward"}{% endAi2Property %}
  {% Ai2Property %}{"name":"ScrollRightward", "getter":false}{% endAi2Property %}
* TimerInterval (Unit: millisecond, 1s=1000ms) - Control when the slideshow should auto-Scroll
  {% Ai2Property %}{"name":"TimerInterval"}{% endAi2Property %}
  {% Ai2Property %}{"name":"TimerInterval", "getter":false}{% endAi2Property %}

* ImageWhileLoading (added in v2) - would not display with blocks

## Download

* Last update 2017.9.24 (v2)
* <a href="/aix/cn.colintree.aix.ColinTreeSlideshow.aix" target="_blank">Mirror 1 (This website)</a>
* [Sample aia](https://github.com/ColinTree/aix_colintree_cn/releases/download/ColinTreeSlideShow_v2/ColinTreeSlideshowTest.aia)  
* [Sample apk](https://github.com/ColinTree/aix_colintree_cn/releases/download/ColinTreeSlideShow_v2/ColinTreeSlideshowTest_appinventor.apk) - Appinventor  
* [Sample apk](https://github.com/ColinTree/aix_colintree_cn/releases/download/ColinTreeSlideShow_v2/ColinTreeSlideshowTest_thunkable.apk) - Thunkable