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
