# RELATÓRIO 1
## Objetivos.

Estudo das características de um amplificador operacional não ideal e de um circuito amplificador subtrator.

Parte 01 : Seguidor de tensão.

Objetivo específico: Verificar o funcionamento de um circuito seguidor de tensão.
Experimento: Utilizando um Amp.OP. Lm324N e um TL082 monte dois circuitos na configuração de seguidor de tensão(Buffer), com uma resistência de realimentação de 10 kΩ em cada um dos circuitos.
Utilize a alimentação simétrica de +/-12V. (limite a corrente em 0,05A)
Procedimento:
1. Monte o circuito no LTSPICE.
2. Configure a fonte com sinal senoidal com 0,5Vp @ 1 kHz e mostre o mesmo e analise o gráfico gerado.
3. Discuta os resultados.

# ANÁLISE TEÓRICA.

## AMPOP Lm324N circuito e gráfico de Vout.

![BufferLM324N](/Relatório 1/Imagens/parte1/BufferLM324N.png)

## AMPOP TL082 circuito e gráfico de Vout.

![BufferTL082](/Relatório 1/Imagens/parte1/BufferTL082.jpg)



Parte 02: Amplificador inversor
Objetivo específico: Medir o ganho de um amplificador inversor e verificar o efeito da saturação.
Experimento: Utilizando um Amp.OP. Lm324N e o TL082 monte dois amplificadores inversores utilize o resistor de realimentação com valor 20 kΩ e a resistência de entrada de 2kΩ.
Utilize a alimentação simétrica de +/-12V. (limite a corrente em 0,05A)
Procedimento:
1. Monte o circuito no LTSPICE.
2. Configure a fonte de entrada com sinal senoidal com 0,5Vp @ 1 kHz e mostre o mesmo e analise o gráfico gerado.
3. Analise o gráfico obtido
4. Verifique o valor do ganho obtido;
5. Aumente o valor da tensão de entrada lentamente e verifique para qual valor da tensão de
entrada ocorre à saturação do sinal.
6. Qual o valor da queda de tensão com relação a tensão de alimentação?
7. Não desmonte o circuito!!

Parte 03: Amplificador não-inversor
1
Objetivo específico: Medir o ganho de um amplificador não-inversor.
Experimento: Utilizando um Amp.OP. Lm324N e o TL082 monte dois amplificadores não inversores
use o resistor de realimentação com valor 20 kΩ e o outro resistor igual à 2kΩ.
Utilize a alimentação simétrica de +/-12V. (limite a corrente em 0,05A)
Procedimento:
1. Monte o circuito em uma matriz de contatos (protoboard) e antes de ligar as fontes chame
o professor.
2. Configure no gerador de função um sinal senoidal com 0,5Vp @ 1 kHz e mostre o mesmo
no canal 1 do osciloscópio.
3. Mostre a saída do amplificador no canal 2 do osciloscópio e chame o professor novamente
e mostre os resultados.
4. Verifique o valor do ganho obtido;
5. .
6. Qual o valor da queda de tensão com relação a tensão de alimentação?
Parte 04: Amplificador subtrator
Objetivo específico: verificar as não idealidades dos ampops aplicadas em um circuito subtrator.
Experimento: Utilizando um Amp.OP. Lm324N e o TL082 monte dois amplificadores subtratores
use o resistor de realimentação com valor 510kΩ e ganho igual á 10V/V.
Utilize a alimentação simétrica de +/-12V. (limite a corrente em 0,05A)
