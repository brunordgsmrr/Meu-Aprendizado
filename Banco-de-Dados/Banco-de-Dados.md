# Banco de dados

## Introdução

#### Fundamentos do Banco de dados

**O que são dados? ** Valores brutos, fatos brutos, observações documentados, registros soltos, que são recolhidos e armazenados sem sofrer qualquer tratamento. Ex: "11987475587" , "Daniel".

**O que são informações?** Estruturação de dados, organização de dados. Conjunto de dados relacionados entre si que geram valor, que criam sentidos aos dados. Material de conhecimento.

#### Modelo relacional

**Definição:** Modelo mais comum, que classifica e organiza as informações em tabelas com linhas e colunas. As linhas, ou tuplas, são os dados organizados, são os valores das tabelas, e as colunas são os atributos destes dados.

<img src="..\Imagens\image-1.png" alt="image-1" style="zoom:50%;" />

**O que pode ser definido como tabelas?**

- **Coisas tangíveis**

  Elementos físicos (carros, produto, animal).

- **Funções**

  Perfis de usuários, status de compra

- **Eventos ou ocorrências**

  Produtos de um pedido, histórico de dados

**Colunas importantes**

- **Chave Primária / Primary Key / PK**

  Conjunto de um ou mais campos que nunca se repetem. Identidade da tabela. São utilizados como índice de referência na criação de relacionamentos entre tabelas.

- **Chave Estrangeira / Foreign Key / FK**

  Valor de referência a uma PK de outra tabela ou da mesma tabela para criar relacionamentos.

<img src="..\Imagens\image-2.png" alt="image-2" style="zoom:50%;" />

#### Sistemas de gerenciamento de banco de dados (SGBD)

​	Conjunto de programas ou softwares responsáveis pelo gerenciamento de um banco de dados. Programas que facilitam a administração de um banco de dados. Ex: PostgreSQL, MySQL.

#### O que é o PostgreSQL?

Sistema de gerenciamento de banco de dados objeto relacional.

Teve início no Departamento de Ciência da Computação na Universidade da Califórnia em Berkeley em 1986.

SGBD Opensource.

<img src="..\Imagens\image-3.png" alt="image-3" style="zoom:50%;" />



## Instalação PostgreSQL

#### Linux (Ubuntu)

**Criar um arquivo de configuração: **

```
sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'
```

**Importar o chave do repositório oficial: **

```
wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
```

**Atualizar os repositórios: **

```
sudo apt-get update
```

**Instalar o PostgreSQL:**

```
sudo apt-get -y install postgresql
```

