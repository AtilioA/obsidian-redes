Em fast recovery ou fast retransmit, um remetente retransmite rapidamente um pacote que foi perdido ou corrompido durante a transmissão, **sem esperar por um tempo limite** ou outra indicação de que o pacote não foi recebido corretamente.
**Ele é acionado quando 3 [[Acknowledgement|ACKs]] duplicados são recebidos para o mesmo [[segmento]] de dados.** Ele permite uma retransmissão de segmentos/pacotes perdidos sem esperar pela expiração de um timer de retransmissão retransmission timer to expire. Depois da retransmissão, o remetente continua a transmitir dados normalmente.
Isso pode ajudar a melhorar a eficiência e confiabilidade de uma rede, reduzindo o tempo gasto esperando por pacotes perdidos serem retransmitidos.

## Exemplo
Como uma retransmissão rápida poderia funcionar:
1.  O remetente envia um pacote para o receptor.
2.  O receptor não recebe o pacote devido a um erro de transmissão.
3.  O remetente não recebe uma confirmação (ACK) do receptor, indicando que o pacote não foi recebido corretamente.
4.  O remetente assume que o pacote foi perdido e retransmite o pacote.
5.  O receptor recebe o pacote retransmitido e envia um ACK para o remetente.

Neste exemplo, a retransmissão rápida ajuda a recuperar um pacote perdido sem que o remetente tenha que esperar por um tempo limite para ocorrer. Isso pode ajudar a melhorar o desempenho geral da rede, reduzindo o tempo gasto esperando por pacotes perdidos serem retransmitidos.