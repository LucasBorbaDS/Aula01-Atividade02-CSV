
# Aula 01 - Atividade 02

## Organização do projeto

- `data/`: arquivos de dados, como o CSV do IBGE.
- `notebooks/`: notebooks usados para análise e visualização.
- `src/`: código-fonte do pacote Python.

## Executar a atividade

Abra o notebook `notebooks/Atividade_02.ipynb` no VS Code e execute a célula de código.

## Tecnologias utilizadas

A atividade foi feita com a biblioteca `pandas`, que facilita a leitura do arquivo CSV e permite visualizar os dados organizados em uma tabela.

## Entendendo o código

```python
tabela = pd.read_csv(
	"../data/csv_IBGE.csv",
	sep=";",
	skiprows=1,
	usecols=range(5)
)
```

- `pd.read_csv()`: lê um arquivo CSV e transforma os dados em uma tabela do pandas.
- `"../data/csv_IBGE.csv"`: indica o caminho do arquivo. O `..` volta da pasta `notebooks` para a pasta principal do projeto.
- `sep=";"`: informa que as colunas do arquivo são separadas por ponto e vírgula.
- `skiprows=1`: ignora a primeira linha, que contém apenas o título do arquivo.
- `usecols=range(5)`: carrega as cinco primeiras colunas do CSV.

Depois da leitura, o código usa:

```python
tabela = tabela.dropna(subset=["NOME DO MUNICÍPIO"])
```

`dropna` remove as linhas que não possuem um nome de município. Assim, as linhas vazias e os textos extras no final do arquivo não aparecem na tabela final.
