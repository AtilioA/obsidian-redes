## Distribuição de arquivos P2P
É uma aplicação que distribui um arquivo  a partir de uma única fonte ara um grande número de pares.

$$D_{cs} \geq max\{\frac{NF}{u_s}, \frac{F}{d_{min}}\}$$
Onde $D_{cs}$ é o tempo de distribuição para a arquitetura cliente-servidor,
$N$ é o número de pares,
$F$ é o número de bits,
$u_s$ é a taxa de upload do enlace de acesso o servidor
$d_{min}$ é a taxa de download *mínima*, isto é, o par com menor taxa de download. O par com menor taxa de download não pode obter todos os $F$ bits do arquivo em menos de $\frac{F}{d_{min}}$ segundos