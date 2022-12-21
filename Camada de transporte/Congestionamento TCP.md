## Controle de congestionamento
A quantidade de dados que uma conexão TCP pode colocar na tubulação é restrita pela janela de congestionamento (*cwnd*) do remetente.
**A janela de congestão determina essencialmente a taxa de envio**.
	->Ao contrário dos protocolos GBN e SR mais simples abordados na Seção 3.4, essa janela é dinâmica.
O TCP reduz a janela de congestão durante a ocorrência de um evento de perda, onde um evento de perda é ou um tempo limite ou a recepção de três confirmações duplicadas. 
Quando os eventos de perda não estão ocorrendo, o TCP aumenta sua janela de congestão. Isso dá origem à dinâmica em forma de serra para a janela de congestão, como mostrado na Figura 3.50 na página 267 do livro-texto. As regras exatas de como os eventos de perda influenciam a janela de congestão são determinadas por três mecanismos: Aumento Aditivo Redução Multiplicativa (AIMD); início lento; e retransmissão rápida.

Normalmente é controlado pelo algoritmo "*slow start*", que define uma *congestion window* (cwnd), ou janela de congestionamento, que tolera uma quantidade de [[Segmento|segmentos]]/pacotes não reconhecido, aumentando enquanto não houver perda; se houver perda, a janela diminui, podendo aumentar novamente.
> *When a connection is first established, the cwnd is set to a small value, and it is gradually increased over time as the connection becomes more stable.*

[[Retransmissão rápida]] permite que o remetente [[TCP]] recupere mais rapidamente os [[Perda|pacotes perdidos]], pois pode continuar enviando novos [[Pacote|pacotes]] a uma taxa mais alta enquanto aguarda [[Acknowledgement|ACKs]] para os pacotes perdidos. Isso pode melhorar o desempenho geral da conexão reduzindo o tempo gasto na fase de slow start.

## Congestion avoidance
Ao entrar no estado de evitação de congestão, em vez de dobrar o valor da cwnd a cada RTT, o TCP adota uma abordagem mais conservadora e aumenta o valor da cwnd apenas um MSS (tamanho máximo de segmento) a cada RTT.

### Interrompendo slow start
A taxa de envio começa lenta, mas cresce de forma exponencial durante a fase de slow start. Mas quando esse crescimento exponencial deve terminar?
O slow start fornece várias respostas para essa pergunta:
- Primeiro, se houver um evento de perda (ou seja, congestão) indicado por um tempo limite, **o remetente TCP define o valor de cwnd como 1 e começa o processo de slow start novamente. Ele também define o valor de uma segunda variável de estado, ssthresh (abreviação para "threshold de slow start", ou limite de slow start), como cwnd/2 - metade do valor da janela de congestão quando a congestão foi detectada.**
- A segunda forma pela qual o slow start pode terminar está diretamente ligada ao valor de ssthresh. Como ssthresh é metade do valor de cwnd quando a congestão foi detectada pela última vez, **pode ser um pouco arriscado continuar a dobrar cwnd quando ele atinge ou ultrapassa o valor de ssthresh. Portanto, quando o valor de cwnd é igual a ssthresh, o slow start termina e o TCP transita para o modo de evitação de congestão.** Como veremos, o TCP aumenta cwnd mais cautelosamente quando está no modo de evitação de congestão;
- A forma final pela qual o slow start pode terminar é se forem detectados três reconhecimentos duplicados, nesse caso o TCP corta cwnd pela metade e realiza uma [[retransmissão rápida]].

![[Pasted image 20221217164755.png]]