É o tempo total de atraso ao enviar um pacote de um *end system* a outro, sendo a soma do [[atraso de transmissão]], do [[atraso de propagação]], [[atraso de fila]] e [[atraso de processamento]] em cada etapa.
$$A_{Total} = \frac{\text{bits}}{\text{bitrate}} + \frac{T}{v} + A_f+d_{proc}$$
Mais especificamente:
1. Primeiramente, temos que transmitir o pacote para dentro do meio de comunicação, tendo então um [[atraso de transmissão]];
2. Após isso, devemos enviar o pacote a um [[enlace]]; teremos um [[atraso de propagação]];
3. Quando o pacote chega ao enlace, normalmente este segue a política de *store-and-forward*, que em termos práticos para nosso contexto levará a um [[atraso de transmissão]], visto que o enlace irá baixar os conteúdos do pacote para verificar integridade, etc;
4. Esta e outras verificações (como determinar próximo destino), por sua vez, provocam [[atraso de processamento]];
5. Repita os passos 2., 3. e 4. até chegar ao último enlace;
6. Por fim, teremos um atraso de propagação para o *end system*.