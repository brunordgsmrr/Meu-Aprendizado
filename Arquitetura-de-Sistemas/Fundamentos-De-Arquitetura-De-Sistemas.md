# Fundamentos de Arquitetura de Sistemas

## Conceitos de Web Services

- São soluções para aplicações se comunicarem independente de linguagem, softwares e hardwares utilizados.
- Inicialmente era utilizado para troca de mensagens utilizando **XML (Extensible Markup Language)** sobre o protocolo HTTP sendo identificado por **URI (Uniform Resource Identifier)**.
- Podemos dizer que Serviços Web são API's que se comunicam por meio de rede sobre protocolo HTTP.

### Funcionamento do Web Service

<img src=".\.\Imagens\image-4.png" alt="image-4" width="50%" />

<img src=".\.\Imagens\image-5.png" alt="image-5" width="50%" />

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

<img src=".\.\Imagens\image-6.png" alt="image-6" width="50%" />

- **SOAP Envelope** é o primeiro elemento do documento e é usado para encapsular toda a mensagem SOAP.
- **SOAP Header** é o elemento onde possui informações de atributos e metadados de requisição.
- **SOAP Body** é o elemento que contém os detalhes da mensagem.

````xml
<soap:Envelope xmlns:soap="http://www.w3.org/2003/05/soap-envelope"
	<soap:Header>
	</soap:Header>
	<soap:Body>
        <m:MetodoEndereco xmlns:m="http://www.example.org/endereco">
            <m:Cidade>Rio de Janeiro</m:Cidade>
            <m:CEP>99999-999</m:CEP>
            <m:Longradouro>Avenida Atlântida</m:Longradouro>
            <m:Numero>99</m:Numero>
        </m:MetodoEndereco>
	</soap:Body>
</soap:Envelope>
````



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

<img src=".\.\Imagens\image-8.png" alt="image-8" width="50%"/>

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

<img src=".\.\Imagens\image-9.png" alt="image-9" width="50%"/>

<img src=".\.\Imagens\image-10.png" alt="image-10" width="50%"/>

<img src=".\.\Imagens\image-11.png" alt="image-11" width="50%"/>

<img src=".\.\Imagens\image-12.png" alt="image-12" width="50%"/>

<img src=".\.\Imagens\image-13.png" alt="image-13" width="50%"/>

<img src=".\.\Imagens\image-14.png" alt="image-14" width="50%"/>

<img src=".\.\Imagens\image-15.png" alt="image-15" width="50%"/>

<img src=".\.\Imagens\image-16.png" alt="image-16" width="50%"/>

<img src=".\.\Imagens\image-17.png" alt="image-17" width="50%"/>

## Conceitos de Internet das Coisas (IoT)

Internet das coisas é um conceito que se refere à interconexão digital de objetos cotidianos com a internet, conexão dos objetos mais do que das pessoas. Em outras palavras, a internet das coisas nada mais é que uma rede de objetos físicos capaz de reunir e de transmitir dados.

### Por que conectar as coisas?

- Embutir sensores em objetos do dia-a-dia.
- Coletar dados dos sensores.
- Usar o dado para tomar decisão.

<img src=".\.\Imagens\image-18.png" alt="image-16" width="50%"/>

#### Exemplos de utilização

- Smart building (Edifícios inteligentes)
- Smart Home (Casas inteligentes)
- Dispositivos vestiveis
- Agricultura
- Smart Transportation (Transporte inteligente)
- RFID Supply Chain (Corrente de suplemento) - Rastreio de objetos por meio de etiquetas RFID
- Energy Efficiency (Energia Eficiente)

#### Desafios da Internet das Coisas

1. Privacidade e Segurança
2. Quantidade exponencial de dispositivos conectados na rede
3. Ser capaz de processar e armazenar uma enorme quantidade de informações
4. Gerar valor a partir dos dados coletados

### Things

<img src=".\.\Imagens\image-33.png" alt="image-33" width="50%"/>

### Exemplos de plataformas para IoT

#### Arduino

- Plataforma de prototipagem
- Com Entradas/Saídas
- Desenvolvedor escreve em C/C++
- Interface serial ou USB
- Shields

<img src=".\.\Imagens\image-19.png" alt="image-19" width="50%"/>

**Código de exemplo para o Arduino**

````c
# include<WProgram.h>

void setup () {
    pinMode (LED_PIN, OUTPUT);	// habilita o pino 13 para saída digital (OUTPUT).
}

void loop () {
    digitalWrite (LED_PIN, HIGH);  // liga o LED.
    delay (1000);                  // espera 1 segundo (1000 milisegundos).
    digitalWrite (LED_PIN, LOW);   // desliga o LED.
    delay (1000);                  // espera 1 segundo.
}

int main(void)
{
    // define LED_PIN 13
    int LED_PIN = 13;
    
    init();
    
    setup();
    
    for (;;)
        loop();
    
    return 0;
}
````

#### MCUs - Microcontrolador de chip único

- sistema operacional real time
- Embarcado
- Uso industrial, médico, militar, transporte

<img src=".\.\Imagens\image-20.png" alt="image-20" width="50%"/>

#### Raspberry Pi - Microcomputador

- Computador completo
- Hardware integrado em uma única placa
- Roda SO Linux ou Windows
- Uso doméstico e comercial

<img src=".\.\Imagens\image-21.png" alt="image-21" width="50%"/>

### O protocolo de comunicação

#### MQTT

- Base na pilha do TCP/IP
- Protocolo de mensagem assíncrona (M2M)
- Criado pela IBM para conectar sensores de pipelines de petróleo a satélites
- Padrão OASIS suportado pelas linguagens de programação mais populares

<img src=".\.\Imagens\image-22.png" alt="image-22" width="50%"/>

**Modelo Cliente Servidor**

<img src=".\.\Imagens\image-23.png" alt="image-23" width="50%"/>

**Modelo Publish/Subscribe**

<img src=".\.\Imagens\image-24.png" alt="image-24" width="50%"/>

<img src=".\.\Imagens\image-25.png" alt="image-25" width="50%"/>

<img src=".\.\Imagens\image-26.png" alt="image-26" width="50%"/>

<img src=".\.\Imagens\image-27.png" alt="image-27" width="50%"/>

<img src=".\.\Imagens\image-28.png" alt="image-28" width="50%"/>

<img src=".\.\Imagens\image-29.png" alt="image-29" width="50%"/>

<img src=".\.\Imagens\image-30.png" alt="image-30" width="50%"/>

<img src=".\.\Imagens\image-31.png" alt="image-31" width="50%"/>

<img src=".\.\Imagens\image-32.png" alt="image-32" width="50%"/>

### Cloud

<img src=".\.\Imagens\image-34.png" alt="image-34" width="50%"/>

<img src=".\.\Imagens\image-35.png" alt="image-35" width="50%"/>

<img src=".\.\Imagens\image-36.png" alt="image-36" width="50%"/>

### Estudo de caso

<img src=".\.\Imagens\image-37.png" alt="image-37" width="50%"/>

<img src=".\.\Imagens\image-38.png" alt="image-38" width="50%"/>

<img src=".\.\Imagens\image-39.png" alt="image-39" width="50%"/>

<img src=".\.\Imagens\image-40.png" alt="image-40" width="50%"/>

<img src=".\.\Imagens\image-41.png" alt="image-41" width="50%"/>

<img src=".\.\Imagens\image-42.png" alt="image-42" width="50%"/>

<img src=".\.\Imagens\image-43.png" alt="image-43" width="50%"/>

