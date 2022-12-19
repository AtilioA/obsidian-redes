---
alias: distance vector, Bellman-Ford
---
Utiliza equação do caminho de menor custo de Bellman-Ford, sendo:
$$d_x(y) = min_v\{c(x, v) + d_v(y)\}$$
## Algoritmo
O algoritmo de Bellman-Ford é um algoritmo de busca utilizado para encontrar o menor caminho entre dois nós em um grafo valorado. Ele é capaz de lidar com grafos que possuem arestas com pesos negativos, o que o torna útil em alguns casos em que o algoritmo de Dijkstra não é aplicável.

Passo a passo simplificado da execução do algoritmo de Bellman-Ford:
1.  Escolha o nó de partida e marque a distância até ele como zero. Marque todos os outros nós como "não visitados" e atribua a eles distância infinita.
2.  Para cada aresta (u, v) do grafo, verifique se a distância atual para o nó v pode ser atualizada, utilizando a seguinte fórmula: distância[v] = min(distância[v], distância[u] + peso(u, v)).
	-> Isso significa que, se houver um caminho mais curto para o nó v passando pelo nó u, atualize a distância para o nó v.
3.  Repita o passo anterior V-1 vezes, onde V é o número de nós do grafo. Isso garante que todos os caminhos possíveis são verificados e que a distância para cada nó é atualizada corretamente.
4.  Para encontrar o menor caminho, basta seguir os nós visitados em ordem, a partir do nó de partida até o nó de destino.
5.  Se o nó de destino não foi encontrado, isso significa que não há caminho entre os dois nós.