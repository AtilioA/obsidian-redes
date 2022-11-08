É a probabilidade de haver **mais usuários simultâneos do que o sistema é capaz de atender**.
Ex: sistema com 2 Mbps de banda, em que até $k = 10$ usuários utilizam 400 Kbps, transmitindo 20% do tempo.
-> Então **ter mais de 5 usuários criará fila**.
	A **probabilidade de mais de 5 usuários** estarem transmitindo é de $\sum_{i=0}^4 [{10 \choose 6+i} 0.2^{6+i}*0.8^{4-i}]$.
	**Por partes**:
		${10 \choose 6}$: devemos considerar poder ser qualquer 6 usuários dentre os 10;
		$0.2^{6}$: Queremos 6 usuários transmitindo, e;
		$0.8^{4}$: 4 usuários não transmitindo.
		(Ver [[Packet switching - Probabilidade de um estar transmitindo e os outros não]])
		Os outros termos são referentes à soma, que irá somar cada termo considerando 6 (mínimo para haver fila) até 10 usuários (máximo de usuários no sistema).
			-> Dessa forma, estaremos calculando a probabilidade de haver mais de 6 usuários na fila, isto é, a probabilidade de haver fila.

