# Weekend Snow Planner

A weekend ski and snowboard planner for **Cali Pass** holders (home resort: Dodge Ridge), covering:

- **Cali Pass, unlimited:** Dodge Ridge, Bear Valley, China Peak, Mountain High
- **Powder Alliance:** Sierra-at-Tahoe and Mt. Shasta Ski Park (drivable), plus 12 fly-to partners
- **Tahoe add-ons, paid:** Palisades Tahoe, Northstar, Heavenly
- **Destination trips, paid:** Mammoth, Park City, Snowbird, Deer Valley, Vail, Breckenridge, Aspen Snowmass
- **Epic Pass mode:** all 44 North American Epic Pass resorts (37 Vail-owned plus Telluride and the 6 Resorts of the Canadian Rockies), shown only when "I have an Epic Pass" is on

**Live site:** https://kartik2112.github.io/claude-weekend-snow-planner/

## What it shows

- A grid of resorts × weekends (Saturdays, Sundays, or the whole weekend), with holiday weekends highlighted
- A 16-day forecast for each resort, loaded live from [Open-Meteo](https://open-meteo.com/) on every page load: high/low temperature, snowfall, chance of precipitation, wind, and snow in the 3 days before
- Beyond 16 days, the 2015–2025 average for that week (typical high/low and the share of days with 1″+ of new snow)
- What each day costs you: Cali Pass days show no price, Powder Alliance days are free Sunday–Friday outside holidays, and everything else shows a lift-ticket price. You can also add a snowboard rental, for every resort or one at a time.
- A map view of whichever resorts are open in the list, with driving routes from an editable start address (OpenStreetMap Nominatim + OSRM)
- A Deals tab: flexible multi-day passes (Epic Day Pass, Mammoth Quad Pack+, Sierra 3-PAK, Dodge/Bear packs, Ikon Session), Palisades packs, advance-online prices and buddy discounts, with deadlines, totals, per-day prices, resort filters, favorites and hide
- A Cali Pass break-even calculator ("Pass value" tab): pass cost, day-ticket prices, Dodge Ridge and Bear Valley multi-day packs, and your planned days
- Live forecasts are fetched only for resort groups that are open, cached for 30 minutes
- A ski-in/ski-out filter
- Switches for "I have a Cali Pass", high/low temperatures, and °F/°C

## Data

| File | What | Freshness |
|---|---|---|
| `data/resorts.json` | Resorts, coordinates, pass rules, holiday/blackout dates, ticket and rental prices | Prices checked Nov 12, 2026. Many are estimates (shown as `$~`); confirm on the resort's site. |
| `data/climate.json` | Weekly averages from the Open-Meteo archive, 2015–2025 | Static |
| `data/forecast.json` | Fallback forecast, used only if the live Open-Meteo request fails | Snapshot |

Prices are adult single-day weekend rates. Palisades, Northstar and Heavenly price by date, so the planner shows a typical advance-online price; window rates run higher.

Built with Claude.
