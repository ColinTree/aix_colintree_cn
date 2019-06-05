# 自定义列表显示 - ColinTreeListView *

---

更高级的“列表显示框”，通过拓展组件动态实现！

* 2019.6.5更新 (V11)：
  * 添加了组件内翻译（需要平台支持）
  * 修复了一个Get获取所有列表项的问题 **感谢[@10MINT](https://github.com/10MINT)的代码**
  * 添加了ColinTreeListViewElement中的ExtraButtonImage **部分代码由[@mkakozbeklem](https://github.com/mkakozbeklem)完成**
  * 取消了有些代码块被弃用的设定

* 2018.7.27更新（V10）：
  * 新增了Get获取所有列表项 **感谢[@10MINT](https://github.com/10MINT) 的PR**
  * 新增了LastLongClickedElement 最后被长按的列表项的编号 **感谢[@10MINT](https://github.com/10MINT) 的PR**
  * 修复了部分平台上部分列表项无法被点击的问题

* 2018.3.10更新（V9）：
  * 修复了显示Visible属性有关的错误
  * 新增了ClearCache(path)-清除缓存 & ClearAllCache()-清除所有缓存 的块 -- 虽说仍在测试中，但应可以达到效果的

* 2018.2.25更新（V8）：
  * 修复了ExtraButtonEnabled没作用的问题
  * 新增了ColinTreeListViewElement中直接设置列表项属性的方法

* 2018.2.25更新（V7） **感谢 [@User81](https://community.thunkable.com/u/User81) 的赞助**:
  * 修复了lastClickedElement从0开始算的问题
  * 修复了同路径缓存图被点击时就会触发的奇怪bug
  * 新增了个小图标
  * 新增了一个列表项处理组件 -> *[查看文档](#colintreelistviewelement)*  
    ![](../images/ColinTreeListView/cap_v7_elementHandler.png)

* 2018.2.11更新（V6）：
  * 新增了两个文本高度属性

* 2018.1.31更新（V5）：
  * 新增了图标文字的相关属性
  * 新增了 最后被点击的列表项的编号(lastClickedElement) 和 最后被点击的图标的列表项编号(lastClickedIcon) 属性

* 2017.12.30更新（V4）：
  * 适配全平台（ai2.appinventor.mit.edu, thunkable, etc.) 应该彻底没有NoSuchMethod的问题了

* 2017.12.29更新（V3）：
  * 适配了2017.12.27新版本Appinventor（伴侣版本 2.45）（解决NoSuchMethod的问题）
  * 新增了图片相关的加载策略属性 - 异步加载图片（AsyncImageLoad） & 缓存同名文件（CacheImage）
  * 新增了自动滚动到底部的属性选项 - ScrollBottomAfterAdd

## 基本使用流程

1. 为该组件预留一个空的 垂直布局 或 垂直滚动布局，将宽高设置好  
  如图：  
  ![](../images/ColinTreeListView/DesignPageScreenshot.png)

2. 在添加列表项之前先初始化一下，调用传入一个参数：  
  图中两种方法选其中一个即可  
  ![](../images/ColinTreeListView/initialize.png)

3. 设置列表的内容：  
  其中，列表（list）这个参数是一个二维的列表（大列表套小列表），列表项可以为：

  * **无图标单文本列表项**：  
    直接一个文本作为列表项，则为列表显示项的文本
  * **无图标单文本列表项**（效果同上一个）：  
    一个列表，只有一个列表项，则这个列表项（文本）即为列表显示项的文本。显示效果与上一种相同
  * **带图标单文本列表项**：  
    一个列表有两个项，则依次对应：列表项图标路径 和 列表项文字
  * **带图标双文本列表项**：  
    一个列表有三个项，则依次对应：列表项图标路径、列表项主文字 和 列表项副文字

  **各种列表项可以在一个列表中共存，并按照各自的规则显示**

  代码样例如图：  
  ![](../images/ColinTreeListView/SetCode.png)  
  对应显示效果（列表项图标复合参数已勾选）：  
  ![](../images/ColinTreeListView/SetCodeScreenshot.png)

## 事件

* 列表项事件：
  * 列表项被点击
    {% Ai2Event %}{"name":"ElementClick", "param":["elementIndex"], "componentName":"ColinTreeListView1"}{% endAi2Event %}
    * *相关属性: 最后一次被点击的列表项（的编号）
      {% Ai2Property %}{"name":"LastClickedElement"}{% endAi2Property %}
  * 列表项被长按
    {% Ai2Event %}{"name":"ElementLongClick", "param":["elementIndex"]}{% endAi2Event %}
    * 相关属性: 最后一次被长按的列表项（的列表项编号）
      {% Ai2Property %}{"name":"LastLongClickedElement"}{% endAi2Property %}
  * 列表项被按下
    {% Ai2Event %}{"name":"ElementTouchDown", "param":["elementIndex"]}{% endAi2Event %}
  * 列表项被松开
    {% Ai2Event %}{"name":"ElementTouchUp", "param":["elementIndex"]}{% endAi2Event %}

* 小图标事件：
  * 图标被点击
    {% Ai2Event %}{"name":"ExtraButtonClick", "param":["elementIndex"]}{% endAi2Event %}
    * 相关属性: 最后一次被点击的小图标（的列表项编号）
      {% Ai2Property %}{"name":"LastClickedExtraButton"}{% endAi2Property %}
  * 图标被长按
    {% Ai2Event %}{"name":"ExtraButtonLongClick", "param":["elementIndex"]}{% endAi2Event %}
  * 图标被按下
    {% Ai2Event %}{"name":"ExtraButtonTouchDown", "param":["elementIndex"]}{% endAi2Event %}
  * 图标被松开
    {% Ai2Event %}{"name":"ExtraButtonTouchUp", "param":["elementIndex"]}{% endAi2Event %}

* 列表图标事件（列表左边图标）：
  * 图标被点击
    {% Ai2Event %}{"name":"IconClick", "param":["elementIndex"]}{% endAi2Event %}
    * *相关属性: 最后一次被点击的图标（的列表项编号）
      {% Ai2Property %}{"name":"LastClickedIcon"}{% endAi2Property %}
  * 图标被长按
    {% Ai2Event %}{"name":"IconLongClick", "param":["elementIndex"]}{% endAi2Event %}
  * 图标被按下
    {% Ai2Event %}{"name":"IconTouchDown", "param":["elementIndex"]}{% endAi2Event %}
  * 图标被松开
    {% Ai2Event %}{"name":"IconTouchUp", "param":["elementIndex"]}{% endAi2Event %}

## 方法

* 列表处理：
  * 添加列表项
    {% Ai2Method %}{"name":"AddElement", "param":["element"]}{% endAi2Method %}
  * 添加空列表项
    {% Ai2Method %}{"name":"AddEmptyElement"}{% endAi2Method %}
  * 清空列表
    {% Ai2Method %}{"name":"Clear"}{% endAi2Method %}
  * 获取所有列表项的内容(返回列表)
    {% Ai2Method %}{"name":"Get", "output":true}{% endAi2Method %}
  * 获取列表项的内容(返回列表)
    {% Ai2Method %}{"name":"GetElement", "param":["elementIndex"], "output":true}{% endAi2Method %}
  * 初始化
    {% Ai2Method %}{"name":"Initialize", "param":["verticalArrangement"]}{% endAi2Method %}
  * 初始化(使用滚动布局)
    {% Ai2Method %}{"name":"Initialize_Scroll", "param":["verticalScrollArrangement"]}{% endAi2Method %}
  * 移除列表项
    {% Ai2Method %}{"name":"RemoveElement", "param":["elementIndex"]}{% endAi2Method %}
  * 设置列表内容
    {% Ai2Method %}{"name":"Set", "param":["list"]}{% endAi2Method %}
  * ** 参数解释： **
    * element - 列表项内容
    * elementIndex - 列表项编号，从1开始算

* 单个列表项控制：
  * 设置单个列表项
    {% Ai2Method %}{"name":"SetElement", "param":["elementIndex", "element"]}{% endAi2Method %}
  * 设置单个列表项的图标
    {% Ai2Method %}{"name":"SetElementIcon", "param":["elementIndex", "path"]}{% endAi2Method %}
  * 设置单个列表项的主文本
    {% Ai2Method %}{"name":"SetElementMainText", "param":["elementIndex", "mainText"]}{% endAi2Method %}
  * 设置单个列表项的副文本
    {% Ai2Method %}{"name":"SetElementSubText", "param":["elementIndex", "subText"]}{% endAi2Method %}
  * 设置单个列表项的文本
    {% Ai2Method %}{"name":"SetElementText", "param":["elementIndex", "text"]}{% endAi2Method %}
  * ** 参数解释： **
    * element - 列表项内容
    * elementIndex - 列表项编号，从1开始算

* 其他操作
  * 清除所有图片缓存
    {% Ai2Method %}{"name":"ClearAllCache"}{% endAi2Method %}
  * 清除单张图片缓存
    {% Ai2Method %}{"name":"ClearCache", "param":["path"]}{% endAi2Method %}

## 组件属性

ColinTreeListView提供了可以供实时更改的列表效果  
其中可供修改的属性有（这些属性的顺序不受代码控制，略微凌乱）：  

* 异步加载图片
  {% Ai2Property %}{"name":"AsyncImageLoad"}{% endAi2Property %}
  {% Ai2Property %}{"name":"AsyncImageLoad", "getter":false}{% endAi2Property %}
* 缓存同名文件
  {% Ai2Property %}{"name":"CacheImage"}{% endAi2Property %}
  {% Ai2Property %}{"name":"CacheImage", "getter":false}{% endAi2Property %}
* 单个列表项的高度 - ElementHeight
  {% Ai2Property %}{"name":"ElementHeight"}{% endAi2Property %}
  {% Ai2Property %}{"name":"ElementHeight", "getter":false}{% endAi2Property %}
* 小图标背景颜色
  {% Ai2Property %}{"name":"ExtraButtonBgColor"}{% endAi2Property %}
  {% Ai2Property %}{"name":"ExtraButtonBgColor", "getter":false}{% endAi2Property %}
* 小图标是否启用 - 默认是不勾选的，如果要启用小图标请勾选此项
  {% Ai2Property %}{"name":"ExtraButtonEnabled"}{% endAi2Property %}
  {% Ai2Property %}{"name":"ExtraButtonEnabled", "getter":false}{% endAi2Property %}
* 小图标高度
  {% Ai2Property %}{"name":"ExtraButtonHeight"}{% endAi2Property %}
  {% Ai2Property %}{"name":"ExtraButtonHeight", "getter":false}{% endAi2Property %}
* 小图标图像
  {% Ai2Property %}{"name":"ExtraButtonImage"}{% endAi2Property %}
  {% Ai2Property %}{"name":"ExtraButtonImage", "getter":false}{% endAi2Property %}
* 小图标内边距
  {% Ai2Property %}{"name":"ExtraButtonPaddings"}{% endAi2Property %}
  {% Ai2Property %}{"name":"ExtraButtonPaddings", "getter":false}{% endAi2Property %}
* 小图标形状 - 同按钮的形状属性
  {% Ai2Property %}{"name":"ExtraButtonShape"}{% endAi2Property %}
  {% Ai2Property %}{"name":"ExtraButtonShape", "getter":false}{% endAi2Property %}
* 小图标文本 - 本拓展将不支持给每个列表项设置不同的小图标文本 :P
  {% Ai2Property %}{"name":"ExtraButtonText"}{% endAi2Property %}
  {% Ai2Property %}{"name":"ExtraButtonText", "getter":false}{% endAi2Property %}
* 小图标字体加粗
  {% Ai2Property %}{"name":"ExtraButtonTextFontBold"}{% endAi2Property %}
  {% Ai2Property %}{"name":"ExtraButtonTextFontBold", "getter":false}{% endAi2Property %}
* 小图标字体大小
  {% Ai2Property %}{"name":"ExtraButtonTextFontSize"}{% endAi2Property %}
  {% Ai2Property %}{"name":"ExtraButtonTextFontSize", "getter":false}{% endAi2Property %}
* 小图标宽度 
  {% Ai2Property %}{"name":"ExtraButtonWidth"}{% endAi2Property %}
  {% Ai2Property %}{"name":"ExtraButtonWidth", "getter":false}{% endAi2Property %}
* 列表项图标背景色
  {% Ai2Property %}{"name":"IconBgColor"}{% endAi2Property %}
  {% Ai2Property %}{"name":"IconBgColor", "getter":false}{% endAi2Property %}
* 列表项图标高度
  {% Ai2Property %}{"name":"IconHeight"}{% endAi2Property %}
  {% Ai2Property %}{"name":"IconHeight", "getter":false}{% endAi2Property %}
* 列表项图标使用复合参数
  * 如果选中这一项，一种新的格式（第5版新增）`图片路径||图标文本` 将会启用。例如 `Photoshop.png||P` 代表着一个图标的图片是 `Photoshop.png` 且上面还写这个 `P`
  {% Ai2Property %}{"name":"IconMultiParams"}{% endAi2Property %}
  {% Ai2Property %}{"name":"IconMultiParams", "getter":false}{% endAi2Property %}
* 列表项图标内边距 - 以确保图标文字能够更优地显示
  {% Ai2Property %}{"name":"IconPaddings"}{% endAi2Property %}
  {% Ai2Property %}{"name":"IconPaddings", "getter":false}{% endAi2Property %}
* 列表项图标形状 - 同按钮的形状属性
  {% Ai2Property %}{"name":"IconShape"}{% endAi2Property %}
  {% Ai2Property %}{"name":"IconShape", "getter":false}{% endAi2Property %}
* 列表项图标字体颜色
  {% Ai2Property %}{"name":"IconTextColor"}{% endAi2Property %}
  {% Ai2Property %}{"name":"IconTextColor", "getter":false}{% endAi2Property %}
* 列表项图标字体加粗
  {% Ai2Property %}{"name":"IconTextFontBold"}{% endAi2Property %}
  {% Ai2Property %}{"name":"IconTextFontBold", "getter":false}{% endAi2Property %}
* 列表项图标字体大小
  {% Ai2Property %}{"name":"IconTextFontSize"}{% endAi2Property %}
  {% Ai2Property %}{"name":"IconTextFontSize", "getter":false}{% endAi2Property %}
* 列表项图标宽度 - IconWidth
  {% Ai2Property %}{"name":"IconWidth"}{% endAi2Property %}
  {% Ai2Property %}{"name":"IconWidth", "getter":false}{% endAi2Property %}
* 添加新的列表项后，滚动到列表最底部（使用了微小的延时以保证列表已经重新渲染）
  {% Ai2Property %}{"name":"ScrollBottomAfterAdd"}{% endAi2Property %}
  {% Ai2Property %}{"name":"ScrollBottomAfterAdd", "getter":false}{% endAi2Property %}
* 副文本的字体颜色
  {% Ai2Property %}{"name":"SubTextColor"}{% endAi2Property %}
  {% Ai2Property %}{"name":"SubTextColor", "getter":false}{% endAi2Property %}
* 副文本字体加粗
  {% Ai2Property %}{"name":"SubTextFontBold"}{% endAi2Property %}
  {% Ai2Property %}{"name":"SubTextFontBold", "getter":false}{% endAi2Property %}
* 副文本字体大小
  {% Ai2Property %}{"name":"SubTextFontSize"}{% endAi2Property %}
  {% Ai2Property %}{"name":"SubTextFontSize", "getter":false}{% endAi2Property %}
* 副文本高度（-1为自适应，-2为填满）
  {% Ai2Property %}{"name":"SubTextHeight"}{% endAi2Property %}
  {% Ai2Property %}{"name":"SubTextHeight", "getter":false}{% endAi2Property %}
* 文本的字体颜色
  {% Ai2Property %}{"name":"TextColor"}{% endAi2Property %}
  {% Ai2Property %}{"name":"TextColor", "getter":false}{% endAi2Property %}
* 文本字体加粗
  {% Ai2Property %}{"name":"TextFontBold"}{% endAi2Property %}
  {% Ai2Property %}{"name":"TextFontBold", "getter":false}{% endAi2Property %}
* 文本字体大小
  {% Ai2Property %}{"name":"TextFontSize"}{% endAi2Property %}
  {% Ai2Property %}{"name":"TextFontSize", "getter":false}{% endAi2Property %}
* 文本高度（-1为自适应，-2为填满）
  {% Ai2Property %}{"name":"TextHeight"}{% endAi2Property %}
  {% Ai2Property %}{"name":"TextHeight", "getter":false}{% endAi2Property %}
* 列表项被按下时的颜 - 默认为白色，透明度136/255，即53%
  {% Ai2Property %}{"name":"TouchDownColor"}{% endAi2Property %}
  {% Ai2Property %}{"name":"TouchDownColor", "getter":false}{% endAi2Property %}
* 列表项分割线的颜色
  {% Ai2Property %}{"name":"UnderlineColor"}{% endAi2Property %}
  {% Ai2Property %}{"name":"UnderlineColor", "getter":false}{% endAi2Property %}
* 列表项分割线的线宽
  {% Ai2Property %}{"name":"UnderlineWidth"}{% endAi2Property %}
  {% Ai2Property %}{"name":"UnderlineWidth", "getter":false}{% endAi2Property %}
* 列表项图标右侧的间距
  {% Ai2Property %}{"name":"WidthAfterIcon"}{% endAi2Property %}
  {% Ai2Property %}{"name":"WidthAfterIcon", "getter":false}{% endAi2Property %}
* 列表项图标左侧的间距
  {% Ai2Property %}{"name":"WidthBeforeIcon"}{% endAi2Property %}
  {% Ai2Property %}{"name":"WidthBeforeIcon", "getter":false}{% endAi2Property %}

** 附列表项被按下时的颜色： **  
![](../images/ColinTreeListView/TouchDownScreenshot.png)


## ColinTreeListViewElement

这是一个用过来处理列表中的任意一个列表项的

**注意：在使用任何其他属性之前，请先使用`LinkToElement`来链接到一个列表项**  
![](../images/ColinTreeListView/linkToElement.png)

以下是ColinTreeListView中没有的选项：

* 跟随列表设置 - 默认是假(False)，如果您希望这个列表项在列表的相关属性改变时不被修改，请设为真(True)
  {% Ai2Property %}{"name":"UseGlobalProperties", "componentName":"ColinTreeListViewElement1"}{% endAi2Property %}
  {% Ai2Property %}{"name":"UseGlobalProperties", "getter":false}{% endAi2Property %}
* 列表项背景色
  {% Ai2Property %}{"name":"ElementBackgroundColor"}{% endAi2Property %}
  {% Ai2Property %}{"name":"ElementBackgroundColor", "getter":false}{% endAi2Property %}

## 下载地址

* 最后更新 2019.6.5 (v11)
* <a href="/aix/cn.colintree.aix.ColinTreeListView.aix" target="_blank">直接下载</a>
* [更新信息](https://github.com/OpenSourceAIX/ColinTreeListView/releases/tag/v11)
* [自动构建文件 binary.zip](https://github.com/OpenSourceAIX/ColinTreeListView/releases/download/v11/binary.zip)
* [源码](https://github.com/OpenSourceAIX/ColinTreeListView)

## [需要更多的功能？](ListViewCustomize.md)