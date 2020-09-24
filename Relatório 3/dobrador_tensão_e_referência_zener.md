# Objetivos

Os objetivos desta aula de laboratório são:
1 Estudar os circuitos multiplicadores de tensão e os reguladores shunt com diodos zener;
2 Em todas as montagens o diodo será o 1n4007 e AmpOp o LM324.
Em todos os circuitos verifique a queda de tensão máxima nos diodos.

### Parte 01: Circuito dobrador de tensão.
Verifique qual a corrente consumida pelo CI LM324, lembre-se este CI tem 04 (quatro)
amplificadores operacionais. Considere também uma corrente de saída dos Ampops de 10mA.
Projete um circuito dobrador de tensão utilizando como tensão de entrada um transformador com
tap central de 12Vrms e no máximo 200ms de tempo de inicialização do circuito.
Qual a tensão de ripple obtida?

![dobrador de tensão](/Imagens/parte3/dobradordetensao.JPG)

fonte: Internet.

### Resultados.


![dobrador de tensão](/Imagens/parte3/capacitor.JPG)

![dobrador de tensão](/Imagens/parte3/dobradordetensaocomcarga.JPG)

### Conclusão.
Levando-se em consideração o valor de corrente de 10mA no ampop e uma tensão de ripper de 10% de  foi possível verificar o capacitor que mais se enquadaria e se chegou a uma valo de 50uF com intuito de aproximar para valores comerciais foi adotado na simulação um valor de 56uF.
Esperava-se que com a utilização do capacitor de 56uF a tensão de ripper ficasse próxima a 10%, no entanto o valor foi bem menor, aproximadamente 1,7% da tensão de pico.
conclui-se que se for utilizado  valores maiores de capacitores a tensão de ripper será cada vez menor, porém sempre existirá.




Parte 02: Circuito referência de tensão com diodo Zener
Adicione a saída do dobrador de tensão do circuito anterior um regulador shunt para a referência de
tensão.
Projete este circuito considerando:
a tensão zener dever ser igual á tensão mínima de de saída menos 2V, ou seja, Vz = Vp -Vr -2V.
Onde Vp é a tensão máxima na saída do dobrador e Vr é tensão de ripple.
Escolha o diodo zener de modo a minimizar o consumo neste circuito.
Qual a regulação de linha e qual a regulação de carga para este circuito?
