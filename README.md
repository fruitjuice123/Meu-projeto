# Dashboard de Desmatamento dos Biomas Brasileiros

<p align="center">
  <img width="900" height="136" alt="banner" src="https://github.com/user-attachments/assets/1e5e5235-c9fb-4e8f-a19d-9bf0e4abe2c5" />
</p>

## Sobre o Projeto

Este projeto analisa 40 anos de desmatamento nos biomas brasileiros
utilizando modelagem analítica em Power BI.

O dashboard permite:

- análise temporal;
- comparação entre biomas;
- ranking de estados;
- monitoramento regional;
- KPIs executivos;
- filtros dinâmicos.

---

## Fluxo de Transformação dos Dados
<p align="center">
  <img width="2385" height="1941" alt="mermaid-diagram" src="https://github.com/user-attachments/assets/89108ecd-9173-400b-9e8a-f203aaffce20" />
</p>

-------------------------------------------------------------------------------------------------------------------------------------------------------


# Dashboard de Desmatamento - Biomas Brasil (1985-2024)

[![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=power%20bi&logoColor=black)](https://powerbi.microsoft.com/)
[![DAX](https://img.shields.io/badge/DAX-FFB74D?style=for-the-badge&logo=powerbi&logoColor=black)](https://learn.microsoft.com/en-us/dax/)
[![Power Query](https://img.shields.io/badge/Power%20Query-2B579A?style=for-the-badge&logo=microsoft&logoColor=white)](https://learn.microsoft.com/en-us/power-query/)

Dashboard analítico para monitoramento de **40 anos de desmatamento** nos biomas brasileiros, com modelagem tabular, medidas DAX e visualizações interativas.  
Projeto desenvolvido como case de Business Intelligence e transformação de dados.

---

## Visão Geral

- **Período:** 1985 – 2024
- **Biomas monitorados:** 6 (Amazônia, Cerrado, Caatinga, Mata Atlântica, Pampa, Pantanal)
- **Regiões:** 5
- **Estados:** 27
- **Área total desmatada:** 148,3 milhões de hectares
- **Desmatamento em 2024:** 3,57 milhões de hectares

---

## Principais Funcionalidades do Dashboard

- Análise temporal (série histórica)
- Comparação entre biomas
- Ranking de estados mais desmatados
- Monitoramento por região
- KPIs executivos (total, média anual, bioma mais afetado)
- Filtros dinâmicos por bioma, região e estado
- Alertas de criticidade

---

## Processo de Transformação dos Dados

O dataset original estava em **formato wide** (colunas `y1985` … `y2024`), o que impedia análises temporais eficientes.

### Etapas no Power Query:

1. **Unpivot** – Conversão de wide para long format  
2. **Padronização** – Remoção do prefixo `y` e criação da coluna `Ano`  
3. **Conversão de tipos** – Garantia de integridade numérica  
4. **Modelagem tabular** – Estrutura otimizada para medidas DAX

plaintext
Antes (Wide)                     Depois (Long)
biome | state | y1985 | y1986    biome | state | Ano  | Área_ha
------|-------|------|------     ------|-------|------|--------
Amaz. | PA    | 1500 | 1800  →   Amaz. | PA    | 1985 | 1500
                                  Amaz. | PA    | 1986 | 1800

 Medidas DAX Implementadas (35 no total)
Categoria	Exemplos
KPIs principais	Área Total, Desmatamento 2024, Média Anual, Bioma Mais Afetado
Série temporal	Acumulado até Ano, Variação Ano Anterior, Tendência
Rankings	Desmatamento por Estado, por Bioma, por Região
Alertas	Status Alerta Bioma, KPI Desmatamento, Biomas acima da média
  Exemplo de medida DAX – Variação Ano Anterior:

dax
Variação % = 
DIVIDE([Desmatamento Ano] - [Desmatamento Ano Anterior], [Desmatamento Ano Anterior], 0)

  Visualizações Entregues
Aba	Tipo	Descrição
Evolução Temporal	Área Chart	Série histórica 1985–2024
Por Bioma	Barras + Pizza	Distribuição por bioma
Por Região	Barras Horizontal	Comparação regional
Estados	Barras Horizontal	Top 10 estados
Classe	Pizza	Primária vs Secundária
  Dashboard Final
Imagem ilustrativa do dashboard (adicione um print real do Power BI aqui)

https://image.png

  Aprendizados e Diferenciais Técnicos
Domínio de Unpivot no Power Query para remodelagem temporal

Criação de medidas DAX complexas (acumulados, variações, ranking dinâmico)

Implementação de alertas condicionais com emojis e semáforos

Modelagem tabular performática para 40 anos de dados

Documentação completa do fluxo de transformação e das medidas

 Dashboard-desmatamento-biomas
├──  README.md
├──  Dashboard_Desmatamento.pbix
├──  dados
│   └── MAPBIOMAS_BRAZIL_COL.10.1_DEFORESTATION.xlsx
├── imagens
│   └── dashboard_preview.png
└──  documentacao
    └── Documentacao_Dashboard.docx

  Equipe
Raul dos Santos

Morgana Ferreira

Tiago José

Leandro Ferreira Prado

Carolina Pantoja Miranda

André Almeida

Cristina Souza

Otavio Nunes

Guilherme Cabral

Gabriel Resende

 Referência dos Dados
Fonte: MapBiomas Brasil – Coleção 10.1
Arquivo original: MAPBIOMAS_BRAZIL_COL.10.1_DEFORESTATION.xlsx


 Nota
Este projeto foi desenvolvido para fins de estudo e demonstração de capacidades analíticas em Power BI. Os dados são públicos e utilizados conforme licença do MapBiomas.
