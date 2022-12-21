>[!TIP] Resumo
> A ideia por trás do controle de fluxo é que o receptor informe ao remetente quanto espaço livre ele tem no seu buffer de recebimento; e para que o remetente restrinja a quantidade de dados que coloca na pipeline para ser menor que o espaço livre. O controle de fluxo ajusta a taxa de envio do remetente à taxa de leitura do receptor.

Flow control reduz a possibilidade do emissor causar overflow no buffer do receptor; é um serviço de alinhamento de velocidades, igualando a velocidade com a qual o emissor envia com a velocidade que o receptor lê.

Flow control deve ser distinguido do [[Congestionamento TCP|controle de congestionamento]], que é usado para controlar o fluxo de dados quando o congestionamento ***de fato*** ocorreu.

Engloba *stop-and-wait*, *[[Sliding window protocol]]*, *[[Go-Back-N]]*.