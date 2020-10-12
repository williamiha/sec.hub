# Lista de Insights

Para todas consultas, há uma lista de possíveis insights que podem retornar para cada consulta realizada na solução **sec.hub**. Estes insights consistem em informações adicionais sobre as variáveis informadas pelo usuário, podendo ser alertas, idade dos dados, informações ou histórico positivo. Os insights podem ser sobre dados isolados ou uma combinação entre dois (ex: dupla CPF + Telefone).



#### Insights

| Código | Tipo                 | Dado      | Descrição                                                    | Status    |
| ------ | -------------------- | --------- | ------------------------------------------------------------ | --------- |
| 1      | ALERTAS              | TEL       | O Telefone teve alerta no mercado há menos  de 1 mês         | Ok        |
| 2      | ALERTAS              | TEL       | O Telefone teve alerta no mercado entre 1 e  3 meses         | Ok        |
| 3      | ALERTAS              | TEL       | O Telefone teve alerta no mercado entre 3 e  6 meses         | Ok        |
| 4      | ALERTAS              | TEL       | O Telefone teve alerta no mercado entre 6  meses e 1 ano     | Ok        |
| 5      | ALERTAS              | TEL       | O Telefone teve alerta no mercado entre 1 e  2 anos          | Ok        |
| 6      | ALERTAS              | TEL       | O Telefone teve alerta no mercado de 2 a 3  anos             | Ok        |
| 7      | ALERTAS              | TEL       | O Telefone teve alerta no mercado há mais  de 3 anos         | Ok        |
| 11     | ALERTAS              | CPF       | O CPF teve alerta no mercado há menos de 1  mês              | Ok        |
| 12     | ALERTAS              | CPF       | O CPF teve alerta no mercado entre 1 e 3  meses              | Ok        |
| 13     | ALERTAS              | CPF       | O CPF teve alerta no mercado entre 3 e 6  meses              | Ok        |
| 14     | ALERTAS              | CPF       | O CPF teve alerta no mercado entre 6 meses  e 1 ano          | Ok        |
| 15     | ALERTAS              | CPF       | O CPF teve alerta no mercado entre 1 e 2  anos               | Ok        |
| 16     | ALERTAS              | CPF       | O CPF teve alerta no mercado de 2 a 3 anos                   | Ok        |
| 17     | ALERTAS              | CPF       | O CPF teve alerta no mercado há mais de 3  anos              | Ok        |
| 21     | ALERTAS              | Email     | O Email teve alerta no mercado há menos de  1 mês            | Ok        |
| 22     | ALERTAS              | Email     | O Email teve alerta no mercado entre 1 e 3  meses            | Ok        |
| 23     | ALERTAS              | Email     | O Email teve alerta no mercado entre 3 e 6  meses            | Ok        |
| 24     | ALERTAS              | Email     | O Email teve alerta no mercado entre 6  meses e 1 ano        | Ok        |
| 25     | ALERTAS              | Email     | O Email teve alerta no mercado entre 1 e 2  anos             | Ok        |
| 26     | ALERTAS              | Email     | O Email teve alerta no mercado de 2 a 3  anos                | Ok        |
| 27     | ALERTAS              | Email     | O Email teve alerta no mercado há mais de 3  anos            | Ok        |
| 31     | ALERTAS              | FP        | O Dispositivo teve alerta no mercado há  menos de 1 mês      | Ok        |
| 32     | ALERTAS              | FP        | O Dispositivo teve alerta no mercado entre  1 e 3 meses      | Ok        |
| 33     | ALERTAS              | FP        | O Dispositivo teve alerta no mercado entre  3 e 6 meses      | Ok        |
| 34     | ALERTAS              | FP        | O Dispositivo teve alerta no mercado entre  6 meses e 1 ano  | Ok        |
| 35     | ALERTAS              | FP        | O Dispositivo teve alerta no mercado entre  1 e 2 anos       | Ok        |
| 36     | ALERTAS              | FP        | O Dispositivo teve alerta no mercado de 2 a  3 anos          | Ok        |
| 37     | ALERTAS              | FP        | O Dispositivo teve alerta no mercado há  mais de 3 anos      | Ok        |
| 130    | INFORMAÇÔES          | CPF+TEL   | Existem outros Telefones possíveis para a  pessoa            | Ok        |
| 230    | INFORMAÇÔES          | CPF+Email | Existem outros Emails possíveis para a  pessoa               | Ok        |
| 330    | INFORMAÇÔES          | CPF+CEP   | Existem outros CEPs possíveis para a pessoa                  | Ok        |
| 430    | INFORMAÇÔES          | CPF+FP    | Existem outros Dispositivos possíveis para  a pessoa         | Ok        |
| 2031   | IDADE DOS DADOS      | CPF       | O CPF informado nunca foi visto no BigData                   | Ok        |
| 2032   | IDADE DOS DADOS      | CPF       | O CPF informado foi visto pela primeira vez  há menos de 1 mês | Ok        |
| 2033   | IDADE DOS DADOS      | CPF       | O CPF informado foi visto pela primeira vez  entre 1 e 3 meses | Ok        |
| 2034   | IDADE DOS DADOS      | CPF       | O CPF informado foi visto pela primeira vez  entre 3 e 6 meses | Ok        |
| 2035   | IDADE DOS DADOS      | CPF       | O CPF informado foi visto pela primeira vez  entre 6 meses e 1 ano | Ok        |
| 2036   | IDADE DOS DADOS      | CPF       | O CPF informado foi visto pela primeira vez  entre 1 e 2 anos | Ok        |
| 2037   | IDADE DOS DADOS      | CPF       | O CPF informado foi visto pela primeira vez  de 2 a 3 anos   | Ok        |
| 2038   | IDADE DOS DADOS      | CPF       | O CPF informado foi visto pela primeira vez  há mais de 3 anos | Ok        |
| 2132   | IDADE DOS DADOS      | CPF       | O CPF informado foi visto pela última vez  há menos de 1 mês | Ok        |
| 2133   | IDADE DOS DADOS      | CPF       | O CPF informado foi visto pela última vez  entre 1 e 3 meses | Ok        |
| 2134   | IDADE DOS DADOS      | CPF       | O CPF informado foi visto pela última vez  entre 3 e 6 meses | Ok        |
| 2135   | IDADE DOS DADOS      | CPF       | O CPF informado foi visto pela última vez  entre 6 meses e 1 ano | Ok        |
| 2136   | IDADE DOS DADOS      | CPF       | O CPF informado foi visto pela última vez  entre 1 e 2 anos  | Ok        |
| 2137   | IDADE DOS DADOS      | CPF       | O CPF informado foi visto pela última vez  de 2 a 3 anos     | Ok        |
| 2138   | IDADE DOS DADOS      | CPF       | O CPF informado foi visto pela última vez  há mais de 3 anos | Ok        |
| 2011   | IDADE DOS DADOS      | TEL       | O Telefone informado nunca foi visto no  BigData             | Ok        |
| 2012   | IDADE DOS DADOS      | TEL       | O Telefone informado foi visto pela  primeira vez há menos de 1 mês | Ok        |
| 2013   | IDADE DOS DADOS      | TEL       | O Telefone informado foi visto pela  primeira vez entre 1 e 3 meses | Ok        |
| 2014   | IDADE DOS DADOS      | TEL       | O Telefone informado foi visto pela  primeira vez entre 3 e 6 meses | Ok        |
| 2015   | IDADE DOS DADOS      | TEL       | O Telefone informado foi visto pela  primeira vez entre 6 meses e 1 ano | Ok        |
| 2016   | IDADE DOS DADOS      | TEL       | O Telefone informado foi visto pela  primeira vez entre 1 e 2 anos | Ok        |
| 2017   | IDADE DOS DADOS      | TEL       | O Telefone informado foi visto pela  primeira vez de 2 a 3 anos | Ok        |
| 2018   | IDADE DOS DADOS      | TEL       | O Telefone informado foi visto pela  primeira vez há mais de 3 anos | Ok        |
| 2112   | IDADE DOS DADOS      | TEL       | O Telefone informado foi visto pela última  vez há menos de 1 mês | Ok        |
| 2113   | IDADE DOS DADOS      | TEL       | O Telefone informado foi visto pela última  vez entre 1 e 3 meses | Ok        |
| 2114   | IDADE DOS DADOS      | TEL       | O Telefone informado foi visto pela última  vez entre 3 e 6 meses | Ok        |
| 2115   | IDADE DOS DADOS      | TEL       | O Telefone informado foi visto pela última  vez entre 6 meses e 1 ano | Ok        |
| 2116   | IDADE DOS DADOS      | TEL       | O Telefone informado foi visto pela última  vez entre 1 e 2 anos | Ok        |
| 2117   | IDADE DOS DADOS      | TEL       | O Telefone informado foi visto pela última  vez de 2 a 3 anos | Ok        |
| 2118   | IDADE DOS DADOS      | TEL       | O Telefone informado foi visto pela última  vez há mais de 3 anos | Ok        |
| 2001   | IDADE DOS DADOS      | Email     | O Email informado nunca foi visto no  BigData                | Ok        |
| 2002   | IDADE DOS DADOS      | Email     | O Email informado foi visto pela primeira  vez há menos de 1 mês | Ok        |
| 2003   | IDADE DOS DADOS      | Email     | O Email informado foi visto pela primeira  vez entre 1 e 3 meses | Ok        |
| 2004   | IDADE DOS DADOS      | Email     | O Email informado foi visto pela primeira  vez entre 3 e 6 meses | Ok        |
| 2005   | IDADE DOS DADOS      | Email     | O Email informado foi visto pela primeira  vez entre 6 meses e 1 ano | Ok        |
| 2006   | IDADE DOS DADOS      | Email     | O Email informado foi visto pela primeira  vez entre 1 e 2 anos | Ok        |
| 2007   | IDADE DOS DADOS      | Email     | O Email informado foi visto pela primeira  vez de 2 a 3 anos | Ok        |
| 2008   | IDADE DOS DADOS      | Email     | O Email informado foi visto pela primeira  vez há mais de 3 anos | Ok        |
| 2102   | IDADE DOS DADOS      | Email     | O Email informado foi visto pela última vez  há menos de 1 mês | Ok        |
| 2103   | IDADE DOS DADOS      | Email     | O Email informado foi visto pela última vez  entre 1 e 3 meses | Ok        |
| 2104   | IDADE DOS DADOS      | Email     | O Email informado foi visto pela última vez  entre 3 e 6 meses | Ok        |
| 2105   | IDADE DOS DADOS      | Email     | O Email informado foi visto pela última vez  entre 6 meses e 1 ano | Ok        |
| 2106   | IDADE DOS DADOS      | Email     | O Email informado foi visto pela última vez  entre 1 e 2 anos | Ok        |
| 2107   | IDADE DOS DADOS      | Email     | O Email informado foi visto pela última vez  de 2 a 3 anos   | Ok        |
| 2108   | IDADE DOS DADOS      | Email     | O Email informado foi visto pela última vez  há mais de 3 anos | Ok        |
| 2021   | IDADE DOS DADOS      | FP        | O Dispositivo informado nunca foi visto no  BigData          | Ok        |
| 2022   | IDADE DOS DADOS      | FP        | O Dispositivo informado foi visto pela  primeira vez há menos de 1 mês | Ok        |
| 2023   | IDADE DOS DADOS      | FP        | O Dispositivo informado foi visto pela  primeira vez entre 1 e 3 meses | Ok        |
| 2024   | IDADE DOS DADOS      | FP        | O Dispositivo informado foi visto pela  primeira vez entre 3 e 6 meses | Ok        |
| 2025   | IDADE DOS DADOS      | FP        | O Dispositivo informado foi visto pela  primeira vez entre 6 meses e 1 ano | Ok        |
| 2026   | IDADE DOS DADOS      | FP        | O Dispositivo informado foi visto pela  primeira vez entre 1 e 2 anos | Ok        |
| 2027   | IDADE DOS DADOS      | FP        | O Dispositivo informado foi visto pela  primeira vez de 2 a 3 anos | Ok        |
| 2028   | IDADE DOS DADOS      | FP        | O Dispositivo informado foi visto pela  primeira vez há mais de 3 anos | Ok        |
| 2122   | IDADE DOS DADOS      | FP        | O Dispositivo informado foi visto pela  última vez há menos de 1 mês | Ok        |
| 2123   | IDADE DOS DADOS      | FP        | O Dispositivo informado foi visto pela  última vez entre 1 e 3 meses | Ok        |
| 2124   | IDADE DOS DADOS      | FP        | O Dispositivo informado foi visto pela  última vez entre 3 e 6 meses | Ok        |
| 2125   | IDADE DOS DADOS      | FP        | O Dispositivo informado foi visto pela  última vez entre 6 meses e 1 ano | Ok        |
| 2126   | IDADE DOS DADOS      | FP        | O Dispositivo informado foi visto pela  última vez entre 1 e 2 anos | Ok        |
| 2127   | IDADE DOS DADOS      | FP        | O Dispositivo informado foi visto pela  última vez de 2 a 3 anos | Ok        |
| 2128   | IDADE DOS DADOS      | FP        | O Dispositivo informado foi visto pela  última vez há mais de 3 anos | Ok        |
| 19     | INFORMAÇÔES          | CPF       | CPF é digital                                                | Ok        |
| 9      | INFORMAÇÔES          | TEL       | Telefone é digital                                           | Ok        |
| 29     | INFORMAÇÔES          | FP        | Disposititivo é digital                                      | Ok        |
| 39     | INFORMAÇÔES          | EMAIL     | E-mail é digital                                             | Ok        |
| 18     | ALERTAS              | CPF       | CPF já foi usado em muitas transações  fraudulentas          | Ok        |
| 8      | ALERTAS              | TEL       | Telefone já foi usado em muitas transações  fraudulentas     | Ok        |
| 28     | ALERTAS              | FP        | Dispositivo já foi usado em muitas  transações fraudulentas  |           |
| 38     | ALERTAS              | EMAIL     | Email já foi usado em muitas transações  fraudulentas        | Ok        |
| 101    | INSIGHTS PARA DUPLAS | CPF+TEL   | A dupla CPF + Telefone informada  nunca foi vista no BigData | Ok        |
| 102    | INSIGHTS PARA DUPLAS | CPF+TEL   | A dupla CPF + Telefone informada  foi vista pela primeira vez há menos de 1 mês | Ok        |
| 103    | INSIGHTS PARA DUPLAS | CPF+TEL   | A dupla CPF + Telefone informada  foi vista pela primeira vez entre 1 e 3 meses | Ok        |
| 104    | INSIGHTS PARA DUPLAS | CPF+TEL   | A dupla CPF + Telefone informada  foi vista pela primeira vez entre 3 e 6 meses | Ok        |
| 105    | INSIGHTS PARA DUPLAS | CPF+TEL   | A dupla CPF + Telefone informada  foi vista pela primeira vez entre 6 meses e 1 ano | Ok        |
| 106    | INSIGHTS PARA DUPLAS | CPF+TEL   | A dupla CPF + Telefone informada  foi vista pela primeira vez entre 1 e 2 anos | Ok        |
| 107    | INSIGHTS PARA DUPLAS | CPF+TEL   | A dupla CPF + Telefone informada  foi vista pela primeira vez de 2 a 3 anos | Ok        |
| 108    | INSIGHTS PARA DUPLAS | CPF+TEL   | A dupla CPF + Telefone informada  foi vista pela primeira vez há mais de 3 anos | Ok        |
| 109    | INSIGHTS PARA DUPLAS | CPF+TEL   | A dupla CPF + Telefone informada  foi vista pela última vez há menos de 1 mês | Ok        |
| 110    | INSIGHTS PARA DUPLAS | CPF+TEL   | A dupla CPF + Telefone informada  foi vista pela última vez entre 1 e 3 meses | Ok        |
| 111    | INSIGHTS PARA DUPLAS | CPF+TEL   | A dupla CPF + Telefone informada  foi vista pela última vez entre 3 e 6 meses | Ok        |
| 112    | INSIGHTS PARA DUPLAS | CPF+TEL   | A dupla CPF + Telefone informada  foi vista pela última vez entre 6 meses e 1 ano | Ok        |
| 113    | INSIGHTS PARA DUPLAS | CPF+TEL   | A dupla CPF + Telefone informada  foi vista pela última vez entre 1 e 2 anos | Ok        |
| 114    | INSIGHTS PARA DUPLAS | CPF+TEL   | A dupla CPF + Telefone informada  foi vista pela última vez de 2 a 3 anos | Ok        |
| 115    | INSIGHTS PARA DUPLAS | CPF+TEL   | A dupla CPF + Telefone informada  foi vista pela última vez há mais de 3 anos | Ok        |
| 116    | HIST. POSITIVO       | CPF+TEL   | Dupla CPF + Telefone com alta  frequência de utilização em transações positivas | Ok        |
| 117    | HIST. POSITIVO       | CPF+TEL   | Dupla CPF + Telefone vista em  diversos segmentos            | Ok        |
| 118    | INFORMAÇÔES          | CPF+TEL   | O Telefone já foi visto com outros CPF''s no último  ano     | Ok        |
| 119    | INFORMAÇÔES          | CPF+TEL   | O CPF já foi visto com outros  telefones no último ano       | Ok        |
| 201    | INSIGHTS PARA DUPLAS | CPF+Email | A dupla CPF + Email informada  nunca foi vista no BigData    | Ok        |
| 202    | INSIGHTS PARA DUPLAS | CPF+Email | A dupla CPF + Email informada  foi vista pela primeira vez há menos de 1 mês | Ok        |
| 203    | INSIGHTS PARA DUPLAS | CPF+Email | A dupla CPF + Email informada  foi vista pela primeira vez entre 1 e 3 meses | Ok        |
| 204    | INSIGHTS PARA DUPLAS | CPF+Email | A dupla CPF + Email informada  foi vista pela primeira vez entre 3 e 6 meses | Ok        |
| 205    | INSIGHTS PARA DUPLAS | CPF+Email | A dupla CPF + Email informada  foi vista pela primeira vez entre 6 meses e 1 ano | Ok        |
| 206    | INSIGHTS PARA DUPLAS | CPF+Email | A dupla CPF + Email informada  foi vista pela primeira vez entre 1 e 2 anos | Ok        |
| 207    | INSIGHTS PARA DUPLAS | CPF+Email | A dupla CPF + Email informada  foi vista pela primeira vez de 2 a 3 anos | Ok        |
| 208    | INSIGHTS PARA DUPLAS | CPF+Email | A dupla CPF + Email informada  foi vista pela primeira vez há mais de 3 anos | Ok        |
| 209    | INSIGHTS PARA DUPLAS | CPF+Email | A dupla CPF + Email informada  foi vista pela última vez há menos de 1 mês | Ok        |
| 210    | INSIGHTS PARA DUPLAS | CPF+Email | A dupla CPF + Email informada  foi vista pela última vez entre 1 e 3 meses | Ok        |
| 211    | INSIGHTS PARA DUPLAS | CPF+Email | A dupla CPF + Email informada  foi vista pela última vez entre 3 e 6 meses | Ok        |
| 212    | INSIGHTS PARA DUPLAS | CPF+Email | A dupla CPF + Email informada  foi vista pela última vez entre 6 meses e 1 ano | Ok        |
| 213    | INSIGHTS PARA DUPLAS | CPF+Email | A dupla CPF + Email informada  foi vista pela última vez entre 1 e 2 anos | Ok        |
| 214    | INSIGHTS PARA DUPLAS | CPF+Email | A dupla CPF + Email informada  foi vista pela última vez de 2 a 3 anos | Ok        |
| 215    | INSIGHTS PARA DUPLAS | CPF+Email | A dupla CPF + Email informada  foi vista pela última vez há mais de 3 anos | Ok        |
| 216    | HIST. POSITIVO       | CPF+Email | Dupla CPF + Email com alta  frequência de utilização em transações positivas | Ok        |
| 217    | HIST. POSITIVO       | CPF+Email | Dupla CPF + Email vista em  diversos segmentos               | Ok        |
| 218    | INFORMAÇÔES          | CPF+Email | O Email já foi visto com outros CPF''s no último  ano        | Ok        |
| 219    | INFORMAÇÔES          | CPF+Email | O CPF já foi visto com outros  Emails no último ano          | Ok        |
| 301    | INSIGHTS PARA DUPLAS | CPF+CEP   | A dupla CPF + CEP informada  nunca foi vista no BigData      | Ok        |
| 302    | INSIGHTS PARA DUPLAS | CPF+CEP   | A dupla CPF + CEP informada foi  vista pela primeira vez há menos de 1 mês | Ok        |
| 303    | INSIGHTS PARA DUPLAS | CPF+CEP   | A dupla CPF + CEP informada foi  vista pela primeira vez entre 1 e 3 meses | Ok        |
| 304    | INSIGHTS PARA DUPLAS | CPF+CEP   | A dupla CPF + CEP informada foi  vista pela primeira vez entre 3 e 6 meses | Ok        |
| 305    | INSIGHTS PARA DUPLAS | CPF+CEP   | A dupla CPF + CEP informada foi  vista pela primeira vez entre 6 meses e 1 ano | Ok        |
| 306    | INSIGHTS PARA DUPLAS | CPF+CEP   | A dupla CPF + CEP informada foi  vista pela primeira vez entre 1 e 2 anos | Ok        |
| 307    | INSIGHTS PARA DUPLAS | CPF+CEP   | A dupla CPF + CEP informada foi  vista pela primeira vez de 2 a 3 anos | Ok        |
| 308    | INSIGHTS PARA DUPLAS | CPF+CEP   | A dupla CPF + CEP informada foi  vista pela primeira vez há mais de 3 anos | Ok        |
| 309    | INSIGHTS PARA DUPLAS | CPF+CEP   | A dupla CPF + CEP informada foi  vista pela última vez há menos de 1 mês | Ok        |
| 310    | INSIGHTS PARA DUPLAS | CPF+CEP   | A dupla CPF + CEP informada foi  vista pela última vez entre 1 e 3 meses | Ok        |
| 311    | INSIGHTS PARA DUPLAS | CPF+CEP   | A dupla CPF + CEP informada foi  vista pela última vez entre 3 e 6 meses | Ok        |
| 312    | INSIGHTS PARA DUPLAS | CPF+CEP   | A dupla CPF + CEP informada foi  vista pela última vez entre 6 meses e 1 ano | Ok        |
| 313    | INSIGHTS PARA DUPLAS | CPF+CEP   | A dupla CPF + CEP informada foi  vista pela última vez entre 1 e 2 anos | Ok        |
| 314    | INSIGHTS PARA DUPLAS | CPF+CEP   | A dupla CPF + CEP informada foi  vista pela última vez de 2 a 3 anos | Ok        |
| 315    | INSIGHTS PARA DUPLAS | CPF+CEP   | A dupla CPF + CEP informada foi  vista pela última vez há mais de 3 anos | Ok        |
| 316    | HIST. POSITIVO       | CPF+CEP   | Dupla CPF + CEP com alta  frequência de utilização em transações positivas | Ok        |
| 317    | HIST. POSITIVO       | CPF+CEP   | Dupla CPF + CEP vista em  diversos segmentos                 | Ok        |
| 319    | INFORMAÇÔES          | CPF+CEP   | O CPF já foi visto com outros  CEPs no último ano            | Ok        |
| 401    | INSIGHTS PARA DUPLAS | CPF+FP    | A dupla CPF + Dispositivo  informada nunca foi vista no BigData | Ok        |
| 402    | INSIGHTS PARA DUPLAS | CPF+FP    | A dupla CPF + Dispositivo  informada foi vista pela primeira vez há menos de 1 mês | Ok        |
| 403    | INSIGHTS PARA DUPLAS | CPF+FP    | A dupla CPF + Dispositivo  informada foi vista pela primeira vez entre 1 e 3 meses | Ok        |
| 404    | INSIGHTS PARA DUPLAS | CPF+FP    | A dupla CPF + Dispositivo  informada foi vista pela primeira vez entre 3 e 6 meses | Ok        |
| 405    | INSIGHTS PARA DUPLAS | CPF+FP    | A dupla CPF + Dispositivo  informada foi vista pela primeira vez entre 6 meses e 1 ano | Ok        |
| 406    | INSIGHTS PARA DUPLAS | CPF+FP    | A dupla CPF + Dispositivo  informada foi vista pela primeira vez entre 1 e 2 anos | Ok        |
| 407    | INSIGHTS PARA DUPLAS | CPF+FP    | A dupla CPF + Dispositivo  informada foi vista pela primeira vez de 2 a 3 anos | Ok        |
| 408    | INSIGHTS PARA DUPLAS | CPF+FP    | A dupla CPF + Dispositivo  informada foi vista pela primeira vez há mais de 3 anos | Ok        |
| 409    | INSIGHTS PARA DUPLAS | CPF+FP    | A dupla CPF + Dispositivo  informada foi vista pela última vez há menos de 1 mês | Ok        |
| 410    | INSIGHTS PARA DUPLAS | CPF+FP    | A dupla CPF + Dispositivo  informada foi vista pela última vez entre 1 e 3 meses | Ok        |
| 411    | INSIGHTS PARA DUPLAS | CPF+FP    | A dupla CPF + Dispositivo  informada foi vista pela última vez entre 3 e 6 meses | Ok        |
| 412    | INSIGHTS PARA DUPLAS | CPF+FP    | A dupla CPF + Dispositivo  informada foi vista pela última vez entre 6 meses e 1 ano | Ok        |
| 413    | INSIGHTS PARA DUPLAS | CPF+FP    | A dupla CPF + Dispositivo  informada foi vista pela última vez entre 1 e 2 anos | Ok        |
| 414    | INSIGHTS PARA DUPLAS | CPF+FP    | A dupla CPF + Dispositivo  informada foi vista pela última vez de 2 a 3 anos | Ok        |
| 415    | INSIGHTS PARA DUPLAS | CPF+FP    | A dupla CPF + Dispositivo  informada foi vista pela última vez há mais de 3 anos | Ok        |
| 416    | HIST. POSITIVO       | CPF+FP    | Dupla CPF + Dispositivo com alta  frequência de utilização em transações positivas | Ok        |
| 417    | HIST. POSITIVO       | CPF+FP    | Dupla CPF + Dispositivo vista em  diversos segmentos         | Ok        |
| 418    | INFORMAÇÔES          | CPF+FP    | O Dispositivo já foi visto com outros CPF''s no último  ano  | Ok        |
| 419    | INFORMAÇÔES          | CPF+FP    | O CPF já foi visto com outros  dispositivos no último ano    | Em estudo |
| 501    | INSIGHTS PARA DUPLAS | CEP+FP    | A dupla CEP + Dispositivo  informada nunca foi vista no BigData | Ok        |
| 502    | INSIGHTS PARA DUPLAS | CEP+FP    | A dupla CEP + Dispositivo  informada foi vista pela primeira vez há menos de 1 mês | Ok        |
| 503    | INSIGHTS PARA DUPLAS | CEP+FP    | A dupla CEP + Dispositivo  informada foi vista pela primeira vez entre 1 e 3 meses | Ok        |
| 504    | INSIGHTS PARA DUPLAS | CEP+FP    | A dupla CEP + Dispositivo  informada foi vista pela primeira vez entre 3 e 6 meses | Ok        |
| 505    | INSIGHTS PARA DUPLAS | CEP+FP    | A dupla CEP + Dispositivo  informada foi vista pela primeira vez entre 6 meses e 1 ano | Ok        |
| 506    | INSIGHTS PARA DUPLAS | CEP+FP    | A dupla CEP + Dispositivo  informada foi vista pela primeira vez entre 1 e 2 anos | Ok        |
| 507    | INSIGHTS PARA DUPLAS | CEP+FP    | A dupla CEP + Dispositivo  informada foi vista pela primeira vez de 2 a 3 anos | Ok        |
| 508    | INSIGHTS PARA DUPLAS | CEP+FP    | A dupla CEP + Dispositivo  informada foi vista pela primeira vez há mais de 3 anos | Ok        |
| 509    | INSIGHTS PARA DUPLAS | CEP+FP    | A dupla CEP + Dispositivo  informada foi vista pela última vez há menos de 1 mês | Ok        |
| 510    | INSIGHTS PARA DUPLAS | CEP+FP    | A dupla CEP + Dispositivo  informada foi vista pela última vez entre 1 e 3 meses | Ok        |
| 511    | INSIGHTS PARA DUPLAS | CEP+FP    | A dupla CEP + Dispositivo  informada foi vista pela última vez entre 3 e 6 meses | Ok        |
| 512    | INSIGHTS PARA DUPLAS | CEP+FP    | A dupla CEP + Dispositivo  informada foi vista pela última vez entre 6 meses e 1 ano | Ok        |
| 513    | INSIGHTS PARA DUPLAS | CEP+FP    | A dupla CEP + Dispositivo  informada foi vista pela última vez entre 1 e 2 anos | Ok        |
| 514    | INSIGHTS PARA DUPLAS | CEP+FP    | A dupla CEP + Dispositivo  informada foi vista pela última vez de 2 a 3 anos | Ok        |
| 515    | INSIGHTS PARA DUPLAS | CEP+FP    | A dupla CEP + Dispositivo  informada foi vista pela última vez há mais de 3 anos | Ok        |
| 516    | HIST. POSITIVO       | CEP+FP    | Dupla CEP + Dispositivo com alta  frequência de utilização em transações positivas | Ok        |
| 517    | HIST. POSITIVO       | CEP+FP    | Dupla CEP + Dispositivo vista em  diversos segmentos         | Ok        |
| 601    | INSIGHTS PARA DUPLAS | EMAIL+CEP | A dupla Email + CEP informada  nunca foi vista no BigData    | Ok        |
| 602    | INSIGHTS PARA DUPLAS | EMAIL+CEP | A dupla Email + CEP informada  foi vista pela primeira vez há menos de 1 mês | Ok        |
| 603    | INSIGHTS PARA DUPLAS | EMAIL+CEP | A dupla Email + CEP informada  foi vista pela primeira vez entre 1 e 3 meses | Ok        |
| 604    | INSIGHTS PARA DUPLAS | EMAIL+CEP | A dupla Email + CEP informada  foi vista pela primeira vez entre 3 e 6 meses | Ok        |
| 605    | INSIGHTS PARA DUPLAS | EMAIL+CEP | A dupla Email + CEP informada  foi vista pela primeira vez entre 6 meses e 1 ano | Ok        |
| 606    | INSIGHTS PARA DUPLAS | EMAIL+CEP | A dupla Email + CEP informada  foi vista pela primeira vez entre 1 e 2 anos | Ok        |
| 607    | INSIGHTS PARA DUPLAS | EMAIL+CEP | A dupla Email + CEP informada  foi vista pela primeira vez de 2 a 3 anos | Ok        |
| 608    | INSIGHTS PARA DUPLAS | EMAIL+CEP | A dupla Email + CEP informada  foi vista pela primeira vez há mais de 3 anos | Ok        |
| 609    | INSIGHTS PARA DUPLAS | EMAIL+CEP | A dupla Email + CEP informada  foi vista pela última vez há menos de 1 mês | Ok        |
| 610    | INSIGHTS PARA DUPLAS | EMAIL+CEP | A dupla Email + CEP informada  foi vista pela última vez entre 1 e 3 meses | Ok        |
| 611    | INSIGHTS PARA DUPLAS | EMAIL+CEP | A dupla Email + CEP informada  foi vista pela última vez entre 3 e 6 meses | Ok        |
| 612    | INSIGHTS PARA DUPLAS | EMAIL+CEP | A dupla Email + CEP informada  foi vista pela última vez entre 6 meses e 1 ano | Ok        |
| 613    | INSIGHTS PARA DUPLAS | EMAIL+CEP | A dupla Email + CEP informada  foi vista pela última vez entre 1 e 2 anos | Ok        |
| 614    | INSIGHTS PARA DUPLAS | EMAIL+CEP | A dupla Email + CEP informada  foi vista pela última vez de 2 a 3 anos | Ok        |
| 615    | INSIGHTS PARA DUPLAS | EMAIL+CEP | A dupla Email + CEP informada  foi vista pela última vez há mais de 3 anos | Ok        |
| 616    | HIST. POSITIVO       | EMAIL+CEP | Dupla Email + CEP com alta  frequência de utilização em transações positivas | Ok        |
| 617    | HIST. POSITIVO       | EMAIL+CEP | Dupla Email + CEP vista em  diversos segmentos               | Ok        |
| 701    | INSIGHTS PARA DUPLAS | EMAIL+FP  | A dupla Email + Dispositivo  informada nunca foi vista no BigData | Ok        |
| 702    | INSIGHTS PARA DUPLAS | EMAIL+FP  | A dupla Email + Dispositivo  informada foi vista pela primeira vez há menos de 1 mês | Ok        |
| 703    | INSIGHTS PARA DUPLAS | EMAIL+FP  | A dupla Email + Dispositivo  informada foi vista pela primeira vez entre 1 e 3 meses | Ok        |
| 704    | INSIGHTS PARA DUPLAS | EMAIL+FP  | A dupla Email + Dispositivo  informada foi vista pela primeira vez entre 3 e 6 meses | Ok        |
| 705    | INSIGHTS PARA DUPLAS | EMAIL+FP  | A dupla Email + Dispositivo  informada foi vista pela primeira vez entre 6 meses e 1 ano | Ok        |
| 706    | INSIGHTS PARA DUPLAS | EMAIL+FP  | A dupla Email + Dispositivo  informada foi vista pela primeira vez entre 1 e 2 anos | Ok        |
| 707    | INSIGHTS PARA DUPLAS | EMAIL+FP  | A dupla Email + Dispositivo  informada foi vista pela primeira vez de 2 a 3 anos | Ok        |
| 708    | INSIGHTS PARA DUPLAS | EMAIL+FP  | A dupla Email + Dispositivo  informada foi vista pela primeira vez há mais de 3 anos | Ok        |
| 709    | INSIGHTS PARA DUPLAS | EMAIL+FP  | A dupla Email + Dispositivo  informada foi vista pela última vez há menos de 1 mês | Ok        |
| 710    | INSIGHTS PARA DUPLAS | EMAIL+FP  | A dupla Email + Dispositivo  informada foi vista pela última vez entre 1 e 3 meses | Ok        |
| 711    | INSIGHTS PARA DUPLAS | EMAIL+FP  | A dupla Email + Dispositivo  informada foi vista pela última vez entre 3 e 6 meses | Ok        |
| 712    | INSIGHTS PARA DUPLAS | EMAIL+FP  | A dupla Email + Dispositivo  informada foi vista pela última vez entre 6 meses e 1 ano | Ok        |
| 713    | INSIGHTS PARA DUPLAS | EMAIL+FP  | A dupla Email + Dispositivo  informada foi vista pela última vez entre 1 e 2 anos | Ok        |
| 714    | INSIGHTS PARA DUPLAS | EMAIL+FP  | A dupla Email + Dispositivo  informada foi vista pela última vez de 2 a 3 anos | Ok        |
| 715    | INSIGHTS PARA DUPLAS | EMAIL+FP  | A dupla Email + Dispositivo  informada foi vista pela última vez há mais de 3 anos | Ok        |
| 716    | HIST. POSITIVO       | EMAIL+FP  | Dupla Email + Dispositivo com  alta frequência de utilização em transações positivas | Ok        |
| 717    | HIST. POSITIVO       | EMAIL+FP  | Dupla Email + Dispositivo vista  em diversos segmentos       | Ok        |
| 801    | INSIGHTS PARA DUPLAS | EMAIL+TEL | A dupla Email + Telefone  informada nunca foi vista no BigData | Ok        |
| 802    | INSIGHTS PARA DUPLAS | EMAIL+TEL | A dupla Email + Telefone  informada foi vista pela primeira vez há menos de 1 mês | Ok        |
| 803    | INSIGHTS PARA DUPLAS | EMAIL+TEL | A dupla Email + Telefone  informada foi vista pela primeira vez entre 1 e 3 meses | Ok        |
| 804    | INSIGHTS PARA DUPLAS | EMAIL+TEL | A dupla Email + Telefone  informada foi vista pela primeira vez entre 3 e 6 meses | Ok        |
| 805    | INSIGHTS PARA DUPLAS | EMAIL+TEL | A dupla Email + Telefone  informada foi vista pela primeira vez entre 6 meses e 1 ano | Ok        |
| 806    | INSIGHTS PARA DUPLAS | EMAIL+TEL | A dupla Email + Telefone  informada foi vista pela primeira vez entre 1 e 2 anos | Ok        |
| 807    | INSIGHTS PARA DUPLAS | EMAIL+TEL | A dupla Email + Telefone  informada foi vista pela primeira vez de 2 a 3 anos | Ok        |
| 808    | INSIGHTS PARA DUPLAS | EMAIL+TEL | A dupla Email + Telefone  informada foi vista pela primeira vez há mais de 3 anos | Ok        |
| 809    | INSIGHTS PARA DUPLAS | EMAIL+TEL | A dupla Email + Telefone  informada foi vista pela última vez há menos de 1 mês | Ok        |
| 810    | INSIGHTS PARA DUPLAS | EMAIL+TEL | A dupla Email + Telefone  informada foi vista pela última vez entre 1 e 3 meses | Ok        |
| 811    | INSIGHTS PARA DUPLAS | EMAIL+TEL | A dupla Email + Telefone  informada foi vista pela última vez entre 3 e 6 meses | Ok        |
| 812    | INSIGHTS PARA DUPLAS | EMAIL+TEL | A dupla Email + Telefone  informada foi vista pela última vez entre 6 meses e 1 ano | Ok        |
| 813    | INSIGHTS PARA DUPLAS | EMAIL+TEL | A dupla Email + Telefone  informada foi vista pela última vez entre 1 e 2 anos | Ok        |
| 814    | INSIGHTS PARA DUPLAS | EMAIL+TEL | A dupla Email + Telefone  informada foi vista pela última vez de 2 a 3 anos | Ok        |
| 815    | INSIGHTS PARA DUPLAS | EMAIL+TEL | A dupla Email + Telefone  informada foi vista pela última vez há mais de 3 anos | Ok        |
| 816    | HIST. POSITIVO       | EMAIL+TEL | Dupla Email + Telefone com alta  frequência de utilização em transações positivas | Ok        |
| 817    | HIST. POSITIVO       | EMAIL+TEL | Dupla Email + Telefone vista em  diversos segmentos          | Ok        |
| 901    | INSIGHTS PARA DUPLAS | TEL+CEP   | A dupla Telefone + CEP informada  nunca foi vista no BigData | Ok        |
| 902    | INSIGHTS PARA DUPLAS | TEL+CEP   | A dupla Telefone + CEP informada  foi vista pela primeira vez há menos de 1 mês | Ok        |
| 903    | INSIGHTS PARA DUPLAS | TEL+CEP   | A dupla Telefone + CEP informada  foi vista pela primeira vez entre 1 e 3 meses | Ok        |
| 904    | INSIGHTS PARA DUPLAS | TEL+CEP   | A dupla Telefone + CEP informada  foi vista pela primeira vez entre 3 e 6 meses | Ok        |
| 905    | INSIGHTS PARA DUPLAS | TEL+CEP   | A dupla Telefone + CEP informada  foi vista pela primeira vez entre 6 meses e 1 ano | Ok        |
| 906    | INSIGHTS PARA DUPLAS | TEL+CEP   | A dupla Telefone + CEP informada  foi vista pela primeira vez entre 1 e 2 anos | Ok        |
| 907    | INSIGHTS PARA DUPLAS | TEL+CEP   | A dupla Telefone + CEP informada  foi vista pela primeira vez de 2 a 3 anos | Ok        |
| 908    | INSIGHTS PARA DUPLAS | TEL+CEP   | A dupla Telefone + CEP informada  foi vista pela primeira vez há mais de 3 anos | Ok        |
| 909    | INSIGHTS PARA DUPLAS | TEL+CEP   | A dupla Telefone + CEP informada  foi vista pela última vez há menos de 1 mês | Ok        |
| 910    | INSIGHTS PARA DUPLAS | TEL+CEP   | A dupla Telefone + CEP informada  foi vista pela última vez entre 1 e 3 meses | Ok        |
| 911    | INSIGHTS PARA DUPLAS | TEL+CEP   | A dupla Telefone + CEP informada  foi vista pela última vez entre 3 e 6 meses | Ok        |
| 912    | INSIGHTS PARA DUPLAS | TEL+CEP   | A dupla Telefone + CEP informada  foi vista pela última vez entre 6 meses e 1 ano | Ok        |
| 913    | INSIGHTS PARA DUPLAS | TEL+CEP   | A dupla Telefone + CEP informada  foi vista pela última vez entre 1 e 2 anos | Ok        |
| 914    | INSIGHTS PARA DUPLAS | TEL+CEP   | A dupla Telefone + CEP informada  foi vista pela última vez de 2 a 3 anos | Ok        |
| 915    | INSIGHTS PARA DUPLAS | TEL+CEP   | A dupla Telefone + CEP informada  foi vista pela última vez há mais de 3 anos | Ok        |
| 916    | HIST. POSITIVO       | TEL+CEP   | Dupla Telefone + CEP com alta  frequência de utilização em transações positivas | Ok        |
| 917    | HIST. POSITIVO       | TEL+CEP   | Dupla Telefone + CEP vista em  diversos segmentos            | Ok        |
| 1001   | INSIGHTS PARA DUPLAS | TEL+FP    | A dupla Telefone + Dispositivo  informada nunca foi vista no BigData | Ok        |
| 1002   | INSIGHTS PARA DUPLAS | TEL+FP    | A dupla Telefone + Dispositivo  informada foi vista pela primeira vez há menos de 1 mês | Ok        |
| 1003   | INSIGHTS PARA DUPLAS | TEL+FP    | A dupla Telefone + Dispositivo  informada foi vista pela primeira vez entre 1 e 3 meses | Ok        |
| 1004   | INSIGHTS PARA DUPLAS | TEL+FP    | A dupla Telefone + Dispositivo  informada foi vista pela primeira vez entre 3 e 6 meses | Ok        |
| 1005   | INSIGHTS PARA DUPLAS | TEL+FP    | A dupla Telefone + Dispositivo  informada foi vista pela primeira vez entre 6 meses e 1 ano | Ok        |
| 1006   | INSIGHTS PARA DUPLAS | TEL+FP    | A dupla Telefone + Dispositivo  informada foi vista pela primeira vez entre 1 e 2 anos | Ok        |
| 1007   | INSIGHTS PARA DUPLAS | TEL+FP    | A dupla Telefone + Dispositivo  informada foi vista pela primeira vez de 2 a 3 anos | Ok        |
| 1008   | INSIGHTS PARA DUPLAS | TEL+FP    | A dupla Telefone + Dispositivo  informada foi vista pela primeira vez há mais de 3 anos | Ok        |
| 1009   | INSIGHTS PARA DUPLAS | TEL+FP    | A dupla Telefone + Dispositivo  informada foi vista pela última vez há menos de 1 mês | Ok        |
| 1010   | INSIGHTS PARA DUPLAS | TEL+FP    | A dupla Telefone + Dispositivo  informada foi vista pela última vez entre 1 e 3 meses | Ok        |
| 1011   | INSIGHTS PARA DUPLAS | TEL+FP    | A dupla Telefone + Dispositivo  informada foi vista pela última vez entre 3 e 6 meses | Ok        |
| 1012   | INSIGHTS PARA DUPLAS | TEL+FP    | A dupla Telefone + Dispositivo  informada foi vista pela última vez entre 6 meses e 1 ano | Ok        |
| 1013   | INSIGHTS PARA DUPLAS | TEL+FP    | A dupla Telefone + Dispositivo  informada foi vista pela última vez entre 1 e 2 anos | Ok        |
| 1014   | INSIGHTS PARA DUPLAS | TEL+FP    | A dupla Telefone + Dispositivo  informada foi vista pela última vez de 2 a 3 anos | Ok        |
| 1015   | INSIGHTS PARA DUPLAS | TEL+FP    | A dupla Telefone + Dispositivo  informada foi vista pela última vez há mais de 3 anos | Ok        |
| 1016   | HIST. POSITIVO       | TEL+FP    | Dupla Telefone + Dispositivo com  alta frequência de utilização em transações positivas | Ok        |
| 1017   | HIST. POSITIVO       | TEL+FP    | Dupla Telefone + Dispositivo  vista em diversos segmentos    | Ok        |



#### 
