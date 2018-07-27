# Custom ListView - ColinTreeListView *

---

Higher level "ListView", using extensions!

* Update on 2018.7.27 (Version 10):
  * Added Get **by [@10MINT](https://github.com/10MINT)**
  * Added LastLongClickedElement **by [@10MINT](https://github.com/10MINT)**
  * Fixes label cannot click on some platforms

* Update on 2018.3.10 (Version 9):
  * Fixed Error of Visiblility
  * Added ClearCache(path) & ClearAllCache() -- still in test, it should works

* Update on 2018.3.4 (Version 8)
  * Fixed extraButtonEnabled not implemented
  * Added support of direct(static) functions in ColinTreeListViewElement

* Update on 2018.2.25 (Version 7) **THANK YOU [@User81](https://community.thunkable.com/u/User81) FOR SPONSORING**:
  * Fixed that lastClickedElement starts from 0
  * Fixed that images that cached by a same path would act wired when one of them is clicked
  * Added a extra button
  * Added property handler for every single element of the listview -> *[useage](#colintreelistviewelement)*  
    ![](../images/ColinTreeListView/cap_v7_elementHandler.png)

* Update on 2018.2.11 (Version 6):
  * Added properties of text height (both main- & sub-text)

* Update on 2018.1.31 (Version 5):
  * Added icon text related properties
  * Added lastClickedElement & lastClickedIcon

* Update on 2017.12.30 (Version 4):
  * Adapted to all platforms (ai2.appinventor.mit.edu , thunkable , etc.) There should not more NoSuchMethodError at anywhere.

* Update on 2017.12.29 (version 3):
  * Adapted to new Appinventor (since 2017.12.27, Companion 2.45) (Fixed NoSuchMethodError)
  * Added properties related to image loading - AsyncImageLoad & CacheImage (that in a same path)
  * Added property - ScrollBottomAfterAdd

## How to use

1. Left a VerticalArrangement or a VerticalScrollArrangement, set the width and the height as you like.  
  Here is the sample:  
  ![](../images/ColinTreeListView/DesignPageScreenshot.png)

2. Before do anything like add a element, initialize it first:  
  Choose **only one** of the initialize method  
  ![](../images/ColinTreeListView/initialize.png)

3. Set the list  
  The "set" method required a list, and the list elements can be: 

  * **Single text element without icon**:  
    The list element here is just a Text, and it will be shown in the element
  * **Single text element without icon**(same with the one above):  
    A sub-list with only one item is also allowed when creating a Single text element without icon.
  * **Single text element with icon**:  
    The sub-list with two item will be proceed as a Single text element with icon.  
    The first item is the icon path, when the second one is the text here.
  * **Double text element with icon**:  
    A list with at least three item, is being recognize as a Double text elemtnt with icon.
    And only the very first three items will be used as the parameters here.
    They are: icon(path), Main-text, and Sub-text

  **The three types of list element can exist when a ColinTreeListView is created**

  Sample code:  
  ![](../images/ColinTreeListView/SetCode.png)  
  Runtime screenshot (IconMultiParams checked):  
  ![](../images/ColinTreeListView/SetCodeScreenshot.png)

## Events

* Element events:
  * ElementClick
    {% Ai2Event %}{"name":"ElementClick", "param":["elementIndex"], "componentName":"ColinTreeListView1"}{% endAi2Event %}
    * *related property: LastClickedIcon*
      {% Ai2Property %}{"name":"LastClickedIcon"}{% endAi2Property %}
  * ElementLongClick
    {% Ai2Event %}{"name":"ElementLongClick", "param":["elementIndex"]}{% endAi2Event %}
    * *related property: LastLongClickedElement*
      {% Ai2Property %}{"name":"LastLongClickedElement"}{% endAi2Property %}
  * ElementTouchDown
    {% Ai2Event %}{"name":"ElementTouchDown", "param":["elementIndex"]}{% endAi2Event %}
  * ElementTouchUp
    {% Ai2Event %}{"name":"ElementTouchUp", "param":["elementIndex"]}{% endAi2Event %}

* ExtraButton events:
  * ExtraButtonClick
    {% Ai2Event %}{"name":"ExtraButtonClick", "param":["elementIndex"]}{% endAi2Event %}
    * *related property: LastClickedExtraButton*
      {% Ai2Property %}{"name":"LastClickedExtraButton"}{% endAi2Property %}
  * ExtraButtonLongClick
    {% Ai2Event %}{"name":"ExtraButtonLongClick", "param":["elementIndex"]}{% endAi2Event %}
  * ExtraButtonTouchDown
    {% Ai2Event %}{"name":"ExtraButtonTouchDown", "param":["elementIndex"]}{% endAi2Event %}
  * ExtraButtonTouchUp
    {% Ai2Event %}{"name":"ExtraButtonTouchUp", "param":["elementIndex"]}{% endAi2Event %}

* Element icon events:
  * IconClick
    {% Ai2Event %}{"name":"IconClick", "param":["elementIndex"]}{% endAi2Event %}
    * *related property: LastClickedIcon*
      {% Ai2Property %}{"name":"LastClickedIcon"}{% endAi2Property %}
  * IconLongClick
    {% Ai2Event %}{"name":"IconLongClick", "param":["elementIndex"]}{% endAi2Event %}
  * IconTouchDown
    {% Ai2Event %}{"name":"IconTouchDown", "param":["elementIndex"]}{% endAi2Event %}
  * IconTouchUp
    {% Ai2Event %}{"name":"IconTouchUp", "param":["elementIndex"]}{% endAi2Event %}

## Methods

* List operations:
  * AddElement
    {% Ai2Method %}{"name":"AddElement", "param":["element"]}{% endAi2Method %}
  * AddEmptyElement
    {% Ai2Method %}{"name":"AddEmptyElement"}{% endAi2Method %}
  * Clear
    {% Ai2Method %}{"name":"Clear"}{% endAi2Method %}
  * Get
    {% Ai2Method %}{"name":"Get", "output":true}{% endAi2Method %}
  * GetElement
    {% Ai2Method %}{"name":"GetElement", "param":["elementIndex"], "output":true}{% endAi2Method %}
  * Initialize
    {% Ai2Method %}{"name":"Initialize", "param":["verticalArrangement"]}{% endAi2Method %}
  * Initialize_Scroll (using the VerticalScrollArrangement)
    {% Ai2Method %}{"name":"Initialize_Scroll", "param":["verticalScrollArrangement"]}{% endAi2Method %}
  * RemoveElement
    {% Ai2Method %}{"name":"RemoveElement", "param":["elementIndex"]}{% endAi2Method %}
  * Set
    {% Ai2Method %}{"name":"Set", "param":["list"]}{% endAi2Method %}

* Element operations:
  * SetElement
    {% Ai2Method %}{"name":"SetElement", "param":["elementIndex", "element"]}{% endAi2Method %}
  * SetElementIcon
    {% Ai2Method %}{"name":"SetElementIcon", "param":["elementIndex", "path"]}{% endAi2Method %}
  * SetElementMainText
    {% Ai2Method %}{"name":"SetElementMainText", "param":["elementIndex", "mainText"]}{% endAi2Method %}
  * SetElementSubText
    {% Ai2Method %}{"name":"SetElementSubText", "param":["elementIndex", "subText"]}{% endAi2Method %}
  * SetElementText
    {% Ai2Method %}{"name":"SetElementText", "param":["elementIndex", "text"]}{% endAi2Method %}

* Other operations:
  * ClearAllCache
    {% Ai2Method %}{"name":"ClearAllCache"}{% endAi2Method %}
  * ClearCache
    {% Ai2Method %}{"name":"ClearCache", "param":["path"]}{% endAi2Method %}

## Properties

ColinTreeListView provide the real-time list layout modifing through properties  
And the properties are: (the order of the properties cannot be control by code, sorry for the mess here)  

* AsyncImageLoad - load image in a asynchronous way
  {% Ai2Property %}{"name":"AsyncImageLoad"}{% endAi2Property %}
  {% Ai2Property %}{"name":"AsyncImageLoad", "getter":false}{% endAi2Property %}
* CacheImage - cache image by file path, in order to avoid wasting time and memory
  {% Ai2Property %}{"name":"CacheImage"}{% endAi2Property %}
  {% Ai2Property %}{"name":"CacheImage", "getter":false}{% endAi2Property %}
* ElementHeight - Height of elements
  {% Ai2Property %}{"name":"ElementHeight"}{% endAi2Property %}
  {% Ai2Property %}{"name":"ElementHeight", "getter":false}{% endAi2Property %}
* ExtraButtonBgColor
  {% Ai2Property %}{"name":"ExtraButtonBgColor"}{% endAi2Property %}
  {% Ai2Property %}{"name":"ExtraButtonBgColor", "getter":false}{% endAi2Property %}
* ExtraButtonEnabled - default as false, if you need a extra button, please check it (set it to true).
  {% Ai2Property %}{"name":"ExtraButtonEnabled"}{% endAi2Property %}
  {% Ai2Property %}{"name":"ExtraButtonEnabled", "getter":false}{% endAi2Property %}
* ExtraButtonHeight
  {% Ai2Property %}{"name":"ExtraButtonHeight"}{% endAi2Property %}
  {% Ai2Property %}{"name":"ExtraButtonHeight", "getter":false}{% endAi2Property %}
* ExtraButtonImage
  {% Ai2Property %}{"name":"ExtraButtonImage"}{% endAi2Property %}
  {% Ai2Property %}{"name":"ExtraButtonImage", "getter":false}{% endAi2Property %}
* ExtraButtonPaddings
  {% Ai2Property %}{"name":"ExtraButtonPaddings"}{% endAi2Property %}
  {% Ai2Property %}{"name":"ExtraButtonPaddings", "getter":false}{% endAi2Property %}
* ExtraButtonShape
  {% Ai2Property %}{"name":"ExtraButtonShape"}{% endAi2Property %}
  {% Ai2Property %}{"name":"ExtraButtonShape", "getter":false}{% endAi2Property %}
* ExtraButtonText - I would not support seting text of extra button of each elements :P
  {% Ai2Property %}{"name":"ExtraButtonText"}{% endAi2Property %}
  {% Ai2Property %}{"name":"ExtraButtonText", "getter":false}{% endAi2Property %}
* ExtraButtonTextFontBold
  {% Ai2Property %}{"name":"ExtraButtonTextFontBold"}{% endAi2Property %}
  {% Ai2Property %}{"name":"ExtraButtonTextFontBold", "getter":false}{% endAi2Property %}
* ExtraButtonTextFontSize
  {% Ai2Property %}{"name":"ExtraButtonTextFontSize"}{% endAi2Property %}
  {% Ai2Property %}{"name":"ExtraButtonTextFontSize", "getter":false}{% endAi2Property %}
* ExtraButtonWidth  
  {% Ai2Property %}{"name":"ExtraButtonWidth"}{% endAi2Property %}
  {% Ai2Property %}{"name":"ExtraButtonWidth", "getter":false}{% endAi2Property %}
* IconBgColor
  {% Ai2Property %}{"name":"IconBgColor"}{% endAi2Property %}
  {% Ai2Property %}{"name":"IconBgColor", "getter":false}{% endAi2Property %}
* IconHeight
  {% Ai2Property %}{"name":"IconHeight"}{% endAi2Property %}
  {% Ai2Property %}{"name":"IconHeight", "getter":false}{% endAi2Property %}
* IconMultiParams - if this is checked, new format (introduced since Version 5) `path||iconText` would be available. Value like `Photoshop.png||P` will be displayed as a Text `P` on image `Photoshop.png`
  {% Ai2Property %}{"name":"IconMultiParams"}{% endAi2Property %}
  {% Ai2Property %}{"name":"IconMultiParams", "getter":false}{% endAi2Property %}
* IconPaddings - for larger space of text displaying
  {% Ai2Property %}{"name":"IconPaddings"}{% endAi2Property %}
  {% Ai2Property %}{"name":"IconPaddings", "getter":false}{% endAi2Property %}
* IconShape - same as one of buttons
  {% Ai2Property %}{"name":"IconShape"}{% endAi2Property %}
  {% Ai2Property %}{"name":"IconShape", "getter":false}{% endAi2Property %}
* IconTextColor
  {% Ai2Property %}{"name":"IconTextColor"}{% endAi2Property %}
  {% Ai2Property %}{"name":"IconTextColor", "getter":false}{% endAi2Property %}
* IconTextFontBold
  {% Ai2Property %}{"name":"IconTextFontBold"}{% endAi2Property %}
  {% Ai2Property %}{"name":"IconTextFontBold", "getter":false}{% endAi2Property %}
* IconTextFontSize
  {% Ai2Property %}{"name":"IconTextFontSize"}{% endAi2Property %}
  {% Ai2Property %}{"name":"IconTextFontSize", "getter":false}{% endAi2Property %}
* IconWidth  
  {% Ai2Property %}{"name":"IconWidth"}{% endAi2Property %}
  {% Ai2Property %}{"name":"IconWidth", "getter":false}{% endAi2Property %}
* ScrollBottomAfterAdd - Scroll to bottom after an element is added - (using delay to make sure listview has been re-rendered)
  {% Ai2Property %}{"name":"ScrollBottomAfterAdd"}{% endAi2Property %}
  {% Ai2Property %}{"name":"ScrollBottomAfterAdd", "getter":false}{% endAi2Property %}
* SubTextColor
  {% Ai2Property %}{"name":"SubTextColor"}{% endAi2Property %}
  {% Ai2Property %}{"name":"SubTextColor", "getter":false}{% endAi2Property %}
* SubTextFontBold
  {% Ai2Property %}{"name":"SubTextFontBold"}{% endAi2Property %}
  {% Ai2Property %}{"name":"SubTextFontBold", "getter":false}{% endAi2Property %}
* SubTextFontSize
  {% Ai2Property %}{"name":"SubTextFontSize"}{% endAi2Property %}
  {% Ai2Property %}{"name":"SubTextFontSize", "getter":false}{% endAi2Property %}
* SubTextHeight (-1 for auto, -2 for fill parent)
  {% Ai2Property %}{"name":"SubTextHeight"}{% endAi2Property %}
  {% Ai2Property %}{"name":"SubTextHeight", "getter":false}{% endAi2Property %}
* TextColor
  {% Ai2Property %}{"name":"TextColor"}{% endAi2Property %}
  {% Ai2Property %}{"name":"TextColor", "getter":false}{% endAi2Property %}
* TextFontBold
  {% Ai2Property %}{"name":"TextFontBold"}{% endAi2Property %}
  {% Ai2Property %}{"name":"TextFontBold", "getter":false}{% endAi2Property %}
* TextFontSize
  {% Ai2Property %}{"name":"TextFontSize"}{% endAi2Property %}
  {% Ai2Property %}{"name":"TextFontSize", "getter":false}{% endAi2Property %}
* TextHeight (-1 for auto, -2 for fill parent)  
  {% Ai2Property %}{"name":"TextHeight"}{% endAi2Property %}
  {% Ai2Property %}{"name":"TextHeight", "getter":false}{% endAi2Property %}
* TouchDownColor - Color when element is touch down, default alpha is 136/255, about 53%
  {% Ai2Property %}{"name":"TouchDownColor"}{% endAi2Property %}
  {% Ai2Property %}{"name":"TouchDownColor", "getter":false}{% endAi2Property %}
* UnderlineColor - An underline is the line between two elements
  {% Ai2Property %}{"name":"UnderlineColor"}{% endAi2Property %}
  {% Ai2Property %}{"name":"UnderlineColor", "getter":false}{% endAi2Property %}
* UnderlineWidth
  {% Ai2Property %}{"name":"UnderlineWidth"}{% endAi2Property %}
  {% Ai2Property %}{"name":"UnderlineWidth", "getter":false}{% endAi2Property %}
* WidthAfterIcon
  {% Ai2Property %}{"name":"WidthAfterIcon"}{% endAi2Property %}
  {% Ai2Property %}{"name":"WidthAfterIcon", "getter":false}{% endAi2Property %}
* WidthBeforeExtraButton
  {% Ai2Property %}{"name":"WidthBeforeExtraButton"}{% endAi2Property %}
  {% Ai2Property %}{"name":"WidthBeforeExtraButton", "getter":false}{% endAi2Property %}
* WidthBeforeIcon  
  {% Ai2Property %}{"name":"WidthBeforeIcon"}{% endAi2Property %}
  {% Ai2Property %}{"name":"WidthBeforeIcon", "getter":false}{% endAi2Property %}

**Attached: the color when element is touch down**  
![](../images/ColinTreeListView/TouchDownScreenshot.png)


## ColinTreeListViewElement

This is a handler for every single element in the listView.

**Note: Before use any property, please link to a element by calling `LinkToElement`**  
![](../images/ColinTreeListView/linkToElement.png)

Properties that not exist in ListView:

* UseGlobalProperties - default as False, if you want the properties of this element not to be refresh when the ListView properties changed, please set this to True.
  {% Ai2Property %}{"name":"UseGlobalProperties", "componentName":"ColinTreeListViewElement1"}{% endAi2Property %}
  {% Ai2Property %}{"name":"UseGlobalProperties", "getter":false}{% endAi2Property %}
* ElementBackgroundColor
  {% Ai2Property %}{"name":"ElementBackgroundColor"}{% endAi2Property %}
  {% Ai2Property %}{"name":"ElementBackgroundColor", "getter":false}{% endAi2Property %}

## Download  

* Last update 2018.7.27 (v10)
* <a href="/aix/cn.colintree.aix.ColinTreeListView.aix" target="_blank">Mirror 1 (This website)</a>
* [Mirror 2 (Github release)](https://github.com/OpenSourceAIX/ColinTreeListView/releases)
* [Source Code](https://github.com/OpenSourceAIX/ColinTreeListView)

## [Need more features?](ListViewCustomize.md)