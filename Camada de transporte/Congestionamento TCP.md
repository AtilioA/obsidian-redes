É controlado pelo algoritmo "*slow start*", que define uma *congestion window* (cwnd), ou janela de congestionamento, que tolera uma quantidade de [[Segmento|segmentos]]/pacotes não reconhecido, aumentando enquanto não houver perda; se houver perda, a janela diminui, podendo aumentar novamente.
> *When a connection is first established, the cwnd is set to a small value, and it is gradually increased over time as the connection becomes more stable.*

Fast recovery permite que o remetente [[TCP]] recupere mais rapidamente os [[Perda|pacotes perdidos]], pois pode continuar enviando novos [[Pacote|pacotes]] a uma taxa mais alta enquanto aguarda [[Acknowledgement|ACKs]] para os pacotes perdidos. Isso pode melhorar o desempenho geral da conexão reduzindo o tempo gasto na fase de slow start.

## Congestion avoidance
Ao entrar no estado de evitação de congestão, em vez de dobrar o valor da cwnd a cada RTT, o TCP adota uma abordagem mais conservadora e aumenta o valor da cwnd apenas um MSS (tamanho máximo de segmento) a cada RTT.

### Interrompendo slow start
A taxa de envio começa lenta, mas cresce de forma exponencial durante a fase de slow start. Mas quando esse crescimento exponencial deve terminar?
O slow start fornece várias respostas para essa pergunta:
- Primeiro, se houver um evento de perda (ou seja, congestão) indicado por um tempo limite, o remetente TCP define o valor de cwnd como 1 e começa o processo de slow start novamente. Ele também define o valor de uma segunda variável de estado, ssthresh (abreviação para "threshold de slow start", ou limite de slow start), como cwnd/2 - metade do valor da janela de congestão quando a congestão foi detectada.
- A segunda forma pela qual o slow start pode terminar está diretamente ligada ao valor de ssthresh. Como ssthresh é metade do valor de cwnd quando a congestão foi detectada pela última vez, pode ser um pouco arriscado continuar a dobrar cwnd quando ele atinge ou ultrapassa o valor de ssthresh. Portanto, quando o valor de cwnd é igual a ssthresh, o slow start termina e o TCP transita para o modo de evitação de congestão. Como veremos, o TCP aumenta cwnd mais cautelosamente quando está no modo de evitação de congestão;
- A forma final pela qual o slow start pode terminar é se forem detectados três reconhecimentos duplicados, nesse caso o TCP corta cwnd pela metade e realiza uma [[retransmissão rápida]].

![[Pasted image 20221217164755.png]]