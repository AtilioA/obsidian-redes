É o tempo transcorrido entre a requisição de um objeto feita pelo navegador e o recebimento dele.
É a soma do atraso da LAN, do atraso de acesso médio (entre os dois roteadores) e o atraso da Internet (em geral, é o [[RTT]]).

1. Tempo médio por requisição = $\frac{\text{tamanho médio do objeto (L)}}{\text{taxa de transmissão (R)}}$ -> igual ao [[atraso de transmissão]], porém usa tamanho médio de objeto;
2. Intensidade do tráfego no enlace: $\frac{\text{tempo médio por requisição}}{\text{requisições por segundo}}$?
3. Atraso de acesso médio: $\frac{\text{tempo médio por requisição}}{1 - \text{intensidade do tráfego no enlace}} + RTT$
>[!TIP] Caso exista cache, lembre-se de atualizar a intensidade do tráfego ao multiplicá-lo pela [[taxa de acerto local]] do cache:
>Atr8aso de acesso médio: $\frac{\text{tempo médio por requisição}}{1 - \text{taxa de acerto local} \cdot \text{intensidade do tráfego no enlace}} + RTT$ 
4. Se houver [[Caching|cache]], considere suas respectivas [[tempo total médio de resposta|taxas]].