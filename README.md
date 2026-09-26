# Projeto Steam Games — ETL & EDA (Portfólio)

## Resumo 

Este projeto utiliza o dataset `games.csv` retirado do Kaggle (https://www.kaggle.com/datasets/fronkongames/steam-games-dataset) para analisar os dados da plataforma Steam, entre os períodos de 2010-2025. O projeto visa a preparação e a análise exploratória (ETL → EDA) aplicados ao dataset. O objetivo deste projeto foi limpar e transformar os dados brutos, extrair métricas úteis e produzir gráficos/insights sobre preços, engajamentos, gêneros, top títulos e padrões de mercado e etc.

---

## Conteúdo dos notebooks (resumo das seções presentes)

### `01_ETL_Limpeza_Steam_games.ipynb` — Etapa inicial
O notebook está organizado nas seguintes seções:

1. **Importação, Definição e Carregamento do DataFrame**  
2. **Linhas e Colunas** — inspeção inicial de dimensão e colunas.  
3. **Análise Inicial do DataFrame** — checagem de dados nulos, tipos e amostras.  
4. **Mapeamento Inicial e Tipos de Dados** — conversões de tipos (ex.: datas, numéricos).  
5. **Descrição Geral - Estatísticas** — comando `.describe()` e estatísticas básicas.  
6. **Visão Geral e Tratamento de Duplicatas** — remoção / inspeção de duplicatas.  
7. **Preenchimento de Valores Nulos e Remoção de Registros Inválidos** — regras aplicadas.  
8. **Nova Visão dos Valores Nulos** — verificação pós-tratamento.  
9. **Limpeza e Formatação da Coluna de Preços** — normalização (remoção de símbolos, conversão para float).  
10. **Ajuste e Criação de Novas Métricas e Categorização de Preço** — criação de faixas de preço / colunas derivadas.  
11. **Limpeza e Formatação de Outras Colunas** — ex.: gêneros, datas, tags, colunas textuais.  

**Nota:** o notebook contém as etapas clássicas de ETL: leitura, validação, limpeza, transformação e a exportação do dataset limpo. Verifique as últimas células para ver se o notebook grava um CSV de saída (por exemplo `steam_dataset_limpo.csv`), se houver, esse CSV será o input do notebook da etapa de EDA.

---

### `02_EDA_Exploratoria_Steam_games.ipynb` — Insights e análises
As seções e insights documentados no notebook incluem:

- **A Explosão e Saturação do Mercado** — análise sobre o crescimento do catálogo e possíveis sinais de saturação.  
- **O Mito do Preço vs. Engajamento** — investigação da relação entre preço e métricas de engajamento/vendas.  
- **O "Vale da Morte" Indie (Pico de Atenção por Preço)** — análise de performance de jogos indies por faixa de preço.  
- **A Elite Absoluta (Top 10 Steam)** — listagem/análise dos top 10 por alguma métrica (vendas, avaliações ou jogadores).  
- **O Domínio dos Gêneros: O que a Steam mais joga?** — distribuição por gênero e insights de preferência.  
- **Conclusão da Análise Exploratória (EDA)** — resumo das análises feitas.

O notebook utiliza bibliotecas do Python `pandas`, `numpy`, `matplotlib` e `seaborn` para análises, visualizações e construções de gráficos.

---

## Dependências

- Python 3.8+
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Seaborn

---

## Autor

Leonardo Lins de Abreu Borges
