# Filmes - Análise de Dados com Python

Projeto de estudo desenvolvido para praticar Python e conceitos básicos de exploração e análise de dados.

## Sobre o projeto

Este projeto foi realizado como exercício de acompanhamento de uma aula do Alex The Analyst sobre análise de dados de filmes utilizando Python.

As etapas da aula foram usadas como base para estudar a manipulação de dados, a criação de gráficos e a análise de correlações. O notebook contém comentários em português para explicar os comandos e o objetivo de cada etapa.

## Dataset

O projeto utiliza uma base de filmes chamada **movies.csv**, contendo informações como:

- título do filme;
- ano e data de lançamento;
- gênero e classificação indicativa;
- empresa produtora;
- orçamento e bilheteria;
- nota e quantidade de votos;
- diretor, roteirista e ator principal.

Essas informações são utilizadas para explorar a distribuição dos valores, comparar características dos filmes e observar possíveis relações entre orçamento, bilheteria e notas.

## Principais etapas

- Inspeção inicial dos dados
- Verificação de valores ausentes e tipos das colunas
- Exploração de possíveis valores fora do padrão
- Consulta de registros duplicados
- Ordenação dos filmes por bilheteria
- Comparação entre orçamento, bilheteria e notas
- Cálculo de correlações
- Visualização das correlações com mapas de calor
- Agrupamento da bilheteria por empresa e por ano
- Conversão de categorias em códigos numéricos

## Análises realizadas

### Inspeção inicial dos dados

A base é carregada com `pd.read_csv()` e exibida para conhecer as informações disponíveis.

Em seguida, `dtypes` é utilizado para conferir os tipos das colunas. Para verificar dados ausentes, um laço percorre as colunas e utiliza `isnull()` e `np.mean()` para calcular a proporção de valores nulos.

Essa etapa ajuda a entender a estrutura da base antes das análises.

### Exploração da bilheteria

Um boxplot da coluna `gross` é utilizado para observar a distribuição da bilheteria e identificar possíveis valores fora do padrão.

Também é utilizada a função `sort_values()` para visualizar os filmes com maiores bilheterias. Valores elevados não são necessariamente erros e precisam ser interpretados considerando o contexto dos filmes.

### Consulta de registros duplicados

O notebook utiliza `drop_duplicates()` para retornar uma versão da tabela sem linhas totalmente repetidas.

Como o resultado não é atribuído a uma variável e não há uso de `inplace=True`, essa operação não remove registros do DataFrame original.

### Comparação entre orçamento, bilheteria e notas

São utilizados gráficos de dispersão e regressão para explorar as relações entre `budget`, `gross` e `score`.

Esses gráficos permitem observar a distribuição dos pontos e tendências entre as variáveis, sem demonstrar uma relação de causa e efeito.

### Análise de correlações

O notebook explora os métodos de Pearson, Kendall e Spearman para comparar relações entre variáveis numéricas.

As matrizes de correlação também são apresentadas em mapas de calor, utilizando `sns.heatmap()`, para facilitar a leitura dos coeficientes.

Em outra etapa, os pares de correlação são organizados e filtrados por magnitude superior a 0,5.

### Agrupamento por empresa e ano

As funções `groupby()` e `sum()` são utilizadas para somar a bilheteria dos filmes por empresa e por combinação de empresa e ano.

Os resultados são ordenados para selecionar os 15 maiores valores. Essa soma representa a bilheteria dos filmes presentes na base, não o lucro das empresas.

### Conversão de categorias em códigos

São explorados `factorize()` e `cat.codes` para representar valores por códigos numéricos.

Essa etapa ajuda a estudar a conversão de categorias, mas os códigos de categorias sem ordem não representam grandezas. Por isso, suas correlações exigem cuidado na interpretação.

## Aprendizados

O projeto reúne práticas de leitura e exploração de dados, agrupamento de informações, criação de gráficos e cálculo de correlações.

Também permite observar detalhes do comportamento do Pandas, como a diferença entre retornar uma nova tabela e modificar a original, além das limitações de representar categorias por números.

## Observações sobre o notebook

O código da aula foi adaptado para permitir a execução das células em sequência. Os ajustes incluem a leitura do CSV por caminho relativo, o cálculo de correlações apenas entre colunas numéricas e a separação das conversões de categorias em uma cópia da tabela.

As 30 células foram testadas em sequência com os 7.668 registros da base, sem erros de execução.

Para executar o notebook, é necessário baixar o arquivo movies.csv e colocá-lo na pasta data/.

O notebook publicado está sem saídas salvas. Os gráficos e as tabelas serão gerados ao executar as células em um ambiente compatível com Jupyter.

O swarmplot utiliza uma amostra de até 500 filmes e pode apresentar avisos de sobreposição de pontos, sem interromper a execução.

## Conceitos de Python e análise de dados praticados

- Importação de bibliotecas
- DataFrames e seleção de colunas
- Laços `for` e condições `if`
- Funções `lambda`
- Verificação de valores nulos com `isnull()`
- Consulta de tipos com `dtypes`
- Ordenação com `sort_values()`
- Consulta de duplicados com `drop_duplicates()`
- Agrupamento e soma com `groupby()` e `sum()`
- Conversão de tipos com `astype()`
- Codificação com `factorize()` e `cat.codes`
- Correlações com `corr()`
- Gráficos de dispersão, regressão e mapas de calor

## Tecnologias

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook
- GitHub

## Estrutura

| Caminho | Conteúdo |
|---|---|
| `README.md` | Apresentação do projeto |
| `notebooks/analise_filmes.ipynb` | Notebook com código e comentários de estudo |
| `data/README.md` | Informações sobre a base de dados |

[Consultar o notebook](notebooks/analise_filmes.ipynb)

## Referência

Projeto baseado em uma aula/tutorial do **Alex The Analyst** sobre análise de dados de filmes com Python.

Tutorial utilizado: [Movie Correlation Project](https://www.youtube.com/watch?v=iPYVYBtUTyE)

Código-base: [Movie Portfolio Project](https://github.com/AlexTheAnalyst/PortfolioProjects/blob/main/Movie%20Portfolio%20Project.ipynb)
