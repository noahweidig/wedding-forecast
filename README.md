# Wedding Weather Forecast

A static GitHub Pages dashboard showing National Weather Service hourly forecasts for two central Florida wedding venues on **Saturday, June 13, 2026**.

## Venues

| Venue | Coordinates |
|---|---|
| Altamonte Springs, FL | 28.6611, -81.3656 |
| Howey-in-the-Hills, FL | 28.7197, -81.7787 |

## How it works

- `index.html` is a single-page dashboard that fetches data **directly from `api.weather.gov`** in the browser on every page load. No backend.
- NWS hourly forecasts are issued ~7 days in advance. Until **June 6, 2026**, the page will show a "check back" message in place of charts.
- The dashboard uses:
  - **Chart.js** for hourly precipitation probability bar charts
  - **Leaflet.js + OpenStreetMap** for the venue map
- A daily GitHub Actions workflow (`daily-refresh.yml`) updates `last_built.json` at 06:00 UTC for cache-busting / freshness signaling. It can also be triggered manually via `workflow_dispatch`.

## Local preview

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

## Deployment

Enable GitHub Pages on this repository (Settings → Pages → Deploy from branch → `main` / root). The site is fully static.
