This is a simple way to remove the Mapbox account or paying for tiles. 
Thanks for the idea from the article: https://markallengis.medium.com/simple-web-map-using-mapbox-gl-js-a44e583e0589

[DEMO HERE](https://holamtruong.github.io/mapbox-gl-js-without-accesstoken/)

![](https://github.com/holamtruong/mapbox-gl-js-without-accesstoken/blob/master/demo.PNG?raw=true)


```js
    var map = new mapboxgl.Map({
        container: 'map',
        //style: 'mapbox://styles/mapbox/streets-v9',
        center: [106.3705298, 10.2338635],
        zoom: 15,
        style: {
            'version': 8,
            'sources': {
                'raster-tiles': {
                    'type': 'raster',
                    'tiles': [
                        //'https://stamen-tiles.a.ssl.fastly.net/terrain/{z}/{x}/{y}.jpg'
                        'https://mt0.google.com/vt/lyrs=p&hl=en&x={x}&y={y}&z={z}'
                    ],
                    'tileSize': 256,
                }
            },
            'layers': [{
                'id': 'simple-tiles',
                'type': 'raster',
                'source': 'raster-tiles',
                'minzoom': 0,
                'maxzoom': 22
            }]
        }
    });
```
