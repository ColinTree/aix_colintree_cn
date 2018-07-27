# Baidu Translate (API) - BaiduFanyi

---

**Using this extension to get the translate result from Baidu Translate API**  
(Actually this is for the people that cannot access Google in China XD)

[Home page of Baidu Translate API](http://fanyi-api.baidu.com/api/trans/product/index)

## Events

* GotError
  {% Ai2Event %}{"name":"GotError", "param":["text","responseContent"], "componentName":"BaiduFanyi1"}{% endAi2Event %}
* GotResult
  {% Ai2Event %}{"name":"GotResult", "param":["text","result","resultInPairs","translateFrom","translateTo"]}{% endAi2Event %}
* GotResultRaw
  {% Ai2Event %}{"name":"GotResultRaw", "param":["responseCode","responseType","responseContent"]}{% endAi2Event %}

## Methods

* JsonTextDecode - Same as Web.JsonTextDecode
  {% Ai2Method %}{"name":"JsonTextDecode", "param":["jsonText"], "output":true}{% endAi2Method %}
* Translate - returns request pair, canbe ignored
  {% Ai2Method %}{"name":"Translate", "param":["text","translateFrom","translateTo"], "output":true}{% endAi2Method %}

## Properties

* apikey
  {% Ai2Property %}{"name":"apikey"}{% endAi2Property %}
  {% Ai2Property %}{"name":"apikey", "getter":false}{% endAi2Property %}
* appid - required by translate api
  {% Ai2Property %}{"name":"appid"}{% endAi2Property %}
  {% Ai2Property %}{"name":"appid", "getter":false}{% endAi2Property %}

## Download

* Last update 2017.8.5
* <a href="/aix/cn.colintree.aix.Translators.BaiduFanyi.aix" target="_blank">Mirror 1 (This website)</a>
* [Sample aia](https://github.com/ColinTree/aix_colintree_cn/releases/download/BaiduFanyiTest/BaiduFanyiTest.aia)  
* [Sample apk](https://github.com/ColinTree/aix_colintree_cn/releases/download/BaiduFanyiTest/BaiduFanyiTest.apk)  
  ![](../images/BaiduFanyi/aiaRuntimeScreenshot1.png) ![](../images/BaiduFanyi/aiaRuntimeScreenshot2.png)
