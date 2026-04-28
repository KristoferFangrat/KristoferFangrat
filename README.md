# Ecommerce KPI Dashboard Portfolio Project

## Dashboard Preview

> Screenshots will appear here once the Power BI dashboard is exported.  
> Add images to `assets/` and update the paths below.

<!-- ![Dashboard Overview](assets/dashboard_overview.png) -->
<!-- ![KPI Trend](assets/kpi_trend.png) -->

## Project Summary
This project analyzes ecommerce performance to answer one core business question:
which channels, categories, and periods are driving revenue growth with healthy margins?

The output is a decision-ready dashboard and a short executive summary with practical actions.

## Business Problem
A fictional ecommerce team needs better visibility into revenue quality, not only top-line growth.
Current reporting is fragmented and does not consistently track margin and return behavior.

### Target KPIs
- Revenue
- Gross margin and gross margin percent
- Average order value (AOV)
- Return rate
- Orders and customers

## Tech Stack
- SQL (cleaning, modeling, KPI logic, validation)
- Power BI (dashboard and filtering)
- Optional Python notebook for EDA

## Project Structure
- `data/raw`: raw source files (not versioned)
- `data/processed`: processed outputs (not versioned)
- `sql`: step-by-step SQL scripts
- `powerbi`: dashboard file
- `reports`: executive summary template and export files
- `docs`: KPI definitions and assumptions
- `assets`: dashboard screenshots for the portfolio

## Workflow
1. Place source CSV files in `data/raw`.
2. Load `raw_orders` into your SQL engine.
3. Run SQL scripts in order:
   - `sql/01_data_cleaning.sql`
   - `sql/02_kpi_queries.sql`
   - `sql/03_validation_checks.sql`
4. Connect Power BI to output tables (`kpi_monthly`, `kpi_by_channel`, `kpi_by_category`).
5. Build visuals and export screenshots to `assets`.
6. Fill in the executive summary in `reports`.

## Key Insights Template
Replace with your real findings once analysis is complete.
1. Revenue trend:
2. Margin pattern:
3. Return behavior:

## Recommended Actions Template
1. Shift budget toward channels with high margin percent.
2. Audit categories with high return rate.
3. Improve discount strategy where AOV is dropping.

## Data Quality and Assumptions
See:
- `docs/metric_definitions.md`
- `docs/assumptions_and_limitations.md`

## Portfolio Presentation Tips
- Keep dashboard to 1 main page plus 1 drilldown page.
- Show trend, segmentation, and root-cause views.
- In the README, emphasize decisions supported by data.

## Next Steps
- Add a conversion-rate view if web session data is available.
- Add cohort retention analysis by first purchase month.
- Add forecast baseline for revenue and margin.
