# 文本输入框提示 - AutoCompleteBox

---

自动输入，让你的文本输入框更聪明！

* 2018.1.4更新（V2）：
  * 新增事件：下拉选项被点击 - AfterSelect


## 组件设计属性

* 使用Appinventor时勾选 (关系到组件样式) - ForAppinventor

  ![](../images/AutoCompleteBox/property.png)

## 事件

* 下拉选项被点击
  {% Ai2Event %}{"name":"AfterSelect", "componentName":"AutoCompleteBox1", "param":["textbox","selection"]}{% endAi2Event %}

## 方法

* 获取自动输入列表
  {% Ai2Method %}{"name":"GetCompletion", "param":["textbox"], "output": true}{% endAi2Method %}
* 设置自动输入列表
  {% Ai2Method %}{"name":"SetCompletion", "param":["textbox","list"]}{% endAi2Method %}

## 样例

![](../images/AutoCompleteBox/code.png)
![](../images/AutoCompleteBox/capture.png)

## 下载地址

* 最后更新 2018.1.4
* <a href="/aix/cn.colintree.aix.AutoCompleteBox.aix" target="_blank">下载1(本站)</a>
