# Trabalho Final

Esse arquivo descreve o trabalho final da disciplina Persistência com Frameworks.

## Nomenclatura do Mapeamento

Na tabela abaixo, a nomenclatura usada para a criação das tabelas (e seus campos):

Objeto | Nomenclatura
--------|------------
Tabelas | TBL_NOMEPLURAL
Chaves primárias | PK\_ABREVIACAO\_TABELA
Chaves estrangeiras | FK\_ABREVIACAO\_TABELA
Valores numéricos | NU_NOMECAMPO
Textos | NM_NOMECAMPO
Múltiplos Valores | ST_NOMECAMPO
Data | DT_NOMECAMPO

## Cardinalidade entre as Entidades

### Produto
1. Um produto pertence a um departamento e um departamento pode ter mais de um produto
2. Um produto tem um responsável e um responsável tem apenas um produto.

### Avaliação
1. A avaliação contém um produto e um produto pode estar em mais de uma avaliação.
2. A avaliação tem um autor e o autor pode ter várias avaliações.
3. Uma avaliação tem um ou mais itens de avaliação.

## Questões

### Atributos (1,5 pontos)

Mapear os atributos das entidades de acordo com a nomenclatura definida. 

### Relacionamentos (2 pontos)

Mapear os relacionamentos entre os objetos observando a nomenclatura definida. Todos os relacionamentos devem ser LAZY.

### Herança (2 pontos)

Mapear a hierarquia de objetos que representam os itens da avaliação.

### Queries (2 pontos)

Criar as seguintes named queries:

1. (JPQL) - Todos os Produtos
   * Nome da Query: Produto.todos   

2. (JPQL) - As Avaliações que possuem Issues com mais de 3 votos
   * Nome da Query: Avaliacao.issuesAcima3Votos
   * ***Evite registros duplicados***

3. (JPQL) - Quantidade de débitos técnicos abertos e fechados para um determinado produto
   * Nome da Query: Produto.qtdeDebitosTecnicos
   * Parametro da query: idProduto
   * O resultado deve ser o total associado com cada status

4. (SQL) - Qual o departamento que tem o maior número de avaliações
   * Nome da Query: Departamento.maiorQtdeAvaliacoes
   * O resultado deve ser a entidade.

```Atenção: As queries devem ser declaradas em XML.```

### Validação (2 pontos)

O que deve ser garantido:

### Usuário
* O nome do usuário não deve ser nulo, nem vazio.

### Departamento
* Nome do departamento não pode ser nulo, nem vazio.

#### Produto
* O departamento de produto não pode ser nulo
* O responsável pelo produto não pode ser nulo.

#### Avaliação
* Produto não pode ser nulo
* Autor não pode ser nulo
* A avaliação tem que ter pelo menos um item

### Item da Avaliação
* O comentário não pode nulo, nem ser vazio e deve ter no máximo 500 caracteres.
* O status não pode ser nulo.

### Débito Técnico
* O custo do débito deve ser no intervalo de 1 a 5

### Eventos (0,5 pontos)

1. Garantir que a data de avaliação esteja preenchida ao inserir.
2. Garantir que o status de um item que vai ser criado na avaliação esteja com o status Aberto.
3. Garantir que a quantidade de votos de uma issue seja criada com 0.

## Baixando o Projeto

### Via GIT

```git clone https://github.com/tarsobessa/jpa-trabalho-final.git```

### Via Download

Baixar da página https://github.com/tarsobessa/jpa-trabalho-final e descompactar em disco

## Importar na IDE

1. Importar no Eclipse como projeto Maven. File > Import > Existing Maven Projects

2. Fazer um Maven Update para garantir que o Eclipse aplique as configurações do pom.xml

## Executando DB

Executar como aplicação Java usando a classe Main (br.edu.uni7.Main) disponibilizada no projeto. 
