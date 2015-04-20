# 使用说明 [![spm version](http://spmjs.io/badge/newmap)](http://spmjs.io/package/newmap)

- order 2
---

newmap module

## 安装

```
$ spm install newmap --save
```
## 样式依赖
````html
<link rel="stylesheet" href="http://www.newmapgis.com/coder/dev/jsExs/api/newmap.css">
 同时div需要具备高度宽度属性
````

## 使用

```js
require('newmap');
        //地图类实例化
        var    map = new NMap("map", { zoom: 1, center: new NXY(116, 39) });
        //图层参数设置	
        var lyrOptionswmts = {
        	tileSize: new NXY(256, 256),
        	tileOrigin: new NXY(-180, 90),
        	resolutions: [0.087890625, 0.0439453125, 0.02197265625, 0.010986328125],
        	format: "image/png",
        	units: "dd",
        	projection: "EPSG:4326",
        	maxExtent: new NBounds(73.406586, 3.4084773, 135.085830688477, 53.8809503125),
        	serverResolutions: { "0": 0.087890625, "1": 0.0439453125, "2": 0.02197265625, "3": 0.010986328125 },
        	layer: "sample1",
        	style: "Default",
        	serviceMode: 'RESTful',
        	tileMatrixSet: "TileMatrixSet_0"
        };
        //NWMTSLayer类实例化
        layer1 = new NWMTSLayer("WMTS", "http://" + "211.168.132.61:8724" + "/newmap/ogc/samples/chinatile/wmts", lyrOptionswmts);
        //图层添加到地图
        map.addLayer(layer1);
        //移动到中心点和缩放级别
        map.moveTo(new NXY(116, 39), 1);
        //缩放平移
        map.setMode("dragzoom");
        ```
