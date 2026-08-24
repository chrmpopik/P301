# Hearty Organics Frozen Foods Dashboard

A clean, action-oriented category performance dashboard for the Hearty Organics Frozen Foods buyer. It brings sales, inventory, profitability, vendor performance, and purchase order signals into one daily view.

## Included

- Daily Action Center for stockout, sales, and vendor alerts
- KPI summary for sales, margin, inventory value, stockout risk, and top product
- Filter controls for date range, store, vendor, and category
- Inventory health with reorder recommendations and days of supply
- Sales trend and top-selling product views
- Product margin and profitable brand analysis
- Vendor fill rate, on-time delivery, backorders, and lead times
- Clickable alert, product, and recommendation drill-in panels
- Fake January-August 2026 dataset in `data.json`

## Run locally

```bash
npm install
npm run dev
```

The project is a static Vite site and can be deployed directly to Vercel. The prototype uses Vue 3, Vuetify 3 styling primitives, and Chart.js. Data is local and there are no API calls.