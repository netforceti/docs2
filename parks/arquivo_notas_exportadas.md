# Leiaute do arquivo das notas exportadas

Abaixo é exibido a descrição e definição do arquivo exportado das notas fiscais (RPS) do sistema de parques.

O arquivo é exportado em formado TXT onde cada linha terá um identificador, seguido com os demais campos separados por pipe ( | ).

Abaixo mostro a ordem e definição dos campos:

### Tabela - Linha Cabeçalho do Arquivo (G001)

| Número | Campo            | Descrição                                                | Tipo | Tamanho |
|:------:|------------------|----------------------------------------------------------|:----:|:-------:|
|   01   |  ID_REG          |  Identificação do registro. Texto "G001"                 |  C   |   4     |
|   02   |  VERSAO          |  Versão do leiaute do arquivo. Versão atual "02"         |  C   |   2     |
|   03   |  DATA_INI        |  Data inicial do periodo do arquivo (dd/mm/yyyy)         |  C   |   10    |
|   04   |  DATA_FIM        |  Data termino do periodo do arquivo (dd/mm/yyyy)         |  C   |   10    |
|   05   |  DATA_GERACAO    |  Data e hora da geração do arquivo (dd/mm/yyyy hh:mm:ss) |  C   |   19    |

### Tabela - Linha com as informações da nota fiscal (N001)

| Número | Campo            | Descrição                                          | Tipo | Tamanho |
|:------:|------------------|----------------------------------------------------|:----:|:-------:|
|   01   |  ID_REG          |  Identificação do registro. Texto "N001"           |  C   |   4     |
|   02   |  SITUACAO_RPS    |  Situação da RPS (2 = Autorizado, 4 = Cancelado)   |  C   |   1     |
|   03   |  NUMERO_RPS      |  Número da RPS                                     |  C   |   20    |
|   04   |  EMISSAO_RPS     |  Data de emissão da RPS (dd/mm/yyyy hh:mm:ss)      |  C   |   19    |
|   05   |  NUMERO_NFSE     |  Número da NFSE                                    |  C   |   20    |
|   06   |  CNPJ/CPF        |  CNPJ / CPF do cliente                             |  C   |   14    |
|   07   |  NOME            |  Nome do cliente                                   |  C   |   250   |
|   08   |  LOGRADOURO      |  Logradouro do endereço do cliente                 |  C   |   250   |
|   09   |  NUMERO          |  Número do endereço do cliente                     |  C   |   20    |
|   10   |  COMPLEMENTO     |  Complemento do endereço do cliente                |  C   |   50    |
|   11   |  BAIRRO          |  Bairro do endereço do cliente                     |  C   |   250   |
|   12   |  CEP             |  CEP do endereço do cliente                        |  C   |   8     |
|   13   |  ESTADO_SIGLA    |  Sigla do estado do endereço do cliente            |  C   |   2     |
|   14   |  MUNICIPIO_NOME  |  Nome do município do endereço do cliente          |  C   |   250   |
|   15   |  VALOR_SERVICO   |  Valor do serviço                                  |  N   |   2*    |
|   16   |  BASE_CALCULO    |  Valor da base de calculo do ISS                   |  N   |   2*    |
|   17   |  ALIQUOTA_ISS    |  Percentual da aliquota do ISS                     |  N   |   2*    |
|   18   |  VALOR_ISS       |  Valor do do ISS                                   |  N   |   2*    |

### Tabela - Linha do item da nota fiscal (N100)

| Número | Campo            | Descrição                                          | Tipo | Tamanho |
|:------:|------------------|----------------------------------------------------|:----:|:-------:|
|   01   |  ID_REG          |  Identificação do registro. Texto "N100"           |  C   |   4     |
|   02   |  NUMERO_RPS      |  Número da RPS                                     |  C   |   20    |
|   03   |  PROD_CODIGO     |  Código do produto                                 |  C   |   20    |
|   04   |  PROD_DESCRICAO  |  Descrição do produto                              |  C   |   255   |
|   05   |  QTDADE          |  Qtdade do produto na nota                         |  N   |   2*    |
|   06   |  VALOR           |  Valor unitario do produto na nota                 |  N   |   2*    |
|   07   |  VALOR_TOTAL     |  Valor total do produto na nota                    |  N   |   2*    |
|   08   |  CONTA_CONTABIL  |  Conta contabil do produto                         |  C   |   100   |


### Tabela - Linha Rodapé da nota fical (N990)

| Número | Campo            | Descrição                                          | Tipo | Tamanho |
|:------:|------------------|----------------------------------------------------|:----:|:-------:|
|   01   |  ID_REG          |  Identificação do registro. Texto "N990"           |  C   |   4     |
|   02   |  QTD_LINHAS      |  Quantidade de itens da nota fiscal. Linhas "N100" |  N   |   2*    |


### Tabela - Linha Rodapé do Arquivo (G990)

| Número | Campo            | Descrição                                          | Tipo | Tamanho |
|:------:|------------------|----------------------------------------------------|:----:|:-------:|
|   01   |  ID_REG          |  Identificação do registro. Texto "G990"           |  C   |   4     |
|   02   |  QTD_LINHAS      |  Quantidade de linhas do arquivo sem o G990        |  N   |   2*    |
