---
alias: tamanho máximo de segmento, maximum segment size
---

O ***tamanho máximo de segmento*** (*MSS*) é a maior quantidade de dados, especificada em bytes, que um computador ou dispositivo de comunicação pode lidar em um único pedaço não fragmentado. Ele é usado pelo Protocolo de Controle de Transmissão ([[TCP]]) da internet para determinar o tamanho máximo de cada pacote em qualquer transmissão.
O MSS segue o protocolo [[TCP]]/IP e geralmente está associado ao Ethernet, onde um pacote de ==1500 bytes é considerado padrão==.

Cada dispositivo TCP tem associado a ele um teto no tamanho TCP, um tamanho de segmento que nunca será excedido, independentemente de quanto grande for o [[tamanho de janela]] atual. Isso é chamado de tamanho máximo do segmento (MSS). Ao decidir quantos dados colocar em um segmento, cada dispositivo na conexão TCP escolherá a quantidade com base no tamanho da janela atual, em conjunto com os vários algoritmos, mas nunca será tão grande que a quantidade de dados ultrapasse o MSS do dispositivo para o qual está enviando.

---
Referências:
- [https://www.cloudflare.com/learning/network-layer/what-is-mss](https://www.cloudflare.com/learning/network-layer/what-is-mss)
- [https://www.webopedia.com/definitions/mss](https://www.webopedia.com/definitions/mss)
- [https://www.imperva.com/learn/application-security/what-is-mtu-mss](https://www.imperva.com/learn/application-security/what-is-mtu-mss)
- [https://www.geeksforgeeks.org/difference-between-mss-and-mtu-in-computer-networking](https://www.geeksforgeeks.org/difference-between-mss-and-mtu-in-computer-networking)
- [https://www.ibm.com/support/pages/what-mss-maximum-segment-size-and-how-it-calculated](https://www.ibm.com/support/pages/what-mss-maximum-segment-size-and-how-it-calculated)