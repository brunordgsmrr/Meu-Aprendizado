# Fundamentos de Arquitetura de Sistemas

## Conceitos de Web Services

- São soluções para aplicações se comunicarem independente de linguagem, softwares e hardwares utilizados.
- Inicialmente era utilizado para troca de mensagens utilizando **XML (Extensible Markup Language)** sobre o protocolo HTTP sendo identificado por **URI (Uniform Resource Identifier)**.
- Podemos dizer que Serviços Web são API's que se comunicam por meio de rede sobre protocolo HTTP.

### Funcionamento do Web Service

<img src=".\Imagens\image-4.png" alt="image-4" width="200"" />

<img src=".\Imagens\image-5.png" alt="image-5" style="max-width:75%;" />

### Vantagens

- Linguagem comum
- Integração
- Reutilização de implementação
- Segurança
- Custos

### Principais Tecnologias

- SOAP
- REST
- XML
- JSON

## SOAP - "Simple Object Access Protocol"

- É um protocolo baseado em XML para acessar serviços web principalmente por HTTP.
- Pode-se dizer que SOAP é uma definição de como o serviços web se comunicam.
- Foi desenvolvido para facilitar integrações entre aplicações.
- Permite integrações entre aplicações, independente de linguagem, pois usa como linguagem comum o XML.
- É independente de plataforma e software.
- Meio de transporte genérico, ou seja, pode ser usado por outros protocolos além do HTTP.

#### XML - "Extensible Markup Language"

- É uma linguagem de marcação criada na década de 90 pela W3C
- Facilita a separação de conteúdo
- Não tem limitação de criação de tags
- Linguagem comum para integração entre aplicações

#### Estrutura SOAP

O "SOAP Message" possui uma estrutura única que deve sempre ser seguida.

<img src=".\Imagens\image-6.png" alt="image-6" style="max-width:75%;" />

- **SOAP Envelope** é o primeiro elemento do documento e é usado para encapsular toda a mensagem SOAP.
- **SOAP Header** é o elemento onde possui informações de atributos e metadados de requisição.
- **SOAP Body** é o elemento que contém os detalhes da mensagem.

<img src=".\Imagens\image-7.png" alt="image-7" style="max-width:75%;" />

#### WSDL - "Web Service Description Language"

- Usado para descrever Web Service, funciona como um contrato do serviço.
- A descrição é feito em um documento XML, onde é descrito o serviço, especificações de acesso, operações e métodos.

#### XSD - "XML Schema Definition"

- É um schema no formato XML usado para definir a estrutura de dados que será validada no XML.
- O XSD funciona como uma documentação de como deve ser montado o SOAP Message (XML) que será enviado através de Web Service.

#### Rest - "Representational State Transfer"

- É um estilo de arquitetura de software que define a implementação de serviço web
- Podem trabalhar com os formatos XML, JSON ou outros.

**Vantagens do REST**

- Permite integrações entre aplicações e também entre cliente e servidor em páginas web e aplicações.
- Utiliza dos métodos HTTP para definir a operação que está seno efetuada.
- Arquitetura de fácil compreensão.

<img src=".\Imagens\image-8.png" alt="image-8" style="max-width:75%;"/>

#### API - "Application Programming Interface"

- São conjuntos de rotinas documentados e disponibilizados por uma aplicação para que outras aplicações possam consumir suas funcionalidades.
- Ficou popular com o aumento dos serviços web.
- As maiores plataformas de tecnologia disponibilizam APIs para acessos de suas funcionalidades, algumas delas são: Facebook, Twitter, Telegram, Whatsapp, GitHub...

#### Principais Métodos HTTP

- **GET** - Solicita a representação de um recurso.
- **POST** - Solicita a criação de um recurso.
- **DELETE** - Solicita a exclusão de um recurso.
- **PUT** - Solicita a atualização de um recurso.

#### JSON - "JavaScript Object Notation"

- Formatação leve utilizada para troca de mensagens entre sistemas.
- Usa-se de uma estrutura de chave e valor e também de listas ordenadas.
- Um dos formatos mais populares e mais utilizados para troca de mensagens entre sistemas.

**Exemplo de arquivo JSON:**

```json
{
	"nome": "Os Vingadores",
    "ano_lancamento": "2019",
    "personagens":[
        {
            "nome": "Thanos"
        },
        {
            "nome": "Homem de Ferro"
        },
        {
            "nome": "Thor"
        }
    ]
}
```

#### Códigos de Estado HTTP

Usado pelo servidor para avisar o cliente sobre o estado da operação

- **1xx** - Informativo
- **2xx** - Sucesso
- **3xx** - Redirecionamento
- **4xx** - Erro do cliente
- **5xx** - Erro do Servidor

#### Referencia de Software e sites

https://www.soapui.org/ - **SoapUI** - É um aplicativo de teste de serviço da Web de código aberto para Simple Object Access Protocol e transferências de estado representacional.

https://soapclient.com/XML/soapresponder.wsdl - WebService público para testes.

https://www.postman.com/ - **Postman** - Aplicação para desenvolvimento de APIs.



## Conceitos de Arquitetura em Aplicações para internet

#### Tipos de Arquiteturas de sistemas

<img src=".\Imagens\image-9.png" alt="image-9" style="max-width:75%;"/>

<img src=".\Imagens\image-10.png" alt="image-10" style="max-width:75%;"/>

<img src=".\Imagens\image-11.png" alt="image-11" style="max-width:75%;"/>

<img src=".\Imagens\image-12.png" alt="image-12" style="max-width:75%;"/>

<img src=".\Imagens\image-13.png" alt="image-13" style="max-width:75%;"/>

<img src=".\Imagens\image-14.png" alt="image-14" style="max-width:75%;"/>

<img src=".\Imagens\image-15.png" alt="image-15" style="max-width:75%;"/>

<img src=".\Imagens\image-16.png" alt="image-16" style="max-width:75%;"/>

