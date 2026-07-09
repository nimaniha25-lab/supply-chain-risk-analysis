# Supply Chain Risk Analysis — Inventory & Supplier Reliability

## Business Question
Which product categories and suppliers are contributing most to stockout risk and delivery delays — and does the company's "Preferred" supplier designation actually reflect real-world delivery performance?

## Dataset
A simulated dataset of 200 retail purchase orders across 3 warehouses (Karachi, Lahore, Islamabad), 5 product categories, and 4 suppliers, including order quantities, stock levels, reorder points, lead times, and delivery outcomes.

## Tools Used
Excel — formulas (SUM, AVERAGE, COUNTIF, IF), VLOOKUP across reference tables, PivotTables, conditional formatting, and a summary dashboard.

## Approach
1. Calculated baseline metrics: total order volume, average lead time, and overall late-delivery rate.
2. Flagged SKUs at reorder risk using an IF formula comparing current stock against reorder point.
3. Built a PivotTable to break down reorder risk by product category and warehouse, to check whether the risk was concentrated in specific products or specific locations.
4. Used VLOOKUP to bring in supplier reliability scores and preferred/standard status from a separate reference table.
5. Applied conditional formatting to flag orders that were both late *and* from a non-preferred supplier — a compounding risk signal.
6. Built a summary dashboard with headline KPIs and two charts, tying the findings together.

## Key Findings
- **18% of all orders (36 of 200)** were delivered late.
- **29 SKUs (14.5% of orders)** were placed while stock was already below the reorder point, indicating a lag in the reordering process.
- **Electronics and Apparel account for ~66% of all reorder-risk SKUs**, while the risk is fairly evenly spread across warehouses — suggesting the issue is driven by category-level demand or reorder policy, not a single warehouse's operations.
- **Counterintuitively, "Preferred" suppliers had a higher late-delivery rate (23%) than "Standard" suppliers (13%)** in this dataset. This suggests the preferred designation, as currently assigned, may not reflect actual delivery performance and could benefit from being re-evaluated using real outcome data rather than a static score.

## Recommendation
Reorder point policy should be reviewed specifically for Electronics and Apparel categories, where risk is concentrated. Additionally, the criteria for "Preferred" supplier status should be revisited to incorporate actual on-time delivery rates, since the current designation does not align with observed performance.

## Files
- `supply_chain_practice.xlsx` — full workbook with raw data, pivot tables, VLOOKUP reference table, conditional formatting, and dashboard.
