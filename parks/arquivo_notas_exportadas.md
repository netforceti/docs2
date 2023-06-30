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
|   02   |  CNPJ            |  Versão do leiaute do arquivo. Versão atual "01"   |  C   |   2     |
|   03   |  xxxx            |  Versão do leiaute do arquivo. Versão atual "01"   |  C   |   2     |

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
