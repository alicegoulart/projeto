# Instituto Federal de Santa Catarina - Campus Florianópolis Departamento Acadêmico de Eletrônica Curso de Engenharia Eletrônica

## Aluno: Luís André G. da Silva.

## Relatório sobre Dobrador de tensão e referência zener.

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
Levando-se em consideração a tensão de pico de 33,3 V já descontado o valor de queda sobre o diodo, o valor de corrente de 10mA no ampop e uma tensão de ripper de 10%  foi possível verificar o capacitor que mais se enquadaria. Cheguei a uma valor de 50uF e com intuito de aproximar para valores comerciais foi adotado na simulação um valor de 56uF.
Esperava-se que com a utilização do capacitor de 56uF a tensão de ripper ficasse próxima a 10%, no entanto o valor foi bem menor, aproximadamente, 1,7% da tensão de pico.
conclui-se que se for utilizado  valores maiores de capacitores a tensão de ripper será cada vez menor, porém sempre existirá.




### Parte 02: Circuito referência de tensão com diodo Zener.

Adicione a saída do dobrador de tensão do circuito anterior um regulador shunt para a referência de
tensão.

Projete este circuito considerando:

1- A tensão zener dever ser igual á tensão mínima de de saída menos 2V, ou seja, Vz = Vp -Vr -2V.
Onde Vp é a tensão máxima na saída do dobrador e Vr é tensão de ripple.Escolha o diodo zener de modo a minimizar o consumo neste circuito.
Qual a regulação de linha e qual a regulação de carga para este circuito?

*** Resultados:
Situação 1: Cálculo geral do resistor com valores do datasheet.

![calculo1](/Imagens/parte3/calculo1.JPG)

![calculo1](/Imagens/parte3/resultado1.JPG)

Observa-se que nesse primeiro momento a tensão de pico ficou menor, aproximadamente, 30,5V e que a tensão VCC ou regulada esta em aproximadamente 26,5V dentro dos parâmetros especificados no datasheet, porém com ripper a ser considerado.

Situação 2: Arbitrando o valor da corrente 1Z em 1,5mA.
![calculo1](/Imagens/parte3/calculo2.JPG)

![calculo1](/Imagens/parte3/resultado2.JPG)


Neste segundo momento se observa na simulação que a imposição da corrente fez o valor da tensão VZ ficar muito próxima da calculada.

Situação 3: teste de variação de 10% na fonte de tensão, ou seja, 280 V e 342 V de pico.

![calculo1](/Imagens/parte3/resultado280.JPG)

![calculo1](/Imagens/parte3/resultado342.JPG)

Em ambas situações se observou que mesmo havendo uma grande variação de tensão na fonte primaria os parâmetros de saída se mantiveram dentro do especificado no datasheet. primeiro mantendo tensão próxima a 26.35V (calculada) e em segundo corrente permanece entre 0.25 e 8 (mA).


Situação 4: Simulação para alimentação da carga.(AmpOp).

![calculo1](/Imagens/parte3/resultadocomcarga.JPG)

Fica claro que mesmo com a carga a corrente que passa pelo diodo zener se mantém próxima a 1,5mA e há uma pequena queda de tensão em VCC que agora será de 25,73V pela inclusão do transistor. Desta forma esperasse que os resultados se confirmem na prática.

Situação 4: Cáculo regulação.

![calculo1](/Imagens/parte3/regulação.JPG)

Obs.: Não foi possível utilizar o modelo spice do diodo zener devido a grande dificuldade de se encontrar o modelo spice.
