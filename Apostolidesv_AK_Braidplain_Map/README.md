# Alaska's Changing Braidplains

This interactive Leaflet web map explores proglacial braidplains across Alaska's Juneau Icefield and Denali National Park study regions. It uses original research boundaries and the Braidplain_Master_Glacierization dataset to display median NDVI, annual NDVI trends, glacierized watershed percentage, lake presence, and watershed-level land-cover summaries. Visitors can switch between Juneau, Denali, or both regions; hover over braidplain polygons to view NDVI; click polygons and lake-status markers for details; and toggle watershed outlines. The map uses Leaflet, Leaflet AJAX-compatible GeoJSON conventions, Font Awesome symbols, and a CARTO basemap, following the supplied Lab 6 example. Braidplain and watershed boundaries were converted from project GeoPackages to GeoJSON (WGS84). Lake symbols indicate *status* at polygon centers, not surveyed lake locations. Land-cover percentages are calculated from the master dataset's 2020 category areas and watershed area; they do not represent a pixel-level land-cover map. Some records have missing NDVI values. Source: project research datasets; OpenStreetMap/CARTO basemap.

## Lake geometry and temporal limitation

The supplied `AllLakes_AK.shp` has geometry but lacks `.dbf`, `.shx`, and `.prj` sidecars. We recovered polygon geometry and selected lake outlines intersecting a ~0.12° buffer around the study watersheds. The coordinates appear geographic longitude/latitude; this should be confirmed against the original `.prj`. No observation years are available, so the map deliberately displays **undated lake outlines** and does not claim lake expansion by year. For historical comparisons, provide lake boundaries for each date or a lake attribute table with dates and stable lake IDs.

Basemap: OpenStreetMap HOT.


## Lake survey periods
AK_Lakes.csv is joined to AllLakes_AK.shp by verified original feature order (0-based index), then subset to the 292 outlines near the study watersheds. Use the lake survey selector to compare 1984–1988, 1997–2001, 2007–2011, and 2016–2019. These are period snapshots, not annual measurements; do not assume all lake IDs persist between periods. The 1997–2011 and missing-year exceptions remain under their recorded midpoint year and may not appear in the four standard survey-period options.


## Data credits

- **Landsat:** USGS EarthExplorer, Landsat surface reflectance imagery (https://earthexplorer.usgs.gov/).
- **Braidplains:** Manually delineated by the student researcher.
- **Watersheds and watershed attributes:** MGHydro (https://mghydro.com/). The MGHydro website references multiple underlying datasets; these references should not automatically be treated as the direct source of each displayed variable.
- **Alaska lakes:** Lake outlines supplied by the research advisor; original source not independently established. Survey periods and mapped areas come from the supplied `AllLakes_AK.shp` and `AK_Lakes.csv`.
- **Institutional logos:** National Science Foundation; Appalachian State University; Department of Geological and Environmental Sciences. Logos are included for attribution and identification, not as a claim of NSF funding or endorsement of this specific map.

### References provided from the MGHydro website

Amatulli, G., et al. (2018). A suite of global, cross-scale topographic variables for environmental and biodiversity modeling. *Scientific Data*, 5, 180040. https://doi.org/10.1038/sdata.2018.40

Fick, S. E., & Hijmans, R. J. (2017). WorldClim 2: New 1-km spatial resolution climate surfaces for global land areas. *International Journal of Climatology*, 37, 4302–4315. https://doi.org/10.1002/joc.5086

Harris, I., et al. (2020). Version 4 of the CRU TS monthly high-resolution gridded multivariate climate dataset. *Scientific Data*, 7, 109. https://doi.org/10.1038/s41597-020-0453-3

Potapov, P., et al. (2022). The global 2000–2020 land cover and land use change dataset derived from the Landsat archive: First results. *Frontiers in Remote Sensing*. https://doi.org/10.3389/frsen.2022.856903

Yamazaki, D., et al. (2017). A high-accuracy map of global terrain elevations. *Geophysical Research Letters*, 44, 5844–5853. https://doi.org/10.1002/2017GL072874

Other MGHydro-listed datasets may support additional environmental variables but are not necessarily direct sources for the layers used in this map.
