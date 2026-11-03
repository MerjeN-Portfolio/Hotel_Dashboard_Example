# Hotel Nordlys: Sales Dashboard

An interactive hotel sales dashboard built as a single, self-contained HTML file. It is a portfolio project that shows how to turn hotel revenue data into a clear, filterable overview using standard revenue management KPIs.

> **Note:** Hotel Nordlys is a fictional property. All data is randomly generated with a fixed seed and does not represent a real business.

## Features

- **KPI strip:** revenue, occupancy, ADR and RevPAR, each with the change versus the previous year
- **Monthly trend chart:** switch between revenue, occupancy, ADR and RevPAR; hover to compare the selected year with the previous one
- **Revenue by sales channel:** Direct, Booking.com, Expedia, Corporate and Travel agents; click a channel to filter the whole dashboard
- **Room type breakdown:** Standard, Superior and Suite with rooms, occupancy, ADR, RevPAR and revenue
- **Occupancy heatmap:** month by room type
- **Monthly data table** as an accessible alternative to the charts
- Light and dark theme (follows the system setting), responsive down to phone width

## Metrics

| Metric | Definition |
|---|---|
| Occupancy | Room nights sold / room nights available |
| ADR (average daily rate) | Revenue / room nights sold |
| RevPAR (revenue per available room) | Revenue / room nights available (equals occupancy x ADR) |

When a channel filter is active, occupancy shows that channel's share of total room capacity.

## Data

The data set is generated in the browser (`REC` array in the script):

- 112 rooms: 60 Standard, 40 Superior, 12 Suite
- Two years (2024 and 2025), 12 months, 3 room types, 5 channels
- Seasonal occupancy and rate patterns, room type and channel rate factors, small random noise
- Seeded pseudo-random generator (mulberry32), so the numbers are the same on every load

To use real data, replace the generator with records in the same shape:

```js
{ y: 2025, m: 6, t: 'Standard', c: 'Direct', n: 812.4, rev: 98765.0 }
// y = year, m = month (0-11), t = room type, c = channel,
// n = room nights sold, rev = revenue in EUR
```

Room counts are set in the `ROOMS` object and are used to calculate available room nights.

## Run it

No build step and no dependencies.

1. Download or clone the repository
2. Open `index.html` in a browser

To publish it, enable **GitHub Pages** (Settings > Pages > deploy from the `main` branch, root folder).

## Tech

- Plain HTML, CSS and JavaScript
- Charts drawn as inline SVG, no charting library
- System font stack, colors defined as CSS custom properties for light and dark themes

## Skills demonstrated

KPI design for the hotel industry, data modelling, interactive filtering, data visualization and accessibility (table view, keyboard focus, color-independent encodings).
