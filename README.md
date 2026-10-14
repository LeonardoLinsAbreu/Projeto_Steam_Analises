# Steam — Análise de Dados com Python e Power BI (Portfólio)

Projeto pessoal de portfólio que reúne tratamento de dados (ETL), análise exploratória (EDA) e um dashboard interativo no Power BI a partir de um dataset do catálogo da platoforma Steam. O objetivo é explorar preços, avaliações, lançamentos, gêneros e métricas de atividade, além de permitir que o usuário encontre títulos por preço, gênero e idioma de áudio.

[Abrir a pasta do dashboard](dashboard/) · [Baixar o relatório Power BI](dashboard/Projeto_Steam_BI_Final.pbix)

## Fonte dos dados:

- Dataset: Steam Games Dataset — FronkonGames (Kaggle).
- Arquivo tratado: [steam_dataset_limpo.csv](steam_dataset_limpo.csv).
- Moeda dos preços: dólar americano (USD / US$).

Os resultados descrevem a base utilizada no projeto. O relatório não acompanha a loja em tempo real, e os preços não representam necessariamente os praticados na região brasileira da Steam.

## Tecnologias utilizadas:

Python, Pandas e NumPy | Inspeção, limpeza e transformação dos dados.
Matplotlib e Seaborn | Visualizações da análise exploratória.
Jupyter Notebook | Registro do código, dos gráficos e das interpretações.
Power Query | Preparação dos dados para o relatório.
Power BI e DAX | Modelagem, indicadores, filtros e visualização interativa.

## 1. Tratamento dos dados — ETL

O notebook [01_ETL_Limpeza_Steam_games.ipynb](01_ETL_Limpeza_Steam_games.ipynb) documenta o tratamento da base:

- Correção do cabeçalho que reúne Discount e DLC count em um único nome.
- Inspeção de dimensões, tipos, valores ausentes e estatísticas descritivas.
- Remoção de linhas duplicadas e de registros sem nome.
- Preenchimento de valores ausentes conforme as regras definidas no notebook.
- Conversão dos preços para valores numéricos e das datas de lançamento para datas.
- Criação de total de avaliações, taxa de aprovação e faixas de preço.
- Remoção de colunas fora do escopo da análise.
- Deduplicação adicional por nome e exportação para CSV sem a coluna de índice.

## 2. Análise exploratória — EDA

O notebook [02_EDA_Exploratoria_Steam_games.ipynb](02_EDA_Exploratoria_Steam_games.ipynb) utiliza o CSV tratado para explorar cinco temas:

1. Evolução dos lançamentos entre 2010 e 2025.
2. Relação entre faixa de preço e tempo de jogo, usando Median playtime forever, convertido em horas e agregado por média em cada faixa.
3. Média de Peak CCU por faixa de preço.
4. Os dez títulos com maior Peak CCU.
5. Soma de Peak CCU por gênero, após separar as categorias de cada título.

Entre os padrões discutidos estão a expansão do catálogo, a concentração de atividade em alguns títulos e uma relação entre preço e tempo de jogo que não cresce de forma uniforme entre todas as faixas.

## 3. Dashboard — Power BI

O relatório [Projeto_Steam_BI_Final.pbix](dashboard/Projeto_Steam_BI_Final.pbix) apresenta duas páginas com identidade visual inspirada na Steam.

### Visão Geral do Catálogo

Apresenta o tamanho e a composição da base por meio de:

- Total de títulos e de avaliações.
- Preço médio dos títulos pagos e percentual de títulos com preço zero.
- Participação das avaliações positivas e negativas, com aprovação geral.
- Quantidade de lançamentos por ano, a partir de 2005.
- Quantidade de títulos por faixa de preço.
- Dez gêneros com mais títulos.
- Filtro de idioma de áudio.

### Explore os Jogos

Permite consultar títulos individuais por meio de:

- Tabela com ID, nome, preço, aprovação, total de avaliações e link para a Steam.
- Filtros de preço, idioma de áudio e gênero.
- Indicador de títulos encontrados.
- Botão para limpar filtros e navegação entre as páginas.

## Modelagem e Indicadores:

A preparação no Power BI inclui uma tabela principal de títulos, uma dimensão de calendário e dimensões de gênero e idioma conectadas por tabelas de associação. Essa organização permite filtrar títulos que possuem vários gêneros ou idiomas. As medidas DAX dão suporte à contagem de títulos, ao total de avaliações, à aprovação geral, ao preço médio dos pagos e ao percentual de títulos com preço zero. A aprovação geral utiliza a proporção entre o total de avaliações positivas e o total de avaliações positivas e negativas, em vez de uma média simples das taxas de cada título.

## Indicadores do painel sem filtros:

Indicador: Valor exibido.
Total de títulos:	124.644.
Total de avaliações: 144.022.096.
Aprovação geral: 86,2%.
Preço médio dos títulos pagos: US$ 6,11.
Títulos com preço zero: 21,2%.

Esses indicadores correspondem à base utilizada no relatório e mudam conforme os filtros aplicados.

## Organização do repositório:

- [01_ETL_Limpeza_Steam_games.ipynb](01_ETL_Limpeza_Steam_games.ipynb)	Tratamento e exportação dos dados
- [02_EDA_Exploratoria_Steam_games.ipynb](02_EDA_Exploratoria_Steam_games.ipynb)	Gráficos e interpretações da EDA
- [steam_dataset_limpo.csv](steam_dataset_limpo.csv)	Base tratada
- [](dashboard/)	Relatório Power BI e documentação da etapa

## Interpretação dos resultados:

- Avaliações não são vendas: o volume de avaliações não fornece diretamente a quantidade de cópias vendidas.
- Peak CCU não representa usuários únicos: somar picos de títulos não equivale a medir pessoas presentes simultaneamente em toda a plataforma.
- Gêneros podem se sobrepor: um título pode contribuir para mais de uma categoria.
- Preço zero não significa necessariamente gratuito: o ETL também converte preços ausentes ou inválidos para zero.
- A base inclui diferentes tipos de títulos da Steam: as análises não pressupõem que todos os registros sejam exclusivamente jogos.
- Deduplicação por nome é uma escolha do tratamento: registros com IDs diferentes e o mesmo nome podem ter sido removidos.
- Associação não demonstra causalidade: as relações exploradas dependem do conjunto de dados e das métricas utilizadas.
  
# Autor

Leonardo Lins de Abreu Borges
