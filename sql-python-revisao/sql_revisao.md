
# SQL

SQL (Structured Query Language) é uma linguagem utilizada para gerenciar e manipular bancos de dados relacionais. Com SQL, é possível realizar diversas operações, como consultas, inserções, atualizações e exclusões de dados, além de criar e modificar a estrutura dos bancos de dados.


## Select

é o comando que mais utilizaremos, utilizado para retornar campos/colunas das tabelas.


```{sql}

SELECT 
campo1,
campo2,
campo3
FROM TABELA

```

## Distinct

utilizado para trazer dados distintos (diferentes)


```{sql}

SELECT 
DISTINCT
marca,
produto
FROM produtos

```

## Where

Utilizado para fitrar dados de uma tabela de acordo com uma determinada condição (caso verdade)

```{sql}

SELECT 
email,
estado
FROM produtos

where estado = 'SC'

```

## Operadores

Aliado das condições, temos os operadores AND , OR, NOR

- AND : Quando utilizado, toda as condições precisam ser verdade para retornar os dados

```{sql}

SELECT 
email,
estado
FROM produtos

where estado = 'SC' and estado = 'SP'

```

- OR : Quando utilizado, toda umas das  condições precisam ser verdade para retornar os dados

```{sql}

SELECT 
email,
estado
FROM produtos

where estado = 'SC' or estado = 'RJ'

```

## Order

Utilizado para ordernar campos numericos ou textos(ordem alfabetica) de uma determinada tabela:


```{sql}

SELECT 
preco,
produto,
cateforia

FROM PRODUTOS

ORDER BY preco (sempre do menor para maior)
ORDER BY preco desc (do maior para o maior)

```

## limit - top

Utilizado para limitar o numero de registro que vamos explorar no retorno de uma query.


```{sql}

SELECT 
 top 1 *
FROM PRODUTOS

```

```{sql}

SELECT 
 *
FROM PRODUTOS

LIMIT 10;

```
**no sql server o limit não funciona**


## Funções de agregações

no sql temos funcoes de agregacoes que usamos realizar operacoes aritmeticas (soma, contagem , media, minimo,maximo)

- funcoes de agregacoes nao contam valores nulos
- quando tivermos uma agregacao e utilizarmos + de 1 campo, esses campos precisam estar dentro do groupby

```{sql}

SELECT 
 
 PRODUTO,
 SUM(VALOR) AS VALOR_SOMADO
FROM PRODUTOS

GROUPBY PRODUTO

```
 **HAVING**

HAVING E UTILIZADO PARA FILTRAR UMA INFORMACAO QUE VEIO DE UM AGREGACAO.

- FILTRE APENAS AS CIDADES QUE POSSUEM + DE 100 CLIENTES

**PODEMOS USAR O WHERE (DESDE QUE NAO SEJA COM AS COLUNAS AGREGADAS)**

``{sql}

SELECT 
 
 COUNT(CLIENTES),
 ESTADOS
FROM CLIENTES
GROUPBY ESTADOS

GROUP BY PRODUTO
HAVING COUNT(CLIENTES) >= 100

```