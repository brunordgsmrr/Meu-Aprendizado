# Fundamentos de Arquitetura de Sistemas

### O que são Web Services?
- São soluções para aplicações se comunicarem independente de linguagem, softwares e hardwares utilizados.
- Inicialmente era utilizado para troca de mensagens utilizando **XML (Extensible Markup Language)** sobre o protocolo HTTP sendo identificado por **URI (Uniform Resource Identifier)**.
- Podemos dizer que Serviços Web são API's que se comunicam por meio de rede sobre protocolo HTTP.

### Funcionamento do Web Service

![image-4.jpg](\Imagens\image-4.png)

![image-5.png](.\Imagens\image-5.png)

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

<img src=".\Imagens\image-6.png" alt="image-6" style="zoom:50%;" />

- **SOAP Envelope** é o primeiro elemento do documento e é usado para encapsular toda a mensagem SOAP.
- **SOAP Header** é o elemento onde possui informações de atributos e metadados de requisição.
- **SOAP Body** é o elemento que contém os detalhes da mensagem.

<img src=".\Imagens\image-7.png" alt="image-7" style="zoom:50%;" />
