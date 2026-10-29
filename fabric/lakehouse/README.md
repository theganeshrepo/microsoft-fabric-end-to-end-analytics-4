# Fabric Lakehouse

## Lakehouse

The project uses a single Microsoft Fabric Lakehouse named `E_Commerce_LH`.

The Lakehouse follows a logical **Medallion Architecture**:

- **Bronze** – raw/source data
- **Silver** – cleaned and transformed data
- **Gold** – curated business-ready data

## Data Domains

The Lakehouse contains data related to:

- Customers
- Orders
- Payments
- Support Tickets
- Web Activities

## Bronze Tables

- `customers`
- `orders`
- `payment_raw`
- `support_ticket`
- `web_activities`

## Silver Tables

- `silver_customers`
- `silver_orders`
- `silver_payment`
- `silver_support_ticket`
- `silver_web_activity`

## Gold Tables

- `gold_customer360`

The Gold layer provides curated customer-level information for downstream analytics and Power BI semantic modeling.

## Storage Structure

```text
E_Commerce_LH
│
├── Tables
│   ├── Bronze
│   ├── Silver
│   └── Gold
│
└── Files
    ├── Bronze
    ├── Silver
    └── Gold
```

The Lakehouse acts as the central analytical storage layer for the end-to-end Fabric solution.