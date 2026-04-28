# Restaurant Profit Dashboard

A portfolio-ready analytics project for restaurant inventory and profit tracking.

## Dashboard Preview

![Dashboard Overview](screenshots/dashboard_overview.png)

![Top Products by Profit](screenshots/profit_by_category.png)

## What this project solves
Restaurants need a quick way to understand:
- Revenue, cost, and profit trends
- Profit margin and average order value
- Which products generate the most profit
- Which products need reorder attention

## Tech stack
- Python
- SQLite
- Streamlit
- Pandas
- Plotly

## Project structure

```
restaurant-profit-dashboard/
├── app.py
├── requirements.txt
├── database/
│   ├── init_db.py
│   ├── schema.sql
│   ├── seed.sql
│   └── restaurant_analytics.db   # generated after init
├── data/
└── screenshots/
```

### Automatic cleanup of kitchen notes/add-ons

During import/init, non-sales rows are automatically removed from the stored database so both Streamlit and DBeaver stay clean. This includes entries like steak doneness notes (`medium`, `well done`), kitchen comments (`allt fram`, `nollbong`), and add-on/info categories (`Info kök`, `Extra tillbehör`, `Sides`, `Snacks`).

## Quick start

1. Install dependencies:

```bash
pip install -r requirements.txt
```

2. Create and seed SQLite database:

```bash
python database/init_db.py --reset
```

Alternative: load real order data from CSV (from your existing ecommerce project file):

```bash
python database/load_orders_csv.py
```

You can also pass a custom CSV path:

```bash
python database/load_orders_csv.py --csv "C:/path/to/orders.csv"
```

If your default DB file is locked (for example by DBeaver), write to a new DB file:

```bash
python database/load_orders_csv.py --db "database/restaurant_analytics_real.db"
```

3. Run Streamlit app:

```bash
streamlit run app.py
```

## KPIs included
- Total revenue
- Total cost
- Total profit
- Profit margin %
- Average order value (AOV)
- Stock value
- Reorder needed
- Top 5 products by profit

## Reorder logic
- `Reorder` if remaining stock < 20
- `Watch` if remaining stock is 20-40
- `OK` if remaining stock > 40

## Data source modes
- Demo mode: `python database/init_db.py --reset`
- Real data mode: `python database/load_orders_csv.py`

In real data mode, the dashboard uses:
- net revenue = `order_amount - discount_amount`
- cost = `cogs_amount`
- only rows with status `completed` in KPI totals

The app sidebar lets you choose which `.db` file to visualize.

## Portfolio value
This project demonstrates practical analytics workflow:
1. SQL modeling and data extraction
2. Python transformation and KPI calculations
3. Interactive dashboard for business decisions
