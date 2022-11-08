Depende da capacidade de [[caching]] instalado. Em geral, a *taxa de resposta local* - fração de requisições atendidas por um cache - fica entre 0.2 e 0.7.
## Exemplo
Se uma instituição possui cache com tempo de resposta local de 0.4, 40% das requisições serão atendidas quase de imediato pelo cache (digamos que em 10ms). No entanto, os demais 60% serão atendidos pelos servidores de origem; ainda, isso reduz a [[intensidade de tráfego na LAN]] neste servidor de 1.0 para 0.6, ficando na casa das dezenas de milissegundos.

Um exemplo de atraso médio, então, poderia ser:
$(0.4 \cdot \overbrace{0.01}^{\text{delay cache}}) + (0.6\cdot\overbrace{2.01}^{\text{RTT + tráfego}})$

No geral, teremos então:
$(p_c \cdot a_c) + (\neg p_c \cdot a_s)$
onde $p_c$ é taxa de acerto do cache, $a_c$ é o atraso do cache, $a_s$ é o atraso do servidor de origem.