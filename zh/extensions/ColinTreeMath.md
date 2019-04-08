# 数学拓展 - ColinTreeMath *

---

所有功能与“数学运算库拓展组件”相同，区别为函数名字进行了压缩
比如GreatestCommonDivisor(最大公约数)缩短为GCD，减小代码占用面积

* 2019.4.6更新（V2）：
  * 修复了奇数平方数会被判定为质数的问题

## 方法

* 平均数 - 返回列表中所有数字的平均数
  {% Ai2Method %}{"name":"Average", "output":true, "param":["list"], "componentName":"ColinTreeMath1"}{% endAi2Method %}
* 立方根
  {% Ai2Method %}{"name":"CbRt", "output":true, "param":["number"]}{% endAi2Method %}
* 最大公约数
  {% Ai2Method %}{"name":"GCD", "output":true, "param":["number1","number2"]}{% endAi2Method %}
* 最小公倍数
  {% Ai2Method %}{"name":"LCM", "output":true, "param":["number1","number2"]}{% endAi2Method %}
* Log10 - 返回Log<sub>10</sub>`参数number`
  {% Ai2Method %}{"name":"Log10", "output":true, "param":["number"]}{% endAi2Method %}
* 返回列表中最大的数字
  {% Ai2Method %}{"name":"Max", "output":true, "param":["list"]}{% endAi2Method %}
* 返回列表中最小的数字
  {% Ai2Method %}{"name":"Min", "output":true, "param":["list"]}{% endAi2Method %}
* 圆周率*π*
  {% Ai2Method %}{"name":"Pi", "output":true}{% endAi2Method %}
* 求幂 - 返回number的n次方
  {% Ai2Method %}{"name":"Power", "output":true, "param":["number","n"]}{% endAi2Method %}
* 判断质数
  {% Ai2Method %}{"name":"Prime", "output":true, "param":["number"]}{% endAi2Method %}
* 平方根倒数 - 1/&#8730;(number)
  {% Ai2Method %}{"name":"ROTSR", "output":true, "param":["number"]}{% endAi2Method %}
* 升序排序 - 使用冒泡排序
  {% Ai2Method %}{"name":"SortAscend", "output":true, "param":["list"]}{% endAi2Method %}
* 降序排序 - 使用冒泡排序
  {% Ai2Method %}{"name":"SortDecend", "output":true, "param":["list"]}{% endAi2Method %}
* e - 自然对数*e*
  {% Ai2Method %}{"name":"e", "output":true}{% endAi2Method %}
* 平方和的根 - &#8730;(number1<sup>2</sup>+number2<sup>2</sup>)
  {% Ai2Method %}{"name":"hypot", "output":true, "param":["number1","number2"]}{% endAi2Method %}

## 下载地址

* 最后更新 2019.4.6
* <a href="/aix/cn.colintree.aix.ColinTreeMath-v2.aix" target="_blank">下载1(本站)</a>
* [下载2（自动编译）](https://github.com/OpenSourceAIX/ColinTreeMath/releases/download/v2/binary.zip)
* [源代码](https://github.com/OpenSourceAIX/ColinTreeMath)