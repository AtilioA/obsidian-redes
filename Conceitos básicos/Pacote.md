Dados divididos em pedaços menores ('*chunks*'), chamados de pacotes ou *packets*, para serem enviados a um destino.
Quando um pacote chega a um **comutador de pacotes**, este utiliza o destino do pacote para determinar a rota até o próximo [[enlace]] para qual encaminhar o pacote, a fim de atingir seu destino final.
>[!NOTE] Comutadores de pacote geralmente salvam o pacote inteiro e verificam integridade/checksum antes de enviá-lo (*store and forward*).
