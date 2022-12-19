## Item I
A vazão de $V_1$ pode ser estimada como:
$V_1 = \frac{32+40}{2} * 11 + \frac{20+30}{2} * 6 = 546$
$V_2 = \frac{32+40}{2} * 11 + \frac{32+35}{2} * 2 = 463$

## Item II
O protocolo TCP utiliza o algoritmo de "slow start" para controlar o congestionamento da rede. Esse algoritmo define uma janela de congestionamento, por vezes chamada de cwnd, que é um limite para a quantidade de segmentos que podem ser enviados sem esperar por um reconhecimento. Se não houver perda de segmentos durante o envio, a cwnd é aumentada aos poucos, mas se houver perda, a cwnd é diminuída. Quando uma conexão é inicialmente estabelecida, a cwnd é definida como um valor pequeno e é gradualmente aumentada à medida que a conexão se torna mais estável.

## Item III
É verdadeiro para $V2$, porém o $V1$ volta para 1 por conta de um *timeout*. Para a rodada 23, os dois são perda por *timeout*.

## Item IV
Sim, mas é reajustado para 20 pois é a metade de 40, quando ocorre a perda de fato.