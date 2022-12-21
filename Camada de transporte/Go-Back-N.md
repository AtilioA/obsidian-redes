---
alias: GBN
---
Go-Back-N ou *GBN*, ou ainda *GBN ARQ* é um algoritmo de [[Sliding window protocol]] que é utilizado em redes de computadores para garantir a entrega confiável de dados. 
Este algoritmo permite que o remetente envie vários segmentos de dados sem esperar por confirmações individuais de cada segmento. Em vez disso, o remetente:
1. Espera por uma confirmação geral após um certo número de segmentos terem sido enviados;
2. Se o receptor não conseguir receber um segmento corretamente, ele envia uma mensagem de erro para o remetente, indicando que os segmentos anteriores precisam ser reenviados.

Um dos principais problemas do GBN é que ==um único erro de pacote pode resultar na retransmissão de um grande número de pacotes==. Isso ==pode levar a uma diminuição do desempenho== em termos de capacidade de tráfego. No entanto, o **GBN é relativamente simples de implementar** e **pode ser eficaz em redes com baixa probabilidade de erro de pacote**.

>[!NOTE] Resumo
>- Go-Back-N é um método de protocolo de janela deslizante que permite que o remetente envie vários segmentos de uma só vez antes de receber uma confirmação do receptor.
>1. Se o receptor não conseguir receber um segmento corretamente, ele envia uma mensagem de erro para o remetente, indicando que os segmentos anteriores precisam ser reenviados. 
>2. O número de segmentos que podem ser enviados de uma vez depende do tamanho da janela do remetente
>3. Os segmentos são numerados sequencialmente para distinguir um segmento de outro.

(Esta nota usa a terminologia de [[segmento]] ainda que o correto seja quadro/frame)

![[Pasted image 20221219175416.png]]

>[!NOTE] Características
>- Envia pacotes N em paralelo
>- Utiliza temporizador
>- Utiliza ACK cumulativo (reenvia se receber ACK duplicado)
>- Descarta pacotes fora de ordem
>- Reenvia todos os pacotes após o perdido
>  Does not require sorting at either the sender or receiver.

Go-Back-N é um algoritmo eficiente para redes com erros de transmissão raros, mas ***pode ser menos eficiente em redes com erros de transmissão mais frequentes***, pois o ***remetente precisaria reenviar todos os segmentos desde o início da janela até o segmento que foi recebido incorretamente***.
Ele precisa enviar um tamanho de janela de N e receber um tamanho de janela de 1. Quando um segmento é recebido que está corrompido, o receptor descartará silenciosamente esse segmento e o remetente reenviará o segmento correto após o temporizador de tempo limite expirar.

%%TODO%%

Os segmentos são numerados sequencialmente e são um número finito de segmentos. O número máximo de segmentos $N$ que podem ser enviados depende do tamanho da janela de envio. Se a confirmação de um segmento não for recebida dentro de um período de tempo acordado, todos os segmentos a partir desse segmento são reenviados.

$N$ é o tamanho da janela do remetente. Suponhamos que temos Go-Back-3, o que significa que os três segmentos podem ser enviados de uma vez antes de esperar a confirmação do receptor.

Ele usa o princípio de pipeline de protocolo, no qual vários segmentos podem ser enviados antes de receber a confirmação do primeiro segmento. Se tivermos cinco segmentos e o conceito for **Go-Back-3, isso significa que os três segmentos podem ser enviados, ou seja, o segmento número 1, o segmento número 2 e o segmento número 3 podem ser enviados antes de esperar a confirmação do segmento número 1.**

No Go-Back-N ARQ, os segmentos são numerados sequencialmente, pois o Go-Back-N ARQ envia vários segmentos de uma vez, o que exige a abordagem de numeração para distinguir o segmento de outro segmento, e esses números são conhecidos como números sequenciais.

O número de segmentos que podem ser enviados de uma vez depende totalmente do tamanho da janela do remetente. Portanto, podemos dizer que "N" é o número de segmentos que podem ser enviados de uma vez antes de receber a confirmação do receptor.

Se a confirmação de um segmento não for recebida dentro de um período de tempo acordado, então todos os segmentos disponíveis na janela atual serão reenviados. Suponhamos que tenhamos enviado o segmento número 5, mas não recebemos a confirmação do segmento número 5 e a janela atual está segurando três segmentos, então esses três segmentos serão reenviados.

O número de sequência dos segmentos de saída depende do tamanho da janela do remetente. Suponha que o tamanho da janela do remetente seja 2 e tenhamos dez segmentos para enviar, então os números de sequência não serão 1,2,3,4,5,6,7,8,9,10. Vamos entender através de um exemplo.

?
N é o tamanho da janela do remetente.
Se o tamanho da janela do remetente for 4, então o número de sequência será 0,1,2,3,0,1,2,3,0,1,2 e assim por diante.

O número de bits no número de sequência é 2 para gerar a sequência binária 00, 01, 10, 11.
?