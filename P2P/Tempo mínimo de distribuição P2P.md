## Distribuição de arquivos P2P
É uma aplicação que distribui um arquivo a partir de uma única fonte para um grande número de pares. A seguinte relação nos dá um limite inferior para este tempo:

$$D_{P2P} \geq max\left\{ \frac{F}{u_s}, \frac{F}{d_{min}}, \frac{NF}{u_s+\sum_{i=1}^{N}u_i} \right\}$$

Onde $D_{P2P}$ é o tempo de distribuição para a arquitetura P2P,
$F$ é o número de bits a serem distribuídos,
$N$ é o número de pares,
$u_s$ é a taxa de upload do enlace de acesso do servidor (neste caso, primeiro par a distribuir)
$d_{min}$ é a taxa de download *mínima*, isto é, o par com menor taxa de download.
	-> O par com menor taxa de download não pode obter todos os $F$ bits do arquivo em menos de $\frac{F}{d_{min}}$ segundos.
$u_i$ é a taxa de download para cada par na rede P2P.
