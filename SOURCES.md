# Sources and credits

Every source used in this project is listed here, including open and freely available ones.

## Data and imagery

All maps come from **NASA Worldview**, through the **Global Imagery Browse Services (GIBS)**, operated by NASA's Earth Science Data and Information System (ESDIS) project.

- NASA Worldview: https://worldview.earthdata.nasa.gov/
- GIBS API documentation: https://nasa-gibs.github.io/gibs-api-docs/
- WMS endpoint used by the app: `https://gibs.earthdata.nasa.gov/wms/epsg4326/best/wms.cgi` (request type `GetMap`, whole globe, EPSG:4326)

Layers offered in the album picker (each layer's own citation and DOI are in its info panel in Worldview):

| Layer ID | Description |
|---|---|
| `VIIRS_NOAA20_DayNightBand_ENCC` | VIIRS Day/Night Band, NOAA-20, enhanced near constant contrast |
| `VIIRS_SNPP_DayNightBand_ENCC` | VIIRS Day/Night Band, Suomi NPP, enhanced near constant contrast |
| `VIIRS_NOAA20_DayNightBand_At_Sensor_Radiance` | VIIRS Day/Night Band, NOAA-20, at-sensor radiance |
| `VIIRS_Black_Marble` | NASA Black Marble night lights |
| `VIIRS_NOAA20_Thermal_Anomalies_375m_All` | VIIRS NOAA-20 375 m thermal anomalies (active fires) |
| `VIIRS_SNPP_Thermal_Anomalies_375m_All` | VIIRS Suomi NPP 375 m thermal anomalies (active fires) |
| `MODIS_Terra_Land_Surface_Temp_Day`, `MODIS_Terra_Land_Surface_Temp_Night` | MODIS Terra land surface temperature |
| `GHRSST_L4_MUR_Sea_Surface_Temperature` | GHRSST MUR sea surface temperature |
| `Coastlines_15m` | Coastline reference overlay, optional |

Reference for the Black Marble product family: Román, M. O. et al. (2018), "NASA's Black Marble nighttime lights product suite", *Remote Sensing of Environment* 210, 113–143.

### The built-in "Light Pollution" album

Made from a screenshot the author took in NASA Worldview of the NOAA-20 VIIRS night-lights layer for 13 November 2026 (the NASA product family VJ246A1, near real time). The screenshot had a swath with no data, so:

- Blank areas were filled with generated texture, matched to the surrounding sea and cloud.
- City lights were hand-placed from geography where data was missing, including parts of Asia and the southern hemisphere.
- Coastlines in the blank areas were redrawn by hand.

These parts are not measurements. The album's on-page description says so.

## Software

- No third-party code, libraries, frameworks or web fonts are used. The app is plain HTML, CSS and JavaScript.
- Browser features used: Canvas 2D, Web Audio API, IndexedDB, Fetch, the Vibration API (where available).
- Text is set in the system's Georgia or serif font.

## Tools

- The app was designed and written with the help of Claude, an AI assistant from Anthropic. The author directed the design and reviewed the results.

## Method references

- Azimuthal equidistant (Postel) projection, standard map projection, used for both record sides.
- Musical scale: F♯ major, two octaves, F♯2 to F♯4.
- Solfeggio-frequency chakra tones were an experiment in an earlier version and are not part of this app.

## Licensing

- The code in this repository is MIT licensed (`LICENSE`).
- NASA imagery is made available for public use under NASA's media usage guidelines; please credit NASA Worldview.
