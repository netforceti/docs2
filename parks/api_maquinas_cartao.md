# API Parks Para Maquina de Cartão

Essa breve definição que como as operadoras de cartão poderão registrar os bilhetes emitidos em nosso sistema de ingressos.

A venda dos ingressos deverá ocorrer na maquina de cartão, ondes as funções de **emissão** e **pagamento** serão executadas na maquina de cartão de forma offline e posteriormente regsitrado os bilhetes no sistema do parque.


Quando ocorrer a venda de um bilhete o mesmo deverá ser cobrado do cliente e emitido o numero do bilhete, impresso o igresso e depois ser registrado no sistema.

### Numeração do bilhete
A numeração do bilhete deverá ser um número sequencial, não podendo ser repedito dentro de cada série. A série deverá ser um prefixo de dois dígitos numéricos, onde será a identificação da maquina de cartão do sistema do parque. Essa serie, deverá ser informada pelo sistema do parque e configurado em cada máquina de cartão.

Exemplo de numeração:
```php
010000123

/**
 * Onde:
 *  01 = número de série da maquina no sistema
 *  0000123 = Número do bilhete dentro da série.
 */
```

### Código de barras
O bilhete impresso pela maquina de cartão deverá ser exatamente o numero de bilhete e série registrado no sistema do parque, o mesmo poderá ser impressora do tipo de código de barra Code39 e ou QRCode.


### Registro do bilhete
Após ser emitido o bilhete na maquina de cartão o sistema do cartão deverá regsitrar os bilhetes emitidos no sistema do parque. Isso deverá ser feito pode lotes (vendas). Cada venda é responsavel por um pagamento.
O JSON que deverá ser enviado para o sistema do parque deverá ser:

```json
{
  "lote"       : "000123",
  "emissao"    : "2023-01-01 12:35:00",
  "serie"      : "01",    
  "pagamento": {
    "forma_pagto": "1",
    "valor_total": 110.00,
    "parcelas": 1,
    "codigo_transacao": "codigo de transacao do pagamento da maquina",
    "codigo_comprovante": "codigo do comprovante de pagamento",
    "codigo_autorizacao": "codigo de autorizacao do pagamento",
    "bandeira_cartao"   : "VISA",
    "cartao_numero"     : "000268******1234",
    "nome_no_cartao"    : "Fulano da Silva"
  },
  "bilhetes": [
    {
      "numero": "010000001234",
      "produto": "AD123",
      "valor"  : 45.00
    },
    {
      "numero": "010000001235",
      "produto": "AD123",
      "valor"  : 45.00
    },
    {
      "numero": "010000001236",
      "produto": "IN123",
      "valor"  : 20.00
    }        
  ]
```

### Resposta do registro

```json
{
  "status"  : "lote_registrado",
  "lote"    : "000123",
  "serie"   : "01",
  "lote_id" : 2
}
```

### AccessToken
A requisição deverá ser executada via método POST (Rest) com autorização via AccessToken que será fornecido durante a configuração o sistema, o mesmo accesstoken poderá ser utilizado por várias maquinas de cartão.
As requisições deverão ser enviadas para um endpoint fornecido durante a configuração do sistema.

### Tabela - Formas de Pagamento

----------------------------------------------------------------------------------
| Forma de Pagamento | Código                                                    |
|--------------------|-----------------------------------------------------------|
| Cartão de crédito  | 1                                                         |
| Cartão de débito   | 2                                                         |
| PIX                | 3                                                         |
| Dinheiro           | 4                                                         |
----------------------------------------------------------------------------------
