### Análise Exploratória de Dados da Tabela northwind_orders

**A análise exploratória de dados (EDA) é uma etapa fundamental para compreendermos melhor a estrutura e o conteúdo do banco de dados. Esse entendimento inicial é essencial para direcionar análises mais aprofundadas e garantir a qualidade das conclusões obtidas.**

**Comando SQL utilizado:**

```sql
SELECT order_id, customer_id, employee_id, order_date, required_date, shipped_date, ship_via, freight, ship_name, ship_address, ship_city, ship_region, ship_postal_code, ship_country
FROM northwind_orders
LIMIT 10;
```

**Print do resultado no mysql:**

![Descrição da tabela employees](https://github.com/ThamaraCrispim/SQL-PoD-Academy/blob/main/imagens/projeto%2001%20-%20select%20%2B%20from.png)

**Classificação das Variáveis**
##A tabela abaixo apresenta a classificação estatística de cada coluna da tabela northwind_orders. Essa classificação é importante para entender como cada variável pode ser utilizada em ##análises estatísticas e modelagens. ##


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
