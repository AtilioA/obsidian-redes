---
alias: GBN
---
Go-Back-N ou *GBN*, ou ainda *GBN ARQ* é um algoritmo de [[sliding window protocol]] que é utilizado em redes de computadores para garantir a entrega confiável de dados. 
Este algoritmo permite que o remetente envie vários quadros de dados sem esperar por confirmações individuais de cada quadro. Em vez disso, o remetente:
1. Espera por uma confirmação geral após um certo número de quadros terem sido enviados.
2. Se o receptor não conseguir receber um quadro corretamente, ele envia uma mensagem de erro para o remetente, indicando que os quadros anteriores precisam ser reenviados.
![[Pasted image 20221219175416.png]]

>[!NOTE] Características
>- Envia pacotes N em paralelo
>- Utiliza temporizador
>- Utiliza ACK cumulativo (reenvia se receber ACK duplicado)
>- Descarta pacotes fora de ordem
>- Reenvia todos os pacotes após o perdido


Go-Back-N é um algoritmo eficiente para redes com erros de transmissão raros, mas pode ser menos eficiente em redes com erros de transmissão mais frequentes, pois o remetente precisa reenviar todos os quadros desde o início da janela até o quadro que foi recebido incorretamente.
Ele precisa enviar um tamanho de janela de N e receber um tamanho de janela de 1. Quando um quadro é recebido que está corrompido, o receptor descartará silenciosamente esse quadro e o remetente reenviará o quadro correto após o temporizador de tempo limite expirar.

%%TODO%%

Os quadros são numerados sequencialmente e são um número finito de quadros. O número máximo de quadros que podem ser enviados depende do tamanho da janela de envio. Se a confirmação de um quadro não for recebida dentro de um período de tempo acordado, todos os quadros a partir desse quadro são reenviados.

N é o tamanho da janela do remetente. Suponhamos que digamos Go-Back-3, o que significa que os três quadros podem ser enviados de uma vez antes de esperar a confirmação do receptor.

Ele usa o princípio de pipeline de protocolo, no qual vários quadros podem ser enviados antes de receber a confirmação do primeiro quadro. Se tivermos cinco quadros e o conceito for Go-Back-3, isso significa que os três quadros podem ser enviados, ou seja, o quadro número 1, o quadro número 2 e o quadro número 3 podem ser enviados antes de esperar a confirmação do quadro número 1.

No Go-Back-N ARQ, os quadros são numerados sequencialmente, pois o Go-Back-N ARQ envia vários quadros de uma vez, o que exige a abordagem de numeração para distinguir o quadro de outro quadro, e esses números são conhecidos como números sequenciais.

O número de quadros que podem ser enviados de uma vez depende totalmente do tamanho da janela do remetente. Portanto, podemos dizer que "N" é o número de quadros que podem ser enviados de uma vez antes de receber a confirmação do receptor.

Se a confirmação de um quadro não for recebida dentro de um período de tempo acordado, então todos os quadros disponíveis na janela atual serão reenviados. Suponhamos que tenhamos enviado o quadro número 5, mas não recebemos a confirmação do quadro número 5 e a janela atual está segurando três quadros, então esses três quadros serão reenviados.

O número de sequência dos quadros de saída depende do tamanho da janela do remetente. Suponha que o tamanho da janela do remetente seja 2 e tenhamos dez quadros para enviar, então os números de sequência não serão 1,2,3,4,5,6,7,8,9,10. Vamos entender através de um exemplo.

N é o tamanho da janela do remetente.
Se o tamanho da janela do remetente for 4, então o número de sequência será 0,1,2,3,0,1,2,3,0,1,2 e assim por diante.

O número de bits no número de sequência é 2 para gerar a sequência binária 00, 01, 10, 11.

Em resumo, o algoritmo Go-Back-N é um método de protocolo de janela deslizante que permite que o remetente envie vários quadros de uma só vez antes de receber uma confirmação do receptor. Se o receptor não conseguir receber um quadro corretamente, ele envia uma mensagem de erro para o remetente, indicando que os quadros anteriores precisam ser reenviados. O número de quadros que podem ser enviados de uma vez depende do tamanho da janela do remetente, e os quadros são numerados sequencialmente para distinguir um quadro de outro.
