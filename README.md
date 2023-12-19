# Aversity Dark Matter

A Mapbox GL map style based on [Dark Matter](https://github.com/openmaptiles/dark-matter-gl-style)

## Edit the Style

Use the [Maputnik CLI](http://openmaptiles.org/docs/style/maputnik/) to edit and develop the style.
After you've started Maputnik open the editor on `localhost:8000`.

## Usage

Here's how you would use this style with [tileserver-gl](https://github.com/maptiler/tileserver-gl):
1) Grab a osm.pbf file from [Geofabrik](https://download.geofabrik.de/)
2) Convert the osm.pbf file to a mbtiles file using [openmaptiles](https://github.com/openmaptiles/openmaptiles):
    - Tweak the .env file for zoom range (0-14 should be fine as it allows over-zoom to 20 and with @2x)
    - Follow the instructions in the README.md file
    - For the `make generate-bbox-file` step, tweak the output bbox file to be a smaller area if you don't want the the entire area from the osm.pbf file
    - OR just download pre-existing vector tiles (MBTiles): https://data.maptiler.com/downloads/planet/
3) Move the generated MBTiles and bbox files to this folder as `tiles.mbtiles` and `tiles.bbox`
4) Tweak theme as necessary:
    - You can edit the style.json directly, but probably easiest to use [maputnik](https://maputnik.github.io/editor)
    - Can generate fonts here: https://github.com/openmaptiles/fonts.git
5) Serve tiles:
    - With docker: `docker run --rm -it -v $(pwd):/data -p 8080:8080 maptiler/tileserver-gl`
6) Check out your new tiles: http://localhost:8080