# Sanathana map

The offline map data of Sanathana, a free Android app about the history and stories of Hindu temples in India.

Each release holds one build of the map's **state packs**: for each of India's 36 states and union territories, `<st>.pmtiles` (vector tiles, zooms 9 to 14: taluks, villages, roads, railways, rivers, forests, peaks) and `<st>.elev.pmtiles` (elevation for hill shading, zooms 8 to 11). The app downloads a state's two files from here when it wasn't installed from Google Play; installs from Play get the same files from Play.

The files are [PMTiles](https://github.com/protomaps/PMTiles) archives. Any PMTiles reader opens them, for example <https://pmtiles.io>.

## Licence and sources

- **OpenStreetMap.** The vector tiles are made from OpenStreetMap data, © OpenStreetMap contributors, and are offered under the [Open Database License (ODbL) 1.0](https://opendatacommons.org/licenses/odbl/1-0/). See <https://www.openstreetmap.org/copyright>.
- **Natural Earth** (public domain): India's outline and state lines, in India's official view.
- **Elevation:** Tilezen terrain tiles on AWS Open Data (`elevation-tiles-prod`), made from NASA SRTM, NOAA ETOPO1, USGS GMTED2010 and other sources. See <https://github.com/tilezen/joerd/blob/master/docs/attribution.md>.

## How the files are made

With [Planetiler](https://github.com/onthegomap/planetiler) from Geofabrik's OpenStreetMap extracts, then cut into one pack per state; the elevation is rounded to 1 m and stored as lossless WebP (Terrarium encoding).
