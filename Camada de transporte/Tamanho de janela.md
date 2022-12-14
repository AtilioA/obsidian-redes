No [[TCP]], o tamanho da janela se refere à quantidade de dados que um remetente pode transmitir a um receptor sem receber uma confirmação ([[Acknowledgement|ACK]]) do receptor. É um mecanismo de controle de fluxo que ajuda a evitar que o remetente sobrecarregue o receptor com muitos dados de uma vez.

>[!NOTE] Resumo
>- É **o número de pacotes que podem estar pendentes de confirmação** a qualquer momento.
>- Quanto maior for o tamanho da janela, **mais pacotes o remetente pode enviar sem esperar por uma confirmação**, o que **pode aumentar a capacidade de tráfego**.
>- No entanto, **também aumenta o risco de erros de pacote**, pois **o remetente não está esperando por uma confirmação antes de enviar o próximo pacote**.

**O tamanho da janela é expressado em bytes e é negociado entre o remetente e o receptor durante o processo de configuração da conexão.** O remetente pode ajustar o tamanho da janela com base na largura de banda disponível e no tempo de ida e volta (RTT) entre o remetente e o receptor. Um tamanho de janela maior permite que o remetente transmita mais dados de uma vez, o que pode melhorar a eficiência da conexão, mas também aumenta o risco de pacotes perdidos se a rede estiver congestionada.

No TCP, o tamanho da janela é dinâmico e pode ser ajustado durante o curso de uma conexão. O remetente pode aumentar ou diminuir o tamanho da janela com base no feedback do receptor, como ACKs e sinais de [[Congestionamento TCP|controle de congestão]]. Isso ajuda a garantir que o remetente esteja enviando dados em uma taxa que o receptor possa lidar e ajuda a evitar a congestão da rede.

The window size on the TCP layer is an advertisement of how much data a receiver can accept[[1]](https://www.networkcomputing.com/data-centers/network-analysis-tcp-window-size)[[2]](https://www.extrahop.com/company/blog/2017/tcp-windowing). It is negotiated during connection setup[[3]](https://learn.microsoft.com/en-us/troubleshoot/windows-server/networking/description-tcp-features) and can be up to 2^30/ MSS, where MSS is the maximum segment size[[4]](https://stackoverflow.com/questions/5208215/what-is-the-maximum-window-size-in-segments-of-a-tcp-connection). If the network bandwidth and delay product exceeds than the TCP receiver window size, then the window scaling option is enabled for the TCP connection[[4]](https://stackoverflow.com/questions/5208215/what-is-the-maximum-window-size-in-segments-of-a-tcp-connection).

https://www.extrahop.com/company/blog/2017/tcp-windowing/