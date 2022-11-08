## Exemplo:
$N$ [[Pacote|pacotes]] chegam simultaneamente em um [[enlace]] com [[Taxa de transmissão]] $R$, não possuindo fila e nem servindo pacotes. Cada pacote possui tamanho $L$. 

**Qual é o atraso médio na fila**?
1. Para o primeiro pacote, é 0;
2. $\frac{L}{R}$ para o segundo;
3. $2\frac{L}{R}$ para o terceiro;
4. $\vdots$
5. $(N - 1)\frac{L}{R}$ para o último.
Somando (indução matemática) e dividindo por $N$ para tirar a média, teremos $(N-1)\frac{L}{2R}$.