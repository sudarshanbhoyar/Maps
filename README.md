# 🌍 GeoJSON Maps Repository  

A curated collection of **open GeoJSON files** for borders, maps, and geospatial data.  
**Free to use** under [Creative Commons Attribution 4.0 (CC-BY-4.0)](https://creativecommons.org/licenses/by/4.0/).  

---

## 📂 Repository Contents  
- `/Country`  
  - `India.geojson` - National boundaries  
- `/States`  
  - `Maharashtra.geojson` - State-level data  
- `/Cities`  
  - `Mumbai.geojson` - City polygons  

*(Add more files as needed!)*  

---

## 🛠️ How to Use  

### 1. **Direct Raw URL** (for OpenLayers/Leaflet)  
```javascript
// OpenLayers example
new ol.layer.Vector({
    source: new ol.source.Vector({
        url: 'https://raw.githubusercontent.com/your-username/repo-name/main/Country/India.geojson',
        format: new ol.format.GeoJSON()
    })
});

### 1. **Direct Raw URL** (for OpenLayers/Leaflet)  
```HTML


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Map of India with Black Boundary</title>
    <link rel="stylesheet" href="https://openlayers.org/en/v6.15.1/css/ol.css" />
    <style>
        body {
            margin: 0;
            padding: 0;
            font-family: Arial, sans-serif;
        }
        #map {
            height: 100vh;
            width: 100%;
        }
    </style>
</head>
<body>
    <div id="map"></div>
    <script src="https://openlayers.org/en/v6.15.1/build/ol.js"></script>
    <script>
        // Initialize the map
        const map = new ol.Map({
            target: 'map',
            layers: [
                // Google Hybrid tiles (Note: May require API key for production)
                new ol.layer.Tile({
                    source: new ol.source.XYZ({
                        url: 'https://mt1.google.com/vt/lyrs=y&x={x}&y={y}&z={z}',
                        attributions: '© Google Maps'
                    })
                }),
                // Vector layer for India's boundary from Data{Meet} GeoJSON
                new ol.layer.Vector({
                    source: new ol.source.Vector({
                        url: 'https://raw.githubusercontent.com/sudarshanbhoyar/maps/main/India/India.geojson',
                        format: new ol.format.GeoJSON({
                            dataProjection: 'EPSG:4326', // GeoJSON is in EPSG:4326
                            featureProjection: 'EPSG:3857' // Transform to map projection
                        })
                    }),
                    style: new ol.style.Style({
                        stroke: new ol.style.Stroke({
                            color: '#000000', // Black outline
                            width: 1 // Thicker outline for visibility
                        }),
                        fill: null // Transparent fill (no fill)
                    })
                })
            ],
            view: new ol.View({
                center: ol.proj.fromLonLat([78.9629, 20.5937]), // Center on India
                zoom: 5
            })
        });

        // Add error handling for GeoJSON loading
        const vectorSource = map.getLayers().getArray()[1].getSource();
        vectorSource.on('featuresloaderror', function () {
            console.error('Failed to load GeoJSON file. Check the URL or file format.');
        });
        vectorSource.on('featuresloadend', function () {
            console.log('GeoJSON file loaded successfully.');
        });
    </script>
</body>
</html>
