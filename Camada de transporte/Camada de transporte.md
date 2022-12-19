**Protocolos de camada de transporte moram nos sistemas finais**, onde movimentam mensagens de processos de aplicação para a borda da rede (isto é, para a camada de rede) e vice-versa, mas não interferem no modo como as mensagens são movimentadas dentro do núcleo.

A camada de transporte estabelece canais de dados básicos que as aplicações usam para *troca de dados* específicos de tarefas. A camada estabelece conectividade de host para host na forma de ***serviços de transferência de mensagem ponto a ponto*** que são *independentes da rede subjacente* e *independentes da estrutura de dados de usuário* e da logística de troca de informações.

A camada de transporte em uma rede de computadores é responsável por fornecer serviços de comunicação entre processos de aplicação em execução em diferentes hosts. Ela fica entre as camadas de aplicação e rede e é implementada através de protocolos como o Protocolo de Controle de Transmissão ([[TCP]]) e o Protocolo de Datagrama de Usuário ([[UDP]]). A camada de transporte estende o serviço de entrega da camada de rede entre dois sistemas finais para um serviço de entrega entre dois processos de camada de aplicação.

A conectividade na camada de transporte pode ser categorizada como:
- orientada a conexão, implementada no TCP, ou
- sem conexão, implementada no UDP.

Os protocolos nesta camada podem fornecer controle de erro, [[Segmento|segmentação]], evitar ou recuperar-se de congestão dentro da rede através de técnicas como controle de fluxo (*flow control*) e [[Congestionamento TCP|controle de congestionamento]], e endereçamento de aplicações/aplicativos (números de porta).

