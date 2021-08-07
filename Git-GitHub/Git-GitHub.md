# Git e GitHUB

## Introdução

 - **O que é Git** - é um sistema de versionamento distribuído, utilizado no desenvolvimento de *software*. Criado por Linus Torvalds, criador e mantenedor do Kernel Linux.
 - **O que é GitHub** - é uma plataforma de repositórios remoto para projetos e controle de versão do Git, além de ser uma rede social para desenvolvedores, onde é possível contribuir com projetos privados e *Open Source*.

**Instalação do Git** - https://git-scm.com/downloads

## Comando básicos terminal via CLI (Command Line Interface)

#### Windows

- **cd \<caminho>** - (change directory)Muda para o diretório especificado
- **dir** - Lista o conteúdo do diretório atual
- **mkdir** - Cria um diretório
- **del** - Deleta apenas arquivo
- **rmdir** - Deleta diretório

#### Unix

- **cd \<caminho>** - (change directory)Muda para o diretório especificado
- **ls** - Lista o conteúdo do diretório atual
- **mkdir** - Cria um diretório
- **rm -rf** - Remover arquivos, (flag "r" - recursivo) apaga sub-pastas, (flag "f" - force) apaga sem confirmação

## Entendendo o Git

### SHA1

A sigla SHA significa *Secure Hash Algorithm* (Algoritmo de Hash Seguro), é um conjunto de funções hash criptográficas projetadas pela NSA(Agência de Segurança Nacional dos EUA).

A encriptação gera conjunto de caracteres identificador de 40 dígitos.

É uma forma curta de representar um arquivo

**Exemplo:**

`````bash
echo "ola mundo" | openssl sha1
> (stdin)= f9fc856e559b950175f2b7cd7dad61facbe58e7b
`````

### Objetos internos do Git

**Blob** 

Objeto onde é guardado o conteúdo.

<img src="..\Imagens\image-70.png" alt="image-70" width="50%"/>

````bash
echo 'conteudo' | git hash-object --stdin
> fc31e91b26cf85a55e072476de7f263c89260eb1

echo -e 'conteudo' | openssl sha1
> 65b0d0dda479cc03cce59528e28961e498155f5c

echo -e 'blob 9/0conteudo' | openssl sha1
> fc31e91b26cf85a55e072476de7f263c89260eb1
````

**Tree**

Objeto que contem um tamanho, o nome do arquivo que esta na *blob* ou outras *tree* e a *hash* da *blob*. Apontam para a *blob* ou para outra *tree*, alterações em um arquivo, iram alterar o *hash* da *blob* que ira alterar o *hash* da *tree*.

<img src="..\Imagens\image-71.png" alt="image-71" width="50%"/>

<img src="..\Imagens\image-72.png" alt="image-72" width="75%"/>

**Commit**

Objeto que contem tamanho, hash da tree que esta apontando, nome do autor, uma mensagem é uma marcação de tempo

<img src="..\Imagens\image-73.png" alt="image-73" width="50%"/>

<img src="..\Imagens\image-74.png" alt="image-74" width="75%"/>

## Primeiros comandos com Git

Inicializar um repositório e criar um arquivo ".git", para começar o versionamento.

````bash
git init
````

Configurar o git pela primeira:

````bash
git config --global user.email "email@email.com"
git config --global user.name "user"
````

Adicionar os arquivos a ser feito o commit.

`````bash
git add .
`````

Fazer a commit.

`````bash
git commit -m "Mensagem"
`````



**Arquivos Markdown**

<img src="..\Imagens\image-75.png" alt="image-75" width="75%"/>



## Ciclo de vida dos arquivos no Git





## Introdução ao GitHub





## Resolvendo conflitos



