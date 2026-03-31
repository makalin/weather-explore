# City Weather Explorer

A web-based tool for comparing average monthly weather patterns between cities using interactive 3D visualizations.

**Live site:** [https://makalin.github.io/weather-explore/](https://makalin.github.io/weather-explore/)

![City Weather Explorer](https://img.shields.io/badge/version-1.2-blue)
![License](https://img.shields.io/badge/license-MIT-green)

## Features

- **3D carousel visualization**: Compare up to three cities on a rotating 3D radar-style chart
- **Multiple data types**: Temperature, rainfall, or daily sunlight hours
- **Historical data**: Choose a decade from the 1940s through the current decade
- **Temperature options**: Actual vs. “feels like,” and high / mean / low
- **Units**: Fahrenheit or Celsius for temperature
- **Themes**: Light, Dark, Ocean, and Sunset—cycle with the theme button in the header
- **Languages**: English and Turkish—use the **TR** / **EN** toggle in the header
- **Tools menu**: Export comparison data as CSV, save the current chart as PNG, reset the 3D camera, clear all cities, and open keyboard shortcuts
- **Year-range stats**: Under the legend, min / max / average for the active metric (when cities are selected)
- **Shareable URLs**: Link includes data type, temperature options, unit, language, theme, and selected cities/decades
- **Responsive layout**: Usable on desktop and mobile
- **Caching**: Weather API responses are cached in the browser to limit repeat requests

## Saved settings

The app stores preferences in **localStorage** (and mirrors many of them in the URL when you share):

| Key | Purpose |
|-----|---------|
| `theme` | Selected theme (`light`, `dark`, `ocean`, `sunset`) |
| `unit` | `celsius` or `fahrenheit` |
| `language` | `en` or `tr` |

On first visit, theme follows the system light/dark preference until you pick a theme explicitly.

## How it works

### Data source

Weather data comes from the [Open-Meteo API](https://open-meteo.com/) (historical archive), including daily highs, lows, means, apparent temperatures, precipitation, and sunshine duration.

### Visualization

Built with [Three.js](https://threejs.org/). Months sit around a circle; height encodes the chosen metric; colors distinguish cities.

### Caching

Responses are keyed by location and decade and stored in `localStorage` to speed up revisits.

## Usage

1. Search for a city and pick a decade
2. Add up to two more cities to compare
3. Use the toggles for data type, temperature flavor, and units
4. Drag the 3D view to rotate; use **Tools** for CSV/PNG, reset view, or shortcuts
5. Use **Share** to copy a link (or the system share sheet on supported devices)
6. Switch **TR** / **EN** or cycle **theme** as needed; choices persist locally and in shared links

## Development

Single-page app in `index.html`; no build step. Open the file locally or serve it with any static file server.

## Author

Developed by [Arthur Juliani](https://awjuliani.github.io/)
