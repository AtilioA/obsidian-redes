## Distribuição de arquivos cliente-servidor
A seguinte relação nos dá um limite inferior para o tempo necessário para distribuir bits em uma arquitetura cliente-servidor:
$$D_{cs} \geq max \left\{ \frac{NF}{u_s}, \frac{F}{d_{min}} \right\}$$
Onde $D_{cs}$ é o tempo de distribuição para a arquitetura cliente-servidor,
$N$ é o número de pares,
$F$ é o número de bits a serem distribuídos,
$u_s$ é a taxa de upload do enlace de acesso do servidor
$d_{min}$ é a taxa de download *mínima*, isto é, o par com menor taxa de download. 
	-> O par com menor taxa de download não pode obter todos os $F$ bits do arquivo em menos de $\frac{F}{d_{min}}$ segundos.