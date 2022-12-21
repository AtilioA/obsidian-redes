O livro-texto desenvolve incrementalmente um protocolo RDT "parada e espera" na Seção 3.4. Em um protocolo de parada e espera, a fonte envia um pacote de cada vez, enviando apenas um novo pacote depois de receber uma confirmação para o pacote anterior. 
	-> Esse tipo de protocolo tem desempenho muito ruim em termos de capacidade de tráfego, especialmente se a taxa de transmissão, R, ou o tempo de ida e volta, RTT, forem grandes.
	
Em um protocolo canalizado (de *pipeline*), o remetente pode enviar vários pacotes sem esperar por um [[Acknowledgement|ACK]]. A pipeline requer um intervalo aumentado de números de sequência e armazenamento adicional no remetente e no receptor.

O livro-texto examinou detalhadamente dois protocolos RDT canalizados: [[Go-Back-N]] (GBN) e [[Selective Repeat]] (SR).
***Ambos os protocolos limitam o número de pacotes não confirmados pendentes que o remetente pode ter na pipeline***.
-> O GBN usa confirmações cumulativas, confirmando apenas até o primeiro pacote não recebido. Um erro de um único pacote pode fazer com que o GBN retransmita um grande número de pacotes.
-> No SR, o receptor confirma individualmente os pacotes corretamente recebidos. O SR tem um desempenho melhor que o GBN, mas é mais complicado tanto no remetente quanto no receptor.