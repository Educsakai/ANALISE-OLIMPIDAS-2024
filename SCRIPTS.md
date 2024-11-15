# Projeto de Análise de Dados das Olimpíadas Usando SQL

Este projeto é uma análise exploratória de dados de Olimpíadas, focando em consultas SQL para entender a relação entre medalhas, PIB, e população dos países participantes.

## Estrutura dos Dados

- **Tabela**: olimpiadas-441313.MEDALHAS.medalhas_olimpiadas
- **Colunas**:
  - `country`: Nome do país
  - `country_code`: Código do país
  - `region`: Continente
  - `gold`: Medalhas de ouro
  - `silver`: Medalhas de prata
  - `bronze`: Medalhas de bronze
  - `total`: Total de medalhas
  - `gdp`: Produto Interno Bruto do país
  - `gdp_year`: Ano de referência do PIB
  - `population`: População do país

## Consultas SQL

### 1. Total de Medalhas por Continente

Consulta:
```sql
SELECT 
    region,
    SUM(gold) AS total_gold,
    SUM(silver) AS total_silver,
    SUM(bronze) AS total_bronze,
    SUM(total) AS total_medals
FROM 
    olimpiadas-441313.MEDALHAS.medalhas_olimpiadas
GROUP BY 
    region
ORDER BY 
    total_medals DESC;

### Total de Medalhas por Continente

| **Region**      | **Total Gold** | **Total Silver** | **Total Bronze** | **Total Medals** |
|-----------------|----------------|------------------|------------------|------------------|
| Europe          | 125            | 131              | 166              | 422              |
| Asia            | 100            | 83               | 99               | 282              |
| North America   | 54             | 58               | 66               | 178              |
| Oceania         | 28             | 27               | 19               | 74               |
| Africa          | 13             | 12               | 14               | 39               |
| South America   | 6              | 15               | 15               | 36               |
| Caribbean       | 2              | 1                | 4                | 7                |

#### Top 5 países com mais medalhas de Ouro
SELECT  
country, gold
from
olimpiadas-441313.MEDALHAS.medalhas_olimpiadas
order by
gold desc
limit 5
| country       | gold |
|---------------|------|
| United States | 40   |
| China         | 40   |
| Japan         | 20   |
| Australia     | 18   |
| France        | 16   |





