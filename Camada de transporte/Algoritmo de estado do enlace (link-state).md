---
alias: link-state
---
Os algoritmos de estado do enlace são um tipo de protocolo de roteamento utilizado em redes de computadores. Eles também são conhecidos como algoritmos de menor caminho primeiro (SPF).
Os algoritmos de estado de ligação funcionam criando um mapa da rede inteira, incluindo todos os dispositivos (nós) e as conexões (ligações) entre eles. Cada dispositivo na rede envia suas próprias informações de estado de ligação para todos os outros dispositivos na rede. Essas informações incluem o próprio endereço do dispositivo, os endereços de seus vizinhos diretamente conectados e o custo (por exemplo, distância ou número de saltos) da ligação entre cada um desses vizinhos e o dispositivo.
Com base nessas informações, cada dispositivo cria um mapa completo da rede e pode então usar esse mapa para determinar o melhor caminho para os dados seguirem de um dispositivo a outro.

O algoritmo de Dijkstra é um algoritmo específico usado para encontrar o caminho mais curto entre dois nós em um gráfico. Ele foi desenvolvido pelo cientista da computação Edsger Dijkstra na década de 1950. O algoritmo de Dijkstra funciona começando pelo nó de origem e explorando todos os nós vizinhos. Ele então seleciona o nó com o menor custo (por exemplo, distância ou número de saltos) e explora seus vizinhos, repetindo esse processo até chegar ao nó de destino.

$$D(v) = min\{D(v), D(w) + c(w,v)\}$$
Onde $D(v)$ é o custo do caminho de menor custo do nó origem ao nó destino $v$;