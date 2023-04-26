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
