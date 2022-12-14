Vários [[Pacote|pacotes]] podem chegar para uma [[comutação de pacotes]] ao mesmo tempo. Se esses $n$ pacotes tiverem de ser encaminhados pelo mesmo [[enlace]] de saída, $n-1$ terão de ser enfileirados, isto é, esperarem para serem transmitidos. Esta espera introduz o atraso de fila.
Ainda, se a fila se tornar muito grande, o buffer pode se exaurir, fazendo com que pacotes sejam largados ou '*[[Perda|perdidos]]*'.
Em geral, o atraso de fila é dado por
$$A_t = \frac{N\cdot L +(L-x)}{R}$$, onde $N$ é o número de pacotes na fila, $L$ é o tamanho para todos os pacotes, $x$ é a quantidade de bits do pacote atual que já foi transmitida, e $R$ é a [[taxa de transmissão]] do enlace.
	-> Lembre-se que $L-x$ representa um pacote que já está sendo transmitindo e, portanto, não é contemplado no $N$, uma vez que o pacote não está mais na fila