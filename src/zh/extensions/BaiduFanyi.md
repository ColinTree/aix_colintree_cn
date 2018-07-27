# 百度翻译Api - BaiduFanyi

---

**直接向百度翻译api获取想要的翻译结果！**  
[百度官方api首页](http://fanyi-api.baidu.com/api/trans/product/index)

## 事件

* 获取翻译期间发生错误
  {% Ai2Event %}{"name":"GotError", "param":["text","responseContent"], "componentName":"BaiduFanyi1"}{% endAi2Event %}
* 得到翻译
  {% Ai2Event %}{"name":"GotResult", "param":["text","result","resultInPairs","translateFrom","translateTo"]}{% endAi2Event %}
* 翻译服务器原始响应
  {% Ai2Event %}{"name":"GotResultRaw", "param":["responseCode","responseType","responseContent"]}{% endAi2Event %}

## 方法

* 解码Json文本 - 功能和Web客户端.解码Json文本 功能相同
  {% Ai2Method %}{"name":"JsonTextDecode", "param":["jsonText"], "output":true}{% endAi2Method %}
* 翻译文本 - 方法返回的是翻译请求头，可以忽略
  {% Ai2Method %}{"name":"Translate", "param":["text","translateFrom","translateTo"], "output":true}{% endAi2Method %}

## 属性

* apikey
  {% Ai2Property %}{"name":"apikey"}{% endAi2Property %}
  {% Ai2Property %}{"name":"apikey", "getter":false}{% endAi2Property %}
* appid
  {% Ai2Property %}{"name":"appid"}{% endAi2Property %}
  {% Ai2Property %}{"name":"appid", "getter":false}{% endAi2Property %}

## 下载地址

* 最后更新 2017.8.5
* <a href="/aix/cn.colintree.aix.Translators.BaiduFanyi.aix" target="_blank">下载1(本站)</a>
* [样例aia](https://github.com/ColinTree/aix_colintree_cn/releases/download/BaiduFanyiTest/BaiduFanyiTest.aia)  
  [使用广州电教馆服务器打开（请先登录）](http://app.gzjkw.net/?repo=aix.colintree.cn/templates/BaiduFanyiTest/BaiduFanyiTest.asc)
* [样例apk](https://github.com/ColinTree/aix_colintree_cn/releases/download/BaiduFanyiTest/BaiduFanyiTest.apk)  
  ![](../images/BaiduFanyi/aiaRuntimeScreenshot1.png) ![](../images/BaiduFanyi/aiaRuntimeScreenshot2.png)