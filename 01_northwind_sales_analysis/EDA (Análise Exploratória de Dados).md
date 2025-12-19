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


**A tabela abaixo apresenta a classificação estatística de cada coluna da tabela northwind_orders. Essa classificação é importante para entender como cada variável pode ser utilizada em ##análises estatísticas e modelagens.**


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


### Número de Resgistos


```sql
select count(*) as toral_registros from northwind_orders
```
**Print do resultado no mysql:**

![ Número de Resgistos](https://github.com/ThamaraCrispim/SQL-PoD-Academy/blob/main/imagens/Numero%20de%20resgisto!%20projeto%201.png)


**Análise:
A consulta realizada contabiliza um total de 830 registros na tabela northwind_orders, valor que representa a quantidade de vendas/pedidos efetuados e devidamente registrados no sistema.***


### Verifique Valores Nulos

```sql
SELECT
  SUM(order_id IS NULL) AS nulos_order_id,
  SUM(customer_id IS NULL) AS nulos_customer_id,
  SUM(employee_id IS NULL) AS nulos_employee_id,
  SUM(order_date IS NULL) AS nulos_order_date,
  SUM(required_date IS NULL) AS nulos_required_date,
  SUM(shipped_date IS NULL) AS nulos_shipped_date,
  SUM(ship_via IS NULL) AS nulos_ship_via,
  SUM(freight IS NULL) AS nulos_freight,
  SUM(ship_name IS NULL) AS nulos_ship_name,
  SUM(ship_address IS NULL) AS nulos_ship_address,
  SUM(ship_city IS NULL) AS nulos_ship_city,
  SUM(ship_region IS NULL) AS nulos_ship_region,
  SUM(ship_postal_code IS NULL) AS nulos_ship_postal_code,
  SUM(ship_country IS NULL) AS nulos_ship_country
FROM northwind_orders;
```
**Print do resultado no mysql:**

![ Valor is null](https://github.com/ThamaraCrispim/SQL-PoD-Academy/blob/main/imagens/is%20null.png)

**Análise:
Todas as colunas analisadas na tabela northwind_orders apresentam 0 valores nulos. Portanto, não é necessário realizar tratamento para dados ausentes nesta etapa.***

