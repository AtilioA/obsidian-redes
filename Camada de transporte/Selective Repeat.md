Com o selective repeat (SR), o remetente:
1. envia um número de quadros especificado pelo tamanho da janela, mesmo sem precisar esperar por um [[Acknowledgement|ACK]] individual do receptor como no [[Go-Back-N]];
2. O receptor pode selecionar rejeitar um único quadro, que pode ser retransmitido sozinho; 
	-> Isso contrasta com outras formas de ARQ, que devem enviar todos os quadros a partir daquele ponto novamente.
3. O receptor aceita quadros fora de ordem e os armazena em buffer;
4. O remetente retransmite individualmente os quadros que expiraram o *timeout*.

>[!NOTE] Resumo 
>O SR é mais complexo do que o GBN, tanto no remetente quanto no receptor, mas tem um desempenho melhor em termos de capacidade de tráfego. 
>	-> Isso ocorre porque o SR não precisa retransmitir um grande número de pacotes por causa de um único erro de pacote, como o GBN.
>- No entanto, o SR é mais propenso a erros de sincronização de sequência, pois o receptor precisa manter o controle dos números de sequência de cada pacote individualmente.

## Janela do emissor
A janela do emissor é um conjunto de números de sequência mantidos pelo remetente correspondentes aos números de sequência de quadros enviados, mas ainda não confirmados.
- O remetente pode transmitir um número máximo de quadros antes de receber qualquer confirmação sem bloqueio (pipeline);
- Quaisquer dos quadros em uma janela de envio podem ser perdidos ou corrompidos e, portanto, devem ser salvos na memória ou buffer até serem confirmados.

## Janela do receptor
A janela do receptor é um conjunto de números de sequência mantidos pelo receptor. Ela permite o recebimento e a confirmação de vários quadros.
- O tamanho da janela do receptor **é fixado em um tamanho inicial especificado**.
- Qualquer quadro recebido com um número de sequência fora da janela de recebimento é descartado.