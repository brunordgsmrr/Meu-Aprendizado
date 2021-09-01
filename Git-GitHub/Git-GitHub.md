# Git e GitHUB

## Introdução ao git

 - **O que é Git** - é um sistema de versionamento distribuído, utilizado no desenvolvimento de *software*. Criado por Linus Torvalds, criador e mantenedor do Kernel Linux.

**Instalação do Git** - https://git-scm.com/downloads

### Comando básicos terminal via CLI (Command Line Interface)

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

A sigla SHA significa *Secure Hash Algorithm* (Algoritmo de Hash Seguro), é um conjunto de funções hash criptográficas projetadas pela NSA (Agência de Segurança Nacional dos EUA).

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

<img src="..\Imagens\image-70.jpg" alt="image-70" width="50%"/>

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

<img src="..\Imagens\image-71.jpg" alt="image-71" width="50%"/>

<img src="..\Imagens\image-72.jpg" alt="image-72" width="75%"/>

**Commit**

Objeto que contem tamanho, hash da tree que esta apontando, nome do autor, uma mensagem é uma marcação de tempo

<img src="..\Imagens\image-73.jpg" alt="image-73" width="50%"/>

<img src="..\Imagens\image-74.jpg" alt="image-74" width="75%"/>

## Primeiros comandos com Git

Inicializar um repositório e criar um arquivo ".git", para começar o versionamento.

````bash
git init
````

Configurar o git pela primeira, para que o autor das alterações sejam identificados tanto no repositório local quanto no remoto:

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

<img src="..\Imagens\image-75.jpg" alt="image-75" width="75%"/>



## Ciclo de vida dos arquivos no Git

### Untracked e Tracked

<img src="..\Imagens\image-76.jpg" alt="image-76" width="75%"/>

**Untracked** - O arquivo não esta sendo versionado

**Tracked** - O arquivo esta sendo versionado, podendo estar em estado de "Unmodified", "Modified" e "Staged".

**Unmodified** - O arquivo não sofreu alterações, ou seja esta em sua ultima versão.

**Modified** - O arquivo foi modificado e esta preparado para um "git add", que o adicionara em "Staged".

**Staged** - Onde o arquivo estará preparado para uma "commit", o deixando em "unmodified" como sendo sua ultima versão.

### Funcionamento do Repositório 

<img src="..\Imagens\image-77.jpg" alt="image-77" width="75%"/>

**Working Directory** - Fica os arquivos que estão sendo trabalhados.

**Staging Area** - Onde fica os arquivos prontos para "commit".

**Local Repository** - Onde fica as ultimas versões dos arquivos.

**Remote Repository** - Seria um repositório remoto, 

## Introdução ao GitHub

**O que é GitHub** - é uma plataforma de repositórios remoto para projetos e controle de versão do Git, além de ser uma rede social para desenvolvedores, onde é possível contribuir com projetos privados e *Open Source*.

### Iniciar um repositório remoto

**Criar um repositorio no GitHub** 

<img src="..\Imagens\image-78.jpg" alt="image-78" width="75%"/>

**Iniciar o repositório remoto** 

<img src="..\Imagens\image-79.jpg" alt="image-79" width="75%"/>

Ou deve ser iniciado um repositório local como mostrado anteriormente, para depois apontar para o remoto com "git remote add origin \<link>" e "git push -u origin master".

Ou se já existir um repositório local, apenas executar "git remote add origin \<link>" e "git push -u origin master".

## Resolvendo conflitos

Caso ocorra de um arquivo estar sendo alterado nos mesmo local por duas pessoas e elas tentem subir este arquivo para o repositório remoto, ira ocorrer um conflito de versão.

<img src="..\Imagens\image-80.jpg" alt="image-80" width="75%"/>

por exemplo, dois desenvolvedores começaram a editar o código de um arquivo que puxaram do repositório remoto, por exemplo esse código com duas funções.

<img src="..\Imagens\image-81.jpg" alt="image-81" width="75%"/>

Porem cada um adicionou uma função nova em um mesma linha, o primeiro ao terminar criou sua commit do arquivo e subiu com a função *div* para o repositório remoto. 

<img src="..\Imagens\image-82.jpg" alt="image-82" width="75%"/>

Algum tempo o segundo subiu o seu código com a função *multi* .

<img src="..\Imagens\image-83.jpg" alt="image-83" width="75%"/>

Porem o Github por ter recebido o arquivo do primeiro desenvolver, ira considerar o do segundo como a penúltima versão, ou seja, uma versão desatualizada, será necessário executar git pull para puxar a ultima versão do código, a que foi adicionada pelo primeiro desenvolvedor e modificar novamente, apenas adicionando sua parte do código.

<img src="..\Imagens\image-84.jpg" alt="image-84" width="75%"/>

