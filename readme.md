                        Asheville Air Quality and City Limits Map


This project visualizes Asheville Air Quality (Ozone) and Asheville City Limits using Leaflet and GeoJSON data. The map displays points representing ozone levels across Asheville, NC, and overlays the city's boundaries. It includes a color-coded legend for ozone levels, a scale bar, and popups showing detailed information.

Project Features
Interactive Map: A map centered on Asheville, NC, with zoom and pan functionality.
Ozone Level Visualization: Points representing ozone levels, color-coded based on the AQI (Air Quality Index).
City Limits Polygon: Displays the boundaries of Asheville's city limits.
Legend: A legend explaining the color codes for different ozone levels.
Scale Bar: A scale bar showing distances on the map.
Popup Information: Displays additional data (ozone levels, location names) when clicking on points.
Setup
1. Clone or Download the Repository
You can clone the repository or download the files directly to your local machine.

bash
Copy code
git clone https://github.com/yourusername/asheville-air-quality-map.git
Or simply download the ZIP file and extract it.

2. Add GeoJSON Data
Ensure that the GeoJSON files for Asheville City Limits and Asheville Air Quality (Ozone) are in the same directory as your index.html file, or update the fetch() paths accordingly in the script.

Required GeoJSON Files:
Asheville City Limits GeoJSON: Asheville_City_Limits.geojson
Asheville Air Quality (Ozone) GeoJSON: Asheville_Air_Quality_Ozone.geojson
3. Open the Map
After ensuring your data is correctly placed, open index.html in a web browser to view the map. The points representing ozone levels and the city limits polygon should appear automatically.

4. GeoJSON File Structure
Make sure that the GeoJSON files are structured properly. Here’s an example of what the Asheville City Limits and Asheville Air Quality Ozone files should look like:

Example Asheville City Limits GeoJSON:
json
Copy code
{
    "type": "FeatureCollection",
    "features": [
        {
            "type": "Feature",
            "geometry": {
                "type": "Polygon",
                "coordinates": [[...]]
            },
            "properties": {
                "name": "Asheville"
            }
        }
    ]
}
Example Asheville Air Quality (Ozone) GeoJSON:
json
Copy code
{
    "type": "FeatureCollection",
    "features": [
        {
            "type": "Feature",
            "geometry": {
                "type": "Point",
                "coordinates": [-82.5515, 35.5951]
            },
            "properties": {
                "name": "Site 1",
                "ozone_level": 80
            }
        },
        ...
    ]
}
ozone_level: This is used to determine the color of the points on the map.
5. Customization
Color Scale: The function getOzoneColor determines the color for each point based on the ozone level. You can modify the color scheme by adjusting the return values in this function.
Popups: The content of the popups is generated dynamically using data from the GeoJSON files. You can modify what information appears by adjusting the onEachFeature function.
Legend: The legend explains the color codes based on the ozone level and can be modified as necessary.
Tools Used
Leaflet: A JavaScript library for interactive maps.
GeoJSON: A format for encoding geographic data.
Chroma.js: A color library for creating color gradients for the ozone levels.
Troubleshooting
No Data Displayed:

Open the console in your browser's Developer Tools to see if any errors occur while loading the GeoJSON files.
Ensure the GeoJSON files are valid and contain coordinates and properties for each feature.
Legend Not Showing:

Ensure that the legend code is correctly added after the data is loaded. It should update the color scale based on the loaded data.
File Paths:

Ensure that the GeoJSON files are in the correct path relative to index.html and accessible by the browser.
License
This project is licensed under the MIT License - see the LICENSE file for details.

Customizing the Map
If you want to extend the map, here are some ideas:

Add additional layers for other air pollutants (NO2, CO, PM2.5, etc.).
Use a satellite basemap or terrain basemap.
Integrate filters for different air quality categories.
Add interactive search or filtering options for different zones.
