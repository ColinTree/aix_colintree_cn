# Asynchronous Image Loader - AsyncImageLoader

---

Do not need to get stuck while loading online image! 

## Events

* ImageLoadFailed
  {% Ai2Event %}{"name":"ImageLoadFailed", "componentName":"AsyncImageLoader1", "param": ["component","path"]}{% endAi2Event %}
* ImageLoaded (Succeed)
  {% Ai2Event %}{"name":"ImageLoaded", "param": ["component","path"]}{% endAi2Event %}
  
## Methods

* SetArrangementImage (TableArrangement has not a Image property, so it is not supported)
  {% Ai2Method %}{"name":"SetArrangementImage", "param":["layoutArrangement","path"]}{% endAi2Method %}
* SetButtonBaseImage (Button, DatePicker, ListPicker, and TimePicker are supproted)
  {% Ai2Method %}{"name":"SetButtonBaseImage", "param":["buttonBaseComponent","path"]}{% endAi2Method %}
* SetImagePicture (For Image only)
  {% Ai2Method %}{"name":"SetImagePicture", "param":["imageComponent","path"]}{% endAi2Method %}

  (Totally 9 components supported)  
  P.S. these methods can set up the background image, but the `Image` property will not be changed  
  e.g. I set a online picture to a empty Image comopnent through `SetImagePicture`, but the property Image.Picture is still empty though the component has already get a picture.

## Download

* Last update 2017.9.24
* <a href="/aix/cn.colintree.aix.AsyncImageLoader.aix" target="_blank">Mirror 1 (This website)</a>

## Sample

* [Sample aia](https://github.com/ColinTree/aix_colintree_cn/releases/download/AsyncImageLoaderTest/AsyncImageLoaderTest_en.aia)   
* [Sample apk](https://github.com/ColinTree/aix_colintree_cn/releases/download/AsyncImageLoaderTest/AsyncImageLoaderTest_en.apk) 

while the app is running in a same network environment, the result has a large difference  
![](../images/AsyncImageLoader/Sample_Screenshot.png)

* Using component propertes make the screen stop responsing for a while, until all the images are loaded (1.3 second stucking in screenshot)  
  ![](../images/AsyncImageLoader/Sample_Raw.png)
* Using extension to set up the images, it just takes about 0.58 second to load, and not getting stuck  
  ![](../images/AsyncImageLoader/Sample_Extension.png)