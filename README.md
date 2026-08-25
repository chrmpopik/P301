# Hearty Organics Frozen Foods Command Center

A buyer-focused frozen category dashboard for Hearty Organics. The experience is designed to help category managers scan demand, inventory, profitability, and vendor reliability quickly, then move directly into recommended actions.

## Included

- Daily Action Center with stockout, sales, and vendor alerts
- KPI row for total sales, gross margin, inventory value, stockout risk, and top-selling product
- Filter controls for time range, store, vendor, and category
- Inventory Health with reorder recommendations and days-of-supply status
- Sales Performance with monthly revenue trend and top-selling products
- Trend Opportunities with:
	- Fastest Growing Products
	- Trend vs. Inventory Risk
	- Seasonal Demand Signals with action CTA
- Profitability views for margin by product, top brands, and low-margin items
- Vendor Performance for fill rate, on-time delivery, backorders, and lead time
- Persona-focused action drawer with primary Go now and secondary Mark as reviewed actions
- Section-level info tooltips and AI Summary accordions (toggle)
- Expanded local mock data covering Jan-Aug 2026 in data.json

## UI Details

- KPI cards include hover lift/shadow interactions
- Section descriptions are provided via hover info icons beside section titles
- AI Summary rows use Material Design star-four-points icon and expand inline in a unified accordion container
- Typography has been scaled for improved readability across cards, tables, and drawers

## Component Work

- Reusable KPI card component added at src/components/KpiStatCard.vue
- Supports configurable label, value, value suffix, compact display mode, and tone state

## Run locally

```bash
npm install
npm run dev
```

## Stack

- Vue 3
- Vite
- Chart.js
- Vuetify styles
- Material Design Icons

The project is a static Vite site and is deployable to Vercel. Data is local and there are no API calls.