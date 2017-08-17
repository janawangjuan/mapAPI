
# mapAPI
> 本人百度地图  AK：mddPsKQzaQpMajMHnvKEHR8UfiFl4PsG

> 建议小伙伴重新申请！！！！

## 主机屋位置地图坐标展示

1、百度地图开发者平台申请秘钥   （http://lbsyun.baidu.com/）

2、认证开发者身份，申请个人 AK   

3、选择对应开发平台，调用接口  (一般开发选择 “浏览器”)

4、通过百度地图拾取坐标系统，进行准确定位  （http://api.map.baidu.com/lbsapi/getpoint/index.html）

5、新建地图页面，直接复制百度地图API具体页面代码 （mapAPI.html）

5、新建显示页面，通过 iframe 标签 引入具体地图页面，注意设置iframe的宽高为100%

## 具体代码示例

* 设置地图的页面（mapAPI.html）

```
<!DOCTYPE html>
<html>
<head>
	<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
	<meta name="viewport" content="initial-scale=1.0, user-scalable=no" />
	<style type="text/css">
            <!--默认样式，可根据具体需求进行修改，但不建议对其修改-->
	    body, html,#allmap {
                width: 100%;
                height: 100%;
                overflow: hidden;
                margin:0;
                font-family:"微软雅黑";
            }
	</style>
	<script type="text/javascript" src="http://api.map.baidu.com/api?v=2.0&ak=您的密钥"></script>
	<title>百度API--demo</title>
</head>
<body>
	<div id="allmap"></div>
</body>
</html>
<script type="text/javascript">
	/*======百度地图API功能==========*/ 
	var map = new BMap.Map("allmap");

        /*=======需要设置的具体经纬度  116.314423 , 40.042801============*/
	var point = new BMap.Point(116.314423,40.042801);   //启用滚轮放大缩小，默认禁用
	map.enableContinuousZoom();    //启用地图惯性拖拽，默认禁用);
	map.centerAndZoom(point, 15);
	var marker = new BMap.Marker(point);  // 创建标注
	map.addOverlay(marker);               // 将标注添加到地图中
	marker.setAnimation(BMAP_ANIMATION_BOUNCE); //跳动的动画
  
      map.enableScrollWheelZoom();   //启用滚轮放大缩小，默认禁用
	map.enableContinuousZoom();    //启用地图惯性拖拽，默认禁用


        //创建地址图片（公司logo）
	var pt = new BMap.Point(116.417, 39.909);
	var myIcon = new BMap.Icon ("http://lbsyun.baidu.com/jsdemo/img/fox.gif", new BMap.Size(300,157));
	var marker2 = new BMap.Marker(pt,{icon:myIcon});  // 创建标注
	map.addOverlay(marker2);              // 将标注添加到地图中
  
</script>

```

* 地图显示页面

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>地图显示页面</title>
    <style>
        .containers {
            width: 1200px;
            height: 600px;
            margin:80px auto;
            border: 1px solid #000;
        }
        h1 {
            text-align: center;
        }
        #ifr {
            width: 100%;
            height: 100%;
        }
    </style>
</head>
<body>
<h1>地图显示页面</h1>
<div class="containers">
    <iframe id="ifr" src="./mapAPI.html" frameborder="0"></iframe>
</div>
</body>
</html>

```

















