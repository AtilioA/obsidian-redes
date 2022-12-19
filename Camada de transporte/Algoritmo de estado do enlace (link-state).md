---
alias: link-state, Dijkstra
---
Os algoritmos de estado do enlace são um tipo de protocolo de roteamento utilizado em redes de computadores. Eles também são conhecidos como algoritmos de menor caminho primeiro (SPF).
Os algoritmos de estado de ligação funcionam criando um mapa da rede inteira, incluindo todos os dispositivos (nós) e as conexões (ligações) entre eles. Cada dispositivo na rede envia suas próprias informações de estado de ligação para todos os outros dispositivos na rede. Essas informações incluem o próprio endereço do dispositivo, os endereços de seus vizinhos diretamente conectados e o custo (por exemplo, distância ou número de saltos) da ligação entre cada um desses vizinhos e o dispositivo.
Com base nessas informações, cada dispositivo cria um mapa completo da rede e pode então usar esse mapa para determinar o melhor caminho para os dados seguirem de um dispositivo a outro.

O algoritmo de Dijkstra é um algoritmo específico usado para encontrar o caminho mais curto entre dois nós em um gráfico. Ele foi desenvolvido pelo cientista da computação Edsger Dijkstra na década de 1950. O algoritmo de Dijkstra funciona começando pelo nó de origem e explorando todos os nós vizinhos. Ele então seleciona o nó com o menor custo (por exemplo, distância ou número de saltos) e explora seus vizinhos, repetindo esse processo até chegar ao nó de destino.

$$D(v) = min\{D(v), D(w) + c(w,v)\}$$
Onde $D(v)$ é o custo do caminho de menor custo do nó origem ao nó destino $v$;

## Algoritmo
O algoritmo de Dijkstra é um algoritmo de busca utilizado para encontrar o menor caminho entre dois nós em um grafo valorado. Ele é muito útil para encontrar o menor caminho entre dois pontos em uma rede, como um mapa de rotas ou uma rede de computadores.

passo a passo simplificado da execução do algoritmo de Dijkstra:
1.  Escolha o nó de partida e marque a distância até ele como zero. Marque todos os outros nós como "não visitados" e atribua a eles a distância infinita, a menos que tenham aresta direta;
2.  Encontre o nó "não visitado" mais próximo e marque-o como visitado. Atualize as distâncias para os nós adjacentes, caso elas sejam menores do que as distâncias atuais;
3.  Repita o passo 2 até que todos os nós sejam visitados;
4.  Para encontrar o menor caminho, basta seguir os nós visitados em ordem, a partir do nó de partida (utilizado para rodar o algoritmo) até o nó de destino.
5. Se o nó de destino não foi encontrado, isso significa que não há caminho entre os dois nós.