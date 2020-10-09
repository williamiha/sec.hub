# Introdução

API de solução antifraude para análise de risco durante processos de vínculo e transações do PIX, retornando o nível de confiança, força do vínculo das variáveis informadas e insights. Nossos modelos e a abordagem de IA validam a verdadeira identidade digital do usuário final por meio da combinação de dados, análise de dispositivos e transações realizadas, prevenindo riscos de fraude em cada momento, seja ele no Onboarding ou Transação.



## Autenticação

Todas as requisições submetidas à nossa API devém ser realizadas através de um token gerado através de um usuário, senha e id da entidade que devem ser fornecidos pela ClearSale. Entre em contato com o seu consultor de vendas para mais informações.

Na autenticação, além do token retornamos seu tempo de expiração. É necessário que contemple no seu desenvolvimento o gerenciamento da vida útil do token com base nesse tempo de expiração. Só gere um novo token após a expiração do seu token atual.

##### Requisição:

```bash
POST v1/authentication HTTP/1.1
 
Content-Type: application/json
Accept:application/json 

{
  "Username:" "{Seu Usuário}",
  "Reason":"{Sua Senha}"
}
```

##### Resposta:

```
HTTP/1.1 200 OK
 
Content-Type: application/json
Accept:application/json
{
  "Token": "{Valor do Token}", 
  "ExpirationDate": "{Tempo de Expiração do Token}"
}
```



## Fingerprint

Para completa utilização da solução **sec.hub** é necessário que o Fingerprint esteja integrado no ato da captura dos dados.

