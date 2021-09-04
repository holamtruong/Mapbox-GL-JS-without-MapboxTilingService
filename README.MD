







In December 2020, the Mapbox GL JS license change sent shock waves through the web mapping industry. In essence, the new library version Mapbox GL JS v2 is not free anymore [  (Breaking changes v2.0.0)](https://github.com/mapbox/mapbox-gl-js/releases/tag/v2.0.0). A billable map load occurs whenever a Map object is initialized. My example is a simple way to remove the Mapbox Vector Tiles API serves vector tiles or paying for tiles. 

 Thanks for the idea from the article: https://markallengis.medium.com/simple-web-map-using-mapbox-gl-js-a44e583e0589

 [DEMO HERE](https://holamtruong.github.io/mapbox-gl-js-without-MapboxTilingService)


![](https://github.com/holamtruong/mapbox-gl-js-without-accesstoken/blob/master/demo2.PNG?raw=true)


```js
        // accessToken
        mapboxgl.accessToken =
            'pk.eyJ1IjoibWFwYm94IiwiYSI6ImNpejY4NXVycTA2emYycXBndHRqcmZ3N3gifQ.rJcFIG214AriISLbB6B5aw';

        var map = new mapboxgl.Map({
            container: 'map',
            // Remove the Mapbox Vector Tiles API serves vector tiles
            //style: 'mapbox://styles/mapbox/streets-v9',
            center: [106.3705298, 10.2338635],
            zoom: 15,
            style: {
                'version': 8,
                'sources': {
                    'raster-tiles': {
                        'type': 'raster',
                        'tiles': [
                        // Add a third party tile server:
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
