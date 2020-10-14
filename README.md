# Introdução

A solução sec.hub é uma plataforma construída em uma parceria entre a CIP e a Clearsale, empresas com vasta experiência em tecnologia e prevenção à fraude.

A plataforma foi elaborada para ser utilizada pelo ecossistema de pagamentos instantâneos brasileiro como um todo, utilizando um conceito de base compartilhada. Quanto mais participantes estiverem integrados à solução, mais seguro será o sistema. Ao mesmo tempo, permite autonomia e controle total dos participantes terem sua própria gestão de risco, recebendo os melhores insumos para tomada de decisão.

## Autenticação

Todas as requisições submetidas à nossa API devém ser realizadas através de um token gerado através de um usuário, senha e id da entidade que devem ser fornecidos pela ClearSale. Entre em contato com o seu consultor de vendas para mais informações.

Na autenticação, além do token retornamos seu tempo de expiração. É necessário que contemple no seu desenvolvimento o gerenciamento da vida útil do token com base nesse tempo de expiração. Só gere um novo token após a expiração do seu token atual.

## Componentes da solução

A solução **sec.hub** recebe como input um conjunto de dados e o dispositivo, capturado por meio do Fingerprint ClearSale, realiza a análise ba base de dados da ClearSale e retorna em tempo real:

    - Nível de risco: varia de 1 a 99% e se refere à propensão do pedido em questão ser uma tentativa de fraude (contexto análise de vínculo na DICT e Transação Pix).
    - Força de vínculo: classificação sobre a força do vínculo de todas as duplas de dados recebidos, podendo ser 1-Baixo, 2-Médio ou 3-Alto (ex: CPF com celular, celular com dispositivo, etc);
    - Insights: informações adicionais sobre os dados informados, como por exemplo alertas sobre os dados recebidos (CPF, celular, Email e device).

O acesso a solução é feito através de API REST, usando padrões de mercado seguros, além de integração de SDK para captura da identificação do dispositivo.

Nos fluxos de validação de vínculo ao DICT e transação no PIX, o participante deve incorporar os retornos das chamadas de API às suas próprias regras internas de validação. Com isso terá todos os insumos e informações mais recentes para tomada de decisão, podendo tomar ações diferentes para níveis de riscos baixo, médio e alto.


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
| Score    | Objeto contendo informações do score do cliente | Score |
| Ratings  | Ratings da relação de dados enviados            | Ratings |
| Insights | Lista de objetos contendo os insights           | Insights |

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
