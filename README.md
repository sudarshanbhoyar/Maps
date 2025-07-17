<?xml version="1.0" encoding="UTF-8"?>
<repository>
    <name>GeoJSON Maps Collection</name>
    <description>
        <![CDATA[
        A curated collection of GeoJSON files for maps, boundaries, and geospatial data.
        Free to use under **Creative Commons Attribution 4.0 (CC-BY-4.0)**.
        ]]>
    </description>

    <license type="CC-BY-4.0">
        <summary>
            You are free to:
            - Share — copy and redistribute the material.
            - Adapt — remix, transform, and build upon the material.
            - Attribute — Credit the original author(s).
        </summary>
        <link>https://creativecommons.org/licenses/by/4.0/</link>
    </license>

    <usage>
        <![CDATA[
        ## How to Use
        1. **Direct Raw Links** (for OpenLayers/Leaflet):
           ```javascript
           new ol.layer.Vector({
               source: new ol.source.Vector({
                   url: 'https://raw.githubusercontent.com/{user}/{repo}/{branch}/{file}.geojson',
                   format: new ol.format.GeoJSON()
               })
           });
           ```
        2. **Download** files manually via GitHub.
        3. **Edit** with [geojson.io](https://geojson.io).
        ]]>
    </usage>

    <structure>
        <![CDATA[
        ## Repository Structure
        ```
        /Country
        │   └── India.geojson       # National boundaries
        /States
        │   └── Maharashtra.geojson # State-level data
        /Cities
            └── Mumbai.geojson     # City polygons
        ```
        ]]>
    </structure>

    <contributions>
        <![CDATA[
        ## Contributing
        - Submit issues for missing regions.
        - Fork + Pull Request to add new GeoJSON files.
        ]]>
    </contributions>

    <credits>
        <author>Your Name</author>
        <link href="https://github.com/abc/Maps"/>
    </credits>
</repository>
