# Earth Jukebox

Earth's night lights pressed onto vinyl. Pick an album from the jukebox, drop the needle on any latitude, and hear the map: a cello follows how bright each spot is, and fire or extreme heat turns it harsh and out of key. Flip the record for side B.

Built for the NASA Space Apps Challenge 2026 challenge "The Earth Information Jukebox". It pairs NASA Earth imagery with sound generated live in the browser, and it is designed to be usable without seeing the picture.

- **Side A** is the northern hemisphere, centred on the North Pole.
- **Side B** is a Postel (azimuthal equidistant) projection centred on the South Pole, made automatically from the same map.

## Run it

It is one static file with no build step, no server code and no third-party libraries.

```
python3 -m http.server 8000     # then open http://localhost:8000
```

You can also open `index.html` directly.

## Put it online (GitHub Pages)

1. Create a public GitHub repository and upload these files (`index.html`, `README.md`, `SOURCES.md`, `SUBMISSION.md`, `LICENSE`, `.nojekyll`).
2. In the repository, open **Settings → Pages**, set the source to **Deploy from a branch**, choose `main` and `/ (root)`, and save.
3. After a minute the app is live at `https://<your-user>.github.io/<repo-name>/`. Open it and add one album from Worldview to confirm the live fetch works from the hosted page.

## Add an album from Worldview

Press **+ Add album**, choose a layer and a date, and press **Press album**. The page requests the whole-globe map from NASA's Worldview image service ([GIBS](https://nasa-gibs.github.io/gibs-api-docs/)) with a WMS `GetMap` request. No server of ours is involved, and nobody needs an account or an API key.

- Pick **Other layer ID…** to use any layer from the [GIBS layer list](https://nasa-gibs.github.io/gibs-api-docs/available-visualizations/). Layer IDs also appear in Worldview's layer info.
- Combine layers by listing IDs separated by commas, for example `VIIRS_NOAA20_DayNightBand_ENCC,VIIRS_NOAA20_Thermal_Anomalies_375m_All` for night lights with fires.
- If you already have a snapshot file, open **Or use a snapshot file you already have**. For a map that is not the whole globe, enter its bounds.

Added albums are saved in the browser (IndexedDB) and stay there. They are not shared between browsers.

## How the sound works

| Map under the needle | Sound |
|---|---|
| Dark | soft low cello note |
| Brighter | higher, across two octaves of F♯ major (F♯2 to F♯4) |
| Dense clusters of light | a second string a fifth above |
| Saturated red-orange (fire, extreme heat) | a quarter-tone off key, a tritone second string, detuned and grating |

Brightness is measured on a log scale, so faint rural lights and dense cities both register. Lifting the needle, pressing Pause or pressing Sound off cuts all sound.

## Accessibility

The challenge treats accessibility as a core theme, so these are part of the app, not extras:

- **Keyboard.** Tab to the record and use the arrow keys (Shift or Page Up/Down for bigger steps, Home and End for the limits) to move the needle, Enter or Space to lift or drop it, and Escape to lift it. The latitude slider, the jukebox rack, the flip, pause and sound buttons and the add-album form are all keyboard operable, with a visible focus outline.
- **Spoken description of the map.** A text line says what is under the needle, for example "35 degrees north, 124 degrees west: town-sized lights, near the US West Coast", and flags fire or extreme heat. It is a polite live region, so screen readers announce changes at most every 2.5 seconds. A checkbox turns the announcements off.
- **Describe this latitude.** One button summarises a whole turn of the record at the current latitude: how much is dark, how much is lit, the brightest places, and whether any fire or heat was found. This lets a listener understand the picture without scrubbing the needle around.
- **About this album.** Every album has a plain-language description of its source and what the sound means.
- **Touch feedback.** On phones that support it, the device vibrates for bright cities and with a stronger pattern for fire.
- **Reduced motion.** With the system setting on, the record flip is a quick cut instead of a turn-over.

Place names in the descriptions come from a small hand-made table of regions and are approximate. The app has not yet been tested with a real screen reader across browsers, so please report any problems.

## Limits

- Blank areas in a map (for example gaps between satellite passes) are filled with generated texture and no invented lights. The built-in Light Pollution album also has hand-placed city lights where its source map was missing data. Those are not measurements, and the album's description says so.
- The sound reads brightness and colour. It suits night-lights and fire layers best.
- Extreme cold is not detected yet.

## Sources and credits

See [SOURCES.md](SOURCES.md) for every data source, layer and tool used. Imagery is from NASA Worldview / GIBS. Please acknowledge NASA Worldview when you share what you make with it.

## License

MIT. See `LICENSE`.
