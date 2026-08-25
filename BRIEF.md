# Frozen Foods Command Center Brief

Hearty Organics is a health-focused grocery retailer improving how the Frozen Foods Category Buyer monitors performance and takes action. The dashboard is designed to surface category risk, growth, and margin opportunities quickly, without relying on spreadsheets or fragmented reports.

## Current Implementation Snapshot
- Hero title: Frozen Foods Command Center
- Purpose: unify demand momentum, inventory exposure, margin quality, and vendor reliability in one buyer workflow
- View style: daily category command view with filter-driven metrics and action prompts

## Technology
- Runtime UI in index.html uses Vue 3 (global build) and Chart.js (UMD)
- Vuetify and MDI styles are loaded via CDN (MDI used for interface icons)
- Project stack also includes Vite + Vue + TypeScript dependencies in package.json
- Local fake dataset only (no API calls)
- Deployable as static site (Vercel-friendly)

## Data Model (Implemented)
- Core generated dataset covers Jan-Aug 2026 across:
    - 4 stores
    - multiple vendors
    - multiple frozen subcategories
    - product-level revenue, units, cost, on-hand, and thresholds
- data.json has expanded mock structures for:
    - metadata
    - monthlyPerformance
    - products
    - storeProductSnapshots
    - vendorPerformance
    - purchaseOrders

## Dashboard Structure
- Header filters:
    - Time range (Last 30 days, Last 90 days, Year to date)
    - Store
    - Vendor
    - Category
- KPI row (5 cards):
    - Total Sales
    - Gross Margin
    - Inventory Value
    - Stockout Risks
    - Top Selling Product
- Daily Action Center:
    - Stockout alert
    - Sales dip signal
    - Vendor delay signal

## Main Sections
- Inventory Health
    - Reorder recommendations table
    - Days of supply bars
    - AI Summary accordion
    - Info tooltip icon next to title
- Sales Performance
    - Revenue trend chart
    - Top-selling products list
    - AI Summary accordion
    - Info tooltip icon next to title
- Trend Opportunities
    - Left card: Fastest Growing Products (Top 5, growth %)
    - Center card: Trend vs Inventory Risk (growth, days of supply, health)
    - Right card: Seasonal Demand Signals (event, impact, action, CTA)
    - AI Summary accordion
    - Info tooltip icon next to title
- Profitability
    - Margin by product chart
    - Most profitable brands
    - Low-margin products needing review
    - AI Summary accordion
    - Info tooltip icon next to title
- Vendor Performance
    - Fill rate, on-time delivery, backorders, lead time
    - AI Summary accordion
    - Info tooltip icon next to title

## Interaction & Behavior
- Filters update KPIs, tables, rankings, and charts reactively
- Drawer workflow is action-specific with persona-targeted guidance
- Drawer CTA set:
    - Primary: Go now
    - Secondary: Mark as reviewed
- Seasonal demand cards include Take recommended action CTA
- KPI cards include hover lift + glow effect (corner circles removed)
- Section headers now omit right-aligned descriptive subtitle text

## AI Summary Pattern (Implemented)
- Each major section has a single accordion container under the title
- Accordion label uses a teal MDI star-four-points icon
- Expands to show dynamic, filter-aware trend summary text
- Summary body no longer prefixes with "AI trend summary:"

## Design System Notes
- Palette direction: green/teal-first with amber accents
- Typography scaled up for readability across KPI, table, panel, vendor, and drawer text
- Visual hierarchy emphasizes urgent risk and next-step actions

## Reusable Component Work
- Added reusable Vue SFC for individual KPI cards:
    - src/components/KpiStatCard.vue
- Supports configurable label, value, suffix, compact value mode, and tone state

## Next Integration Step
- Optional: replace hardcoded KPI markup in index.html with KpiStatCard.vue instances rendered from a config array once the page is migrated to a full SFC-based Vue app entry.