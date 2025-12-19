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

### Resumo Estatístico de Colunas Numéricas


```sql
SELECT
  MIN(freight) AS minimo,
  MAX(freight) AS maximo,
  AVG(freight) AS media,
  STDDEV(freight) AS desvio_padrao,
  SUM(freight) AS soma
FROM northwind_orders;
```
**Print do resultado no mysql:**

![ Número de Resgistos](https://github.com/ThamaraCrispim/SQL-PoD-Academy/blob/main/imagens/estat%C3%ADstica%20basica.png)


**Análise dos Resultados**

1. Valor Mínimo (0.02)
O menor valor de frete registrado é 0,02.
Isso indica que há pedidos com frete praticamente nulo, o que pode ser resultado de promoções, entregas locais ou até mesmo possíveis erros de cadastro.
2. Valor Máximo (1007.64)
O maior valor de frete é 1007,64.
Esse valor é bastante elevado em relação à média, sugerindo a existência de pedidos excepcionais (talvez entregas internacionais, cargas muito grandes ou erros de digitação).
3. Média (78.24)
O valor médio do frete é 78,24.
Isso representa o custo médio de envio dos pedidos registrados no banco de dados.
4. Desvio Padrão (116.71)
O desvio padrão é 116,71, que é maior do que a média.
Isso indica uma grande dispersão nos valores de frete, ou seja, há bastante variação entre os pedidos (alguns com fretes muito baixos e outros com valores muito altos).
5. Soma Total (64942.69)
A soma total dos valores de frete é 64.942,69.
Esse valor representa o total arrecadado (ou gasto) com fretes em todos os pedidos registrados

###  Distribuição de Valores (Frequência)


```sql
select ship_country, count(*) As frequencia 
from northwind_orders
Group by ship_country
order by frequencia desc
```
**Print do resultado no mysql:**

![Distribuição de Valores](https://github.com/ThamaraCrispim/SQL-PoD-Academy/blob/main/imagens/Frequencia.png)

**Análise:**
1- Países com Maior Número de Pedidos: Alemanha (Germany) e Estados Unidos (USA) lideram com o mesmo número de pedidos (122 cada), indicando que são mercados muito relevantes para a empresa. Brasil aparece em terceiro lugar, mostrando também grande importância no volume de vendas. Países europeus como França, Reino Unido, Áustria, Suécia, Itália e Espanha também têm destaque, sugerindo uma forte atuação da empresa na Europa.

![Distribuição de Valores](https://github.com/ThamaraCrispim/SQL-PoD-Academy/blob/main/imagens/frequencia01.png)

**Análise:**
2- Esses países têm participação menor no volume total de pedidos.
Destaca-se a presença de países da Europa Ocidental e do Norte, além da Argentina e Portugal.

###  Distribuição Temporal (se houver datas)

```sql
SELECT YEAR(order_date) AS ano, COUNT(*) AS total
FROM northwind_orders
GROUP BY ano
ORDER BY ano;
```
![Distribuição](https://github.com/ThamaraCrispim/SQL-PoD-Academy/blob/main/imagens/DATA.png)

***Análise:**
1-Crescimento Significativo em 1997
O número de pedidos aumentou de 152 em 1996 para 408 em 1997, representando um crescimento de aproximadamente 168%.
Esse salto pode indicar um período de expansão da empresa, entrada em novos mercados, aumento da base de clientes ou estratégias comerciais mais agressivas.

2-Queda em 1998
Em 1998, houve uma redução para 270 pedidos, uma queda de cerca de 33% em relação ao ano anterior.
Essa diminuição pode estar relacionada a fatores como sazonalidade, mudanças no mercado, ajustes internos ou até mesmo questões econômicas externas.

3-Tendência Geral
O período analisado mostra um pico em 1997, seguido por uma estabilização em um patamar superior ao de 1996.
Mesmo com a queda em 1998, o volume de pedidos permaneceu consideravelmente maior do que no início da série.

### Identifique Valores Únicos

```sql
SELECT COUNT(DISTINCT ship_country) AS valores_unicos FROM northwind_orders;
````
![Distribuição](https://github.com/ThamaraCrispim/SQL-PoD-Academy/blob/main/imagens/pa%C3%ADs.png)

***Análise:**
A presença de 21 países distintos demonstra que a empresa fictícia Northwind possui uma atuação internacional significativa, atendendo clientes em diversos mercados ao redor do mundo. Esse dado pode ser útil para análises futuras sobre distribuição de vendas, identificação de mercados prioritários e estratégias de expansão.



