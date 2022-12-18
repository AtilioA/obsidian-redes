É controlado pelo algoritmo "*slow start*", que define uma *congestion window* (cwnd), ou janela de congestionamento, que possui uma quantidade de [[Segmento|segmentos]]/pacotes que aumenta enquanto não houver perda; se houver perda, a janela diminui, podendo aumentar novamente.
> *When a connection is first established, the cwnd is set to a small value, and it is gradually increased over time as the connection becomes more stable.*

Fast recovery permite que o remetente [[TCP]] recupere mais rapidamente os [[Perda|pacotes perdidos]], pois pode continuar enviando novos [[Pacote|pacotes]] a uma taxa mais alta enquanto aguarda [[Acknowledgement|ACKs]] para os pacotes perdidos. Isso pode melhorar o desempenho geral da conexão reduzindo o tempo gasto na fase de slow start.

![[Pasted image 20221217164755.png]]