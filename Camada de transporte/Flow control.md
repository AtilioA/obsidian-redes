Flow control reduz a possibilidade do emissor causar overflow no buffer do receptor; é um serviço de alinhamento de velocidades, igualando a velocidade com a qual o emissor envia com a velocidade que o receptor lê.

Flow control deve ser distinguido do [[Congestionamento TCP|controle de congestionamento]], que é usado para controlar o fluxo de dados quando o congestionamento ***de fato*** ocorreu.

Engloba *stop-and-wait*, *[[sliding window protocol]]*, *[[Go-Back-N]]*.