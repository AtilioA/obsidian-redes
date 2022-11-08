O atraso de transmissão de um [[enlace]] é igual ao número de bits em um [[pacote]] dividido pela [[Taxa de transmissão]] do enlace:
$$A_t=\frac{\text{bits}}{\text{bitrate}}$$

>[!TIP] É o tempo que leva para passar todos os bits de um pacote para dentro de um enlace.
>Note que, uma vez dentro do enlace, o pacote deve ser propagado para o outro lado.

>[!WARNING] Não depende do tamanho/distância do enlace nem da velocidade de propagação.

>[!NOTE] Também chamado de *store-and-forward delay*, ou ainda **packetization delay**.
>Este atraso é ocorre para realizar a política de *store-and-forward*, em que pacotes são armazenados para que seja feita a verificação de integridade destes antes que sejam enviados para frente. Teremos então um [[atraso de processamento]], que também contempla determinar o próximo destino no envio do pacote.
