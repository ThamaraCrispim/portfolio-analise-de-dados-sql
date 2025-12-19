**Comando SQL utilizado:**

```sql
SELECT order_id, customer_id, employee_id, order_date, required_date, shipped_date, ship_via, freight, ship_name, ship_address, ship_city, ship_region, ship_postal_code, ship_country
FROM northwind_orders
LIMIT 10;
```

###classificação


| Coluna             | Tipo estatístico              |
|--------------------|-------------------------------|
| order_id           | Qualitativa nominal           |
| customer_id        | Qualitativa nominal           |
| employee_id        | Qualitativa nominal           |
| order_date         | Quantitativa contínua (temporal) |
| required_date      | Quantitativa contínua (temporal) |
| shipped_date       | Quantitativa contínua (temporal) |
| ship_via           | Qualitativa nominal           |
| freight            | Quantitativa contínua         |
| ship_name          | Qualitativa nominal           |
| ship_address       | Qualitativa nominal           |
| ship_city          | Qualitativa nominal           |
| ship_region        | Qualitativa nominal           |
| ship_postal_code   | Qualitativa nominal           |
| ship_country       | Qualitativa nominal           |
