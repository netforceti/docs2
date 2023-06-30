# Leiaute do arquivo das notas exportadas

Abaixo é exibido a descrição e definição do arquivo exportado das notas fiscais (RPS) do sistema de parques.

O arquivo é exportado em formado TXT onde cada linha terá um identificador, seguido com os demais campos separados por pipe ( | ).

Abaixo mostro a ordem e definição dos campos:

### Tabela - Linha Cabeçalho do Arquivo (G001)

| Número | Campo            | Descrição                                          | Tipo | Tamanho |
|:------:|------------------|----------------------------------------------------|:----:|:-------:|
|   01   |  ID_REG          |  Identificação do registro. Texto "G001"           |  C   |   4     |
|   02   |  VERSAO          |  Versão do leiaute do arquivo. Versão atual "01"   |  C   |   2     |

### Tabela - Linha com as informações da nota fiscal (N001)

| Número | Campo            | Descrição                                          | Tipo | Tamanho |
|:------:|------------------|----------------------------------------------------|:----:|:-------:|
|   01   |  ID_REG          |  Identificação do registro. Texto "N001"           |  C   |   4     |
|   02   |  NUMERO_RPS      |  Número da RPS                                     |  C   |   20    |
|   03   |  EMISSAO_RPS     |  Data de emissão da RPS (dd/mm/yyyy hh:mm:ss)      |  C   |   19    |
|   04   |  CNPJ/CPF        |  CNPJ / CPF do cliente                             |  C   |   14    |
|   05   |  VALOR_SERVICO   |  Valor do serviço                                  |  N   |   2*    |
|   06   |  BASE_CALCULO    |  Valor da base de calculo do ISS                   |  N   |   2*    |
|   07   |  ALIQUOTA_ISS    |  Percentual da aliquota do ISS                     |  N   |   2*    |
|   07   |  VALOR_ISS       |  Valor do do ISS                                   |  N   |   2*    |

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
|   02   |  QTD_LINHAS      |  Quantidade de itens da nota fiscal. Linhas "N002" |  N   |   2*    |


### Tabela - Linha Rodapé do Arquivo (G990)

| Número | Campo            | Descrição                                          | Tipo | Tamanho |
|:------:|------------------|----------------------------------------------------|:----:|:-------:|
|   01   |  ID_REG          |  Identificação do registro. Texto "G990"           |  C   |   4     |
|   02   |  QTD_LINHAS      |  Quantidade de linhas do arquivo sem o G990        |  N   |   2*    |
