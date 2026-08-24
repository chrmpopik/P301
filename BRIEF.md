# Frozen Foods Category Performance Dashboard

Hearty Organics is a health-focused grocery retailer looking to improve how its Frozen Foods Category Buyer monitors category performance. The dashboard should provide an at-a-glance view of sales, inventory, profitability, and vendor performance, enabling the buyer to quickly identify risks, opportunities, and actions needed without relying on spreadsheets or multiple reports.

## Technology
– Vue 3 + TypeScript + Vuetify 3
– Chart.js via vue-charts for all charts
– Fake data from a local JSON (no API calls)
– Data sources: POS system, inventory management system, purchase orders, vendor data
– Daily data refresh with potential for near real-time inventory updates
– Role-based access and filtering
– Deploys to Vercel as a static site

## Layout
– Header: Date range filter, Store filter, Vendor filter, Product category filter
– KPI cards: Total Sales, Gross Margin %, Inventory Value, Stockout Risks, Top Selling Product
– Main Dashboard Sections:
    – Inventory Health: Low stock items, Overstocked products, Days of supply remaining, Reorder recommendations
    – Sales Performance: Sales trends over time, Top-selling products, Revenue by subcategory, Sales growth/decline indicators
    – Profitability: Margin by product, Most profitable brands, Low-margin products needing review
    – Vendor Performance: Fill rate %, On-time delivery %, Backorders, Lead times by vendor
– Daily Action Center: section at the top that surfaces the 3-5 most urgent items requiring the buyer's attention that day.

## Data
Generate a fake dataset as a JSON file. 12 months of data (Jan-August 2026), each month containing:
– Product information (SKU, name, brand, category)
– Inventory levels and reorder thresholds
– Sales and revenue data
– Cost and margin data
– Vendor performance metrics
– Purchase order history

## Design
– Clean, modern retail dashboard
– Health-focused color palette (greens, blues, neutrals)
– Highlight critical issues with alerts and color indicators
– Prioritize actionable insights over detailed reporting
– Accessible and easy to scan within seconds
– Define reuseable components for me to customize

## Interactions
– Filter by store, vendor, category, and time period
– Drill into product-level details
– Hover for additional metrics and trends
– Alert notifications for stockout risks and sales declines
– Click-through to product and vendor performance views