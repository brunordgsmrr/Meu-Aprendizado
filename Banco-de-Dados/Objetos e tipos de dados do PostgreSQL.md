# Objetos e tipos de dados do PostgreSQL

## O arquivo postgresql.conf

**Definição**

Arquivo onde estão definidas e armazenadas todas as configurações do servidor PostgreSQL. Alguns parâmetros só podem ser alterados com uma reinicialização do banco de dados. A view pg_settings, acessada por dentro do banco de dados, guarda todas as configurações atuais.

**postgresql.conf**

Ao acessar a view pg_settings, é possível visualizar todas as configurações atuais:

````sql
SELECT name, setting
FROM pg_settings;
````

Ou é possível usar o comando:

````sql
SHOW [parâmetro];
````

**Localização do arquivo postgresql.conf**

<img src="../Imagens/image-89.png" alt="image-89" width="75%"/>

Por padrão, encontra-se dentro do diretório PGDATA definido no momento da inicialização do cluster de banco de dados.

No sistema operacional Ubuntu, se o PostgreSQL foi instalado a partir do repositório oficial, o local do arquivo postgresql.conf será diferente do diretório de dados.

````bash
/etc/postgressql/[versão]/[nome do cluster]/postgresql.conf
````

<img src="../Imagens/image-90.png" alt="image-90" width="75%"/>

**Configurações de conexão**

- **LISTEN_ADDRESSES** - Endereço(s) TCP/IP das interfaces que o servidor PostgreSQL vai escutar/liberar conexões.
- **PORT** - A porta TCP que o servidor PostgreSQL vai ouvir. O padrão é 5432.
- **MAX_CONNECTIONS** - Número máximo de conexões simultâneas no servidor PostgreSQL.
- **SUPERUSER_RESERVED_CONNECTIONS** - Número de conexões (slots) reservados para conexões ao banco de dados de super usuários.
- **AUTRENTICATION_TIMEOUT** - Tempo máximo em segundos para o cliente conseguir uma conexão com o servidor.
- **PASSWORD_ENCRYPTION** - Algoritmo de criptografia das senhas dos novos usuários criados no banco de dados.
- **SSL** - Habilita a conexão criptografada por SSL (Somente se o PostgreSQL foi compilado com suporte SSL).

**Configuração de memória**

- **SHARED_BUFFERS** - Tamanho da memória compartilhada do servidor PostgreSQL para cache/buffer de tabelas, índices e demais relações.
- **WORK_MEM** - Tamanho da memória para operações de agrupamento e ordenação (ORDER BY, DISTINCT, MERGE JOINS).
- **MAINTENANCE_QORK_MEM** - Tamanho da memória para operações como VACUUM, INDEX, ALTER, TABLE.

## O arquivo pg_hba.conf

**Definição**

Arquivo responsável pelo controle de autenticação dos usuários no servidor PostgreSQL.

O formato do arquivo pode ser:

<img src="../Imagens/image-91.png" alt="image-91" width="75%"/>

**Métodos de autenticação**

- **TRUST** - (conexão sem requisição de senha)
- **REJECT** - (rejeitar conexões)
- **MD5** - (criptografia md5)
- **PASSWORD** - (Senha sem criptografia)
- **GSS** - (Generic Security Service Application Program Interface)
- **SSPI** - (Security Support Provider Interface - somente para windows)
- **KRB5** - (Kerberos V5)
- **IDENT** - (Utiliza o usuário do sistema operacional do cliente via ident server)
- **PEER** - (Utiliza o usuário do sistema operacional do cliente)
- **LDAP** - (ldap server)
- **RADIUS** - (radius server)
- **CERT** - (Autenticação via certificado ssl do cliente)
- **PAM** - (pluggable authentication modules. O usuário precisa estar no banco de dados)

<img src="../Imagens/image-92.png" alt="image-92" width="75%"/>

## O arquivo pg_ident.conf

**Definição**

Arquivo responsável por mapear os usuários do sistema operacional com os usuários do banco de dados. Localizado no diretório de dados PGDATA de sua instalação. A opção ident deve ser utilizada no arquivo pg_hba.conf.

 <img src="../Imagens/image-93.png" alt="image-93" width="75%"/>

## Comandos administrativos

**Ubuntu:**

````bash
# Listar todos os cluster PostgreSQL
pg_lscluster
# Criar um novo cluster PostgreSQL
pg_createcluster <version> <cluster name>
# Apagar um cluster PostgreSQL
pg_dropcluster <version> <cluster>
# Start, Stop, Status, Restart de clusters PostgreSQL
pg_ctlcluster <version> <cluster> <action>
````

**CentOS:**

````bash
systemctl <action> <cluster>

# Iniciar o cluster PostgreSQL
systemctl start postgresql-13
# Mostra o status do cluster PostgreSQL
systemctl status postgresql-13
# Para o cluster PostgreSQL
systemctl stop postgresql-13
# Restarta o cluster PostgreSQL
systemctl restart postgresql-13
````

**Binários do  PostgreSQL:**

- createdb
- createuser
- dropdb
- dropuser
- initdb
- pg_ctl
- pg_basebackup
- pg_dump / pg_dumpall (Não é backup)
- pg_restore
- psql
- reindexdb
- vacuumdb

## Arquitetura/Hierarquia

**Cluster**

Coleção de bancos de dados que compartilham as mesmas configurações (arquivos de configuração) do PostgreSQL e do sistemas operacional (porta, listen_addresses, etc).

**Banco de dados (database)**

Conjunto de schemas com seus objetos/relações (tabelas, funções, views, etc).

**Schema**

Conjunto de objetos/relações (tabelas, funções, views, etc).

<img src="../Imagens/image-94.png" alt="image-94" width="75%"/>

<img src="../Imagens/image-95.png" alt="image-95" width="75%"/>

## Conhecendo a ferramenta PGAdmin

**Importante para conexão:**

1. Liberar acesso ao cluster em postgresql.conf.
2. Liberar acesso ao cluster para p usuário do banco de dados em pg_hba.conf.
3. Criar/editar usuários.

**Para liberar acesso:**

Editar o postgresql.conf

<img src="../Imagens/image-96.png" alt="image-96" width="100%"/>

Ao iniciar a edição, desce ate "CONNECTIONS AND AUTHENTICATION", como mostra a imagem:

<img src="../Imagens/image-97.png" alt="image-97" width="100%"/>

Alterar o listen_addresses para os IP's que poderão se conectar, "*****" significa que todos tem acesso, sendo recomendado usa-lo apenas em testes.

<img src="../Imagens/image-98.png" alt="image-98" width="100%"/>

Por fim, iniciar o cluster com "pg_ctlcluster \<version> \<cluster name> start:

<img src="../Imagens/image-99.png" alt="image-99" width="100%"/>

Para alterar a senha do usuário postgres, basta acessar o usuário com "sudo su - postgres" e depois o psql, seguindo a imagem:

<img src="../Imagens/image-100.png" alt="image-100" width="75%"/>

Após isso deve editar o arquivo pg_hba.conf:

<img src="../Imagens/image-101.png" alt="image-101" width="75%"/>

Por padrão, o que está em verde estará escrito "peer", isso significa que para acessar o banco, ele casara o usuário da maquina com o do banco para acessar,  já o "md5" irá pedir uma senha para acessar.

**PgAdmin4**

Primeiro passo é criar um grupo para os servidores:

<img src="../Imagens/image-102.png" alt="image-102" width="75%"/>

<img src="../Imagens/image-103.png" alt="image-103" width="75%"/>

Criar um server:

<img src="../Imagens/image-105.png" alt="image-105" width="75%"/>

Obs: Comentar a finalidade do servidor é uma pratica recomendada.

<img src="../Imagens/image-106.png" alt="image-106" width="75%"/>

Agora com o grupo e o servidor criado, vamos criar o Banco de dados:

<img src="../Imagens/image-107.png" alt="image-107" width="75%"/>

Utilizando Query Tool, vamos executar os seguintes comandos:

<img src="../Imagens/image-108.png" alt="image-108" width="75%"/>

<img src="../Imagens/image-109.png" alt="image-109" width="75%"/>

Após ser criado o novo banco de dados não aparecera na lista, sendo necessário um refresh:

<img src="../Imagens/image-110.png" alt="image-110" width="50%"/>

<img src="../Imagens/image-111.png" alt="image-111" width="50%"/>

