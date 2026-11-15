# Space Apps submission draft: Earth Jukebox

Challenge: The Earth Information Jukebox

Fill in the bracketed links before submitting.

- Repository: [your GitHub repository URL]
- Live demo: [your GitHub Pages URL]
- Demo video: [your video URL]

## Summary

Earth Jukebox turns NASA Earth imagery into a record you can play. Each album is a vinyl record with Earth's night lights on side A (northern hemisphere) and the southern hemisphere on side B. Drop the needle on any latitude as the record spins and a cello plays what is under it, live in the browser.

## How it works

- Maps come straight from NASA Worldview (GIBS), chosen by layer and date inside the app, or from a snapshot file.
- Each map is reprojected onto a disc. Side A is centred on the North Pole and side B is a Postel projection centred on the South Pole.
- Brightness under the needle sets the pitch across two octaves of F♯ major. Dense clusters of light add a second string. Saturated red-orange (fire, extreme heat) makes the cello harsh and out of key, so bad news sounds bad.
- Everything runs in the browser with the Web Audio API. There is no server and no account.

## Accessibility

- Full keyboard control of the needle, and visible focus.
- A live text description of what is under the needle, and a "Describe this latitude" summary of a whole turn of the record, so the map can be understood without the picture.
- Plain-language description of every album, optional vibration feedback on phones, and reduced-motion support.

## Limits we are open about

- Where the source snapshot had no data, areas are filled with generated texture and some city lights are hand placed. These are labelled as not measured.
- The app has not been tested with every screen reader. Place names in descriptions are approximate.

## Data and credits

NASA Worldview / GIBS imagery. Full list in SOURCES.md. Built with the help of Claude (Anthropic).