Para maiores informações sobre as configurações do Fingerprint [**clique aqui**.](https://api.clearsale.com.br/docs/finger-print)



### SDK

Para completa utilização do Fingerprint é necessário que o SDK esteja integrado no ato da captura dos dados no aplicativo.

Para maiores informações sobre as configurações do SDK [**clique aqui**.](https://api.clearsale.com.br/docs/mobile-sdk/versions)



## Vínculo

A solução **sec.hub** mensura o nível de confiança durante a inclusão, portabilidade ou reivindicação de um registro na DICT.



#### Envio

Este método é utilizado para fazer o envio de uma transação para solução **sec.hub**



##### Requisição:

```python
POST v1/entries HTTP/1.1

Content-Type: application/json
Accept:application/json 

{
   "RequestType:" "0|1", //0 - Consulta, devolve análise e gera cobrança ou 1 - Retroalimentação,não gera cobrança e não retorna análise.
   "Reason":"USER_REQUESTED", //Enum: "USER_REQUESTED" "ACCOUNT_CLOSURE" "BRANCH_TRANSFER""ENTRY_INACTIVITY" "RECONCILIATION" Valores válidos: USER_REQUESTED e RECONCILIATION, campo especificado na API do DICT.
   "RequestId":"a946d533-7f22-42a5-9a9b-e87cd55c0f4d", // esse campo é um UUID versão 4 e deve ser único no contexto de um mesmo participante, é o mesmo campo enviado para transação na DICT pelo participante.
   "Name":"Bruno Botelho", //Person or organization name.
   "Document": "12345678912", (obrigatório)
   "DocumentType": "CPF" | "CNPJ", (obrigatório)
   "Phone": "+5511999991234", // opcional, telefone completo, incluindo código de país.
   "Verified Phone": false, // opcional - por padrão é falso, caso seja true o dado é verificado na sua base
   "Verified Email": false, // opcional - por padrão é falso, caso seja true o dado é verificado na sua base
   "Address": { // opcional
       "ZipCode": "00000000",
       "Street": "Rua teste",
       "Number": "12355",
       "Complement": "Esquina 3",
       "District": "B13",
       "City": "São Paulo",
       "State": "SP",
       "Country": "Brasil"
   },
   "Email": "joao.silva@email.com.br", // opcional
   "SessionID": "SessionID123", // opcional, gerado pelo SDK de defive fingerprint - Obrigatório se Type = 2
   "Reference Date" : "2019-06-05T12:00:00.000", // opcional
   "Account": { //Obrigatorio
       "Participant": "12345678", //Numero do Banco
       "Branch": "00001", //Agencia
       "AccountNumber":"0007654321", //Número da Conta
       "AccountType":"CACC" // Tipo de conta
    }
} 
```



##### Resposta:

```
HTTP/1.1 200 Ok
Content-Type: application/json; charset=utf-8
{
   "ID": "teste01",
   "Document": "12345678912",
   "DocumentType": "CPF",
   "Phone": "+5511665985875",
   "VerifiedPhone": false,
   "VerifiedEmail": false,
   "Address": {
       "ZipCode": "00000000",
       "Street": "Rua teste",
       "Number": "12355",
       "Complement": "Esquina 3",
       "District": "B13",
       "City": "São Paulo",
       "State": "SP",
       "Country": "Brasil"
   },
   "Email": "joao.silva@email.com.br",
   "SessionID": "SessionID123",
   "Type" : 1,
   "CreationDate": "2019-06-05T12:00:00.000",
   "Results": {
       "Score": {
            "Value": 90.99,
            "Reason": "Suspeita de fraude",
            "Date": "2019-06-07T12:45:00.000"
       },
       "Ratings": [
            {
                "Value": 3,
                "RelatedTo": [
                    "Document",
                    "Phone"
                ]
            },
            {
                "Value": 3,
                "RelatedTo": [
                    "Document",
                    "ZipCode"
                ]
            },
            {
                "Value": 2,
                "RelatedTo": [
                    "Document",
                    "Email"
                ]
            }
       ],
        "Insights": [
            {
               "Code": "TEL001",
               "Description": "O Celular informado foi visto nos últimos 3 meses.",
               "Type": "consulta",
               "Category": "fraude",
               "Relevance": "Positivo",
               "RelatedTo": [
                   "Document",
                   "Phone"
               ]
            },
           {
               "Code": "TEL002",
               "Description": "O endereço informado não pertence a pessoa.",
               "Type": "consulta",
               "Category": "fraude",
               "Relevance": "Neutro",
               "RelatedTo": [
                   "Document",
                   "ZipCode"
               ]
            },
           {
               "Code": "TEL002",
               "Description": "O device informado foi visto nos ultimos 3 meses.",
               "Type": "consulta",
               "Category": "fraude",
               "Relevance": "Alerta",
               "RelatedTo": [
                   "Device"
               ]
            }
       ]
   }
}   
```



## Transacional

A solução **sec.hub** avalia o nível de risco de uma transação PIX, sendo que esta requisição deve ser feita imediatamente antes de se incluir a transação no SPI, de modo que viabilize uma ação do participante



#### Envio

Este método é utilizado para fazer o envio de uma transação para solução **sec.hub**



##### Requisição:

```python
POST /v1/transfers/pix HTTP/1.1
 
Content-Type: application/json
Accept:application/json Authorization: Bearer {Token} {
 
{
   "RequestType:" "0", // Obrigatório: 
0 - Consulta, devolve análise e gera cobrança ou 
1 - Retroalimentação,não gera cobrança e não retorna análise.
   "TransactionType":"pacs.008",     // Obrigatório
Pacs.008: Tarnferencia de valores entre participantes no SPI.
Pacs.004: Devolução de valores no SPI.
   "EndToEndID": "E9999901012341234123412345678900", // Obrigatório, Unique identification assigned by the initiating party to unambiguously identify the transaction. This identification is passed on, unchanged, throughout the entire end-to-end chain.
       "Channel":"MOBILE",     // Obrigatório, canal utilizado pelo cliente para executar a transação. PODE SER: mobile, web, agencia.
   "ReferenceDate" : "2019-06-05T12:00:00.000", // obrugatório   
   "SenderDocument": "12345678912", / Obrigatório, numero do CPF ou CNPJ
   "SenderDocumentType": "CPF", / Obrigatório, valores aceitos (CNPJ ou CPF
   "SessionID": "SessionID123", // opcional, gerado pelo SDK de defive fingerprint
   "SenderAccount": { //Obrigatorio
       "Participant": "12345678", //Numero do Banco
       "Branch": "00001", //Agencia
       "AccountNumber":"0007654321", //Número da Conta
       "AccountType":"CACC" // Tipo de conta
    }
   "RecipientDocument": "12345678912", / Obrigatório, numero do CPF ou CNPJ
   "RecipientDocumentType": "CPF", // Obrigatório, valores aceitos (CNPJ ou CPF
   "RecipientAlias": "bruno.botelho.br@gmail.com", / Opcional, caso um alias tenha sido utilizado na transação para se obter a conta de destino, deve ser informado.
   "RecipientAliasType": "EMAIL", // Opcional, valores aceitos: CPF / CNPJ /EMAIL / PHONE /EVP
   "transactionQRCode": "....", // Opcional, caso um QRcode tenha sido utilizado na transação seu valor deve ser incluído para correlação.
   "Recipient-Account": { //Obrigatorio
       "Participant": "12345678", //Numero do Banco
       "Branch": "00001", //Agencia
       "AccountNumber":"0007654321", //Número da Conta
       "AccountType":"CACC" // Tipo de conta
    }
	   "Currency":"BRL", //Obrigatorio
       "Amount":"123.23", //Obrigatorio
```



##### Resposta:

```
HTTP/1.1 200 Ok
Content-Type: application/json; charset=utf-8
{
   "ID": "teste01",
   "TransactionType":"pacs.008",
   "EndToEndID": "E9999901012341234123412345678900", 
   "Channel":"MOBILE",
   "ReferenceDate" : "2019-06-05T12:00:00.000",   
   "SenderDocument": "12345678912", 
   "SenderDocumentType": "CPF", 
   "SessionID": "SessionID123",
   "SenderAccount": {
   "Participant": "12345678",
       "Branch": "00001", 
       "AccountNumber":"0007654321", 
       "AccountType":"CACC" 
    }
   "RecipientDocument": "12345678912",
   "RecipientDocumentType": "CPF", 
   "RecipientAlias": "bruno.botelho.br@gmail.com", 
   "RecipientAliasType": "EMAIL", 
   "transactionQRCode": "....", 
   "Recipient-Account": {
       "Participant": "12345678", 
       "Branch": "00001", 
       "AccountNumber":"0007654321", 
       "AccountType":"CACC" 
    }
"Currency":"BRL", 
"Amount":"123.23", 
}
,
   "Email": "joao.silva@email.com.br",
   "SessionID": "SessionID123",
   "Type" : 1,
   "CreationDate": "2019-06-05T12:00:00.000",
   "Results": {
       "Score": {
            "Value": 90.99,
            "Reason": "Suspeita de fraude",
            "Date": "2019-06-07T12:45:00.000"
       },
       "Ratings": [
            {
                "Value": 3,
                "RelatedTo": [
                    "Document",
                    "SessionID"
                ]
            },
            {
                "Value": 3,
                "RelatedTo": [
                    "Document",
                    "DestinationDocument"
                      ]
            },
            {
                "Value": 2,
                "RelatedTo": [
                    "Document",
                    "Channel"
                ]
            }
       ],
       "Insights": [
            {
               "Code": "TEL001",
               "Description": "O Celular informado foi visto nos últimos 3 meses.",
               "Type": "consulta",
               "Category": "fraude",
               "Relevance": "Positivo",
               "RelatedTo": [
                   "Document",
                   "Phone"
               ]
            },
           {
               "Code": "TEL002",
               "Description": "O endereço informado não pertence a pessoa.",
               "Type": "consulta",
               "Category": "fraude",
               "Relevance": "Neutro",
               "RelatedTo": [
                   "Document",
                   "ZipCode"
               ]
            },
           {
               "Code": "TEL002",
               "Description": "O device informado foi visto nos ultimos 3 meses.",
               "Type": "consulta",
               "Category": "fraude",
               "Relevance": "Alerta",
               "RelatedTo": [
                   "Device"
               ]
            }
              ]
   }
}
```



#### Lista de Insights

Os insights estão em constante evolução e para otimizar o processo serão devolvidos apenas os códigos dos insights para o participante. A seguir, uma descrição com os insights presentes no processo de análise de transações PIX:











## Retroalimentação

A Retroalimentação possibilita ao participante contribuir com informações  para enriquecer os dados de suas próprias análises futuras. De modo geral sempre que uma consulta for feita, seja de **vínculo** ou **transacional**, esta será incluída na base de dados e utilizada em correções futuras. No entanto, um participante pode optar por não fazer uma consulta de dados a fim de otimizar seus custos. Neste cenário, a retroalimentação irá apenas incluir os dados da requisição na base de dados para correlação futura. Este método difere de uma requisição normal por não retornar uma análise de risco e também não gera custo ao participante. 

Para enviar uma requisição de retroalimentação, é necessário preencher o campo "Request-Type" com a opção 1 tanto para o vínculo quanto no transacional.



#### Fraude

O participante pode também auxiliar na retroalimentação da base de dados para incluir ou atualizar uma marcação de fraude na plataforma.



##### Requisição:

```python
POST /v1/fraud HTTP/1.1
 
Content-Type: application/json
Accept:application/json Authorization: Bearer {Token} {
 
{
   "Participant": "12345678" // Obrigatório  
   "Summary": "Fraude de roubo de whatsapp", // Opcional, deve ser preenchido com uma Breve descrição da fraude, caso o participante ache pertinente.   
   "Description": "Fraude de roubo de whatsapp relatada pelo cliente em XX/YY/ZZZZ, nos ligou informando o modo de operação, o cliente recebeu uma mensagem...", // Opcional, deve ser preenchido com uma descrição detalhada da fraude, caso o participante ache pertinente.   
   "Visibility":"0",     // Obrigatório, 0 significa que somente você poderá ver esta fraude, 1 significa que outros participantes podem acessar a fraude e ver seus detalhes..
   "ReferenceDate" : "2019-06-05T12:00:00.000", // obrigatório   
   "LastupdateDate" : "2019-06-05T12:00:00.000", // calculado pela propria plataforma.
   "FraudStatus": "0",  // obrigatório, 
     0 - Suspeita de fraude: Trata-se de um indício de fraude e ainda não foi confirmada
     1 - Fraude Confirmada: (True Positive), é uma fraude confirmada e ainda está em andamento.
     2 - Suspeita descartada: (False Positive), a suspeita de fraude não foi confirmada, ao ser movida para esse status não será mais considerada em análises de risco de transações e vínculos.
3 - Fraude Arquivada : Foi uma fraude verdadeira mas foi contornada e seus objetos a refletiram como um histórico e não como uma fraude em andamento.
     "FraudRelations": {  // obrigatório, objetos relacionados na Fraude 
       "Relation": { // obrigatório, podem haver n relações em uma fraude
             "RelationType": "1"  // obrigatório, Tipo de relação na Fraude
              0 - Atacante, por exemplo um QRCode de um atacante utilizado na fraude de sobreposição de QRCode.
            1 - Alvo, por exemplo conta corrente ou CPF de um cliente que caiu em uma fraude.
            2 - N/A, por exemplo uma transação gerada por uma fraude, quando não há relação atacante / alvo em um objeto.
             "Objecttype": "email",  // obrigatório, Tipo de objeto, valores aceitos: CPF, CNPJ, Conta, Email, Phone, QRCode, IP, CEP, Nome, Device, QRCode, URL, EVP, Transaction
             "ObjectValue": "bruno.botelho.br@gmail.com",  / obrigatório, valor do obeto.
        }
     },
    "History" : "....", // gerado pela plataforma, seria uma string em csv que representa o histórico de modificações deste objeto, com data, variável alterada, valor antigo e valor novo.
}
```



##### Resposta:

```
HTTP/1.1 200 OK
 
Content-Type: application/json
Accept:application/json 
 
{
       "FraudID": "Identificado da fraude", 
}
```



# Dicionário de variáveis



#### Request

| Nome          | Descrição                                     | Tipo     | Tamanho | Obrigatório |
| ------------- | --------------------------------------------- | -------- | ------- | ----------- |
| Document      | Documento do cliente                          | String   | 11      | Sim         |
| DocumentType  | Tipo do documento do cliente                  | String   | -       | Sim         |
| Phone         | Número do celular do cliente                  | String   | 14      | Não         |
| VerifiedPhone | Flag de celular verificado                    | Boolean  | -       | Não         |
| VerifiedEmail | Flag de Email verificado                      | Boolean  | -       | Não         |
| Address       | Objeto com informações do endereço do cliente | Address  | -       | Não         |
| Email         | Email do cliente                              | String   | 320     | Não         |
| SessionID     | Chave do device do cliente                    | String   | -       | Não         |
| ReferenceDate | Data de referência da transação               | DateTime | -       | Não         |
| CreationDate  | Data de criação da transação                  | DateTime | -       | Não         |
| Results       | Objeto contendo os resultados da transação    | Results  | -       | Não         |

#### Address

| Nome             | Descrição                            | Tipo    | Tamanho | Obrigatório |
| ---------------- | ------------------------------------ | ------- | ------- | ----------- |
| ZipCode          | Código Postal do endereço do cliente | String  | 9       | Não         |
| Street           | Endereço do cliente                  | String  | -       | Não         |
| Number           | Número do endereço do cliente        | String  | -       | Não         |
| Complement       | Complemento do endereço do cliente   | String  | -       | Não         |
| District         | Distrito do endereço do cliente      | String  | -       | Não         |
| City             | Cidade do cliente                    | String  | -       | Não         |
| State            | Estado do cliente                    | String  | -       | Não         |
| Country          | País do cliente                      | String  | -       | Não         |
| PhysicalDelivery | Flag de entrega física do pedido     | Boolean | -       | Não         |

#### Result

| Nome     | Descrição                                       | Tipo                                                         |
| -------- | ----------------------------------------------- | ------------------------------------------------------------ |
| Score    | Objeto contendo informações do score do cliente | [Score](https://api.clearsale.com.br/docs/home/data-trust#score-dictionary) |
| Ratings  | Ratings da relação de dados enviados            | [Ratings](https://api.clearsale.com.br/docs/home/data-trust#ratings-dictionary) |
| Insights | Lista de objetos contendo os insights           | [Insights](https://api.clearsale.com.br/docs/home/data-trust#insights-dictionary) |

#### Score

| Nome   | Descrição                    | Tipo     |
| ------ | ---------------------------- | -------- |
| Value  | Valor do Score do cliente    | Decimal  |
| Reason | Motivo da alteração do Score | String   |
| Date   | Data da alteração do Score   | DateTime |

#### Ratings

| Nome      | Descrição                                    | Tipo   |
| --------- | -------------------------------------------- | ------ |
| Value     | Valor do rating da relação de dados enviados | Int    |
| RelatedTo | Dados referentes ao insight                  | String |

#### Insights

| Nome               | Descrição                                                    | Tipo                                          |
| ------------------ | ------------------------------------------------------------ | --------------------------------------------- |
| Code               | Código do insight                                            | String                                        |
| Description        | Descrição do insight                                         | String                                        |
| Type               | Tipo do insight (Consulta, retorno)                          | String                                        |
| Category           | Categoria do insight                                         | String                                        |
| Relevance          | Relevância do insight                                        | String                                        |
| RequestType        | 0 - Consulta, devolve análise e gera cobrança ou 1 - Retroalimentação,não gera cobrança e não retorna análise. | Boleano                                       |
| TransactionType    | Pacs.008: Transferência de valores entre participantes no SPI.Pacs.004: Devolução de valores no SPI. | String                                        |
| EndToEndID         | Unique identification assigned by the initiating party to unumbiguously identify the transaction. This identification is passed on, unchanged, throughout the entire end-to-end chain. | Data Type:  Max35Text, Format:  maxLength: 35 |
| Channel            | Obrigatório, canal utilizado pelo cliente para executar a transação. PODE SER: mobile, web, agencia. | String                                        |
| ReferenceDate      | Carimbo de tempo da transação (Quando realmente foi solicitado pelo usuário final) | Tiem Stamp                                    |
| SenderDocument     | Números (CPF ou CNPJ)                                        |                                               |
| SenderType         | CPF ou CNPJ                                                  | String                                        |
| Participant        | Numero do Banco                                              |                                               |
| Branch             | Numero da Agencia                                            |                                               |
| AccountNumber      | Numero da Conta                                              |                                               |
| AccountType        | Tipo de conta, exemplo CACC                                  |                                               |
| RecipientDocument  | Números (CPF ou CNPJ)                                        |                                               |
| RecipentType       | CPF ou CNPJ                                                  | String                                        |
| RecipientAlias     | Chave utilizada na consulta a conta no DIC para uma transferência. |                                               |
| RecipientAliasType | Tipo de chave utilizada na consulta a conta no DIC para uma transferência, valores: CPF / CNPJ /EMAIL / PHONE /EVP | String                                        |
| transactionQRCode  | Valor do QRCode utilizada na consulta a conta no DIC para uma transferência. | String                                        |
| Currency           | Moeda utilizada na transação, para Real (BRL)                | String                                        |
| Amount             | Valor da transação, com 2 casas decimais.                    | Float                                         |
| Summary            | Breve descrição (256 Chars)                                  | String                                        |
| Description        | Descrição detalhada (4096 Chars)                             | String                                        |
| LastUpdateDate     | Data de ultima atualização do Objeto                         | TimeStamp                                     |
| Visibility         | 0 significa que somente você poderá ver esta fraude, 1 significa que outros participantes podem acessar a fraude e ver seus detalhes, é int pois no futuro podem haver variações do grau de visibilidade. | Int                                           |
| RelationType       | 0 - Atacante, por exemplo um QRCode de um atacante utilizado na fraude de sobreposição de QRCode.1 - Alvo, por exemplo conta corrente ou CPF de um cliente que caiu em uma fraude.2 - N/A, por exemplo uma transação gerada por uma fraude, quando não há relação atacante / alvo em um objeto. | Int                                           |
| ObjectValue        | Valor do Objeto relacionado a uma fraude.                    | String                                        |
| ObjectType         | Tipo de objeto, valores aceitos: CPF, CNPJ, Conta, Email, Phone, QRCode, IP, CEP, Nome, Device, QRCode, URL, EVP, Transaction. | String                                        |
