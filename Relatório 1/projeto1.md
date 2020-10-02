# Instituto Federal de Santa Catarina - Campus Florianópolis Departamento Acadêmico de Eletrônica Curso de Engenharia Eletrônica

## Alunos:

## Luís André G. da Silva

### Relatório sobre Circuitos com Amplificadores Operacionais

## Objetivos.

Estudo das características de um amplificador operacional não ideal e de um circuito amplificador subtrator.

Parte 01 : Seguidor de tensão.

Objetivo específico: Verificar o funcionamento de um circuito seguidor de tensão.
Experimento: Utilizando um Amp.OP. Lm324N e um TL082 monte dois circuitos na configuração de seguidor de tensão(Buffer), com uma resistência de realimentação de 10 kΩ em cada um dos circuitos.
Utilize a alimentação simétrica de +/-12V. (limite a corrente em 0,05A)
Procedimento:
1. Monte o circuito no LTSPICE.
2. Configure a fonte com sinal senoidal com 0,5Vp @ 1 kHz e analise o gráfico gerado.
3. Discuta os resultados.

## Análise teórica.

### AMPOP Lm324N circuito e gráfico de Vout.

![BufferLM324N](/Imagens/parte1/BufferLM324N.PNG)

### AMPOP TL082 circuito e gráfico de Vout.

![BufferTL082](/Imagens/parte1/BufferTL082.JPG)

## Conclusão.

Sabendo-se que o ganho para a topologia Buffer tem ganho igual a 1 fez-se a análise com dois modelos de AMPOP Lm324N e TL082 e se constatou que de fato não houve ganho de tensão na saída Vout.
sendo assim, foi verificado que este modelo pode ser usado para isolar e conectar um estágio de alta impedância de entrada a uma carga de baixa impedância de saída sendo este conhecido também como caçador de impedâncias





### Parte 02: Amplificador inversor

Objetivo específico: Medir o ganho de um amplificador inversor e verificar o efeito da saturação.
Experimento: Utilizando um Amp.OP. Lm324N e o TL082 monte dois amplificadores inversores utilize o resistor de realimentação com valor 20 kΩ e a resistência de entrada de 2kΩ.
Utilize a alimentação simétrica de +/-12V. (limite a corrente em 0,05A)
Procedimento:
1. Monte o circuito no LTSPICE.
2. Configure a fonte de entrada com sinal senoidal com 0,5Vp @ 1 kHz.
3. Analise o gráfico obtido.
4. Verifique o valor do ganho obtido;
5. Aumente o valor da tensão de entrada lentamente e verifique para qual valor da tensão de entrada ocorre à saturação do sinal.
6. Qual o valor da queda de tensão com relação a tensão de alimentação?
7. Não desmonte o circuito!!

## Análise teórica.

![InvesorLM324N](/Imagens/parte1/Inversora.JPG)

### AMPOP LM324N circuito e gráfico de Vin e Vout.

![InvesorLM324N](/Imagens/parte1/InversorLM324N.JPG)

### Saturação do circuito LM324N.

![InvesorLM324N](/Imagens/parte1/saturaçãoinversoraLM324N.JPG)

### AMPOP TL082 circuito e gráfico de Vin e Vout.

![InversorTL082.JPG](/Imagens/parte1/InversorTL082.JPG)

### Saturação do circuito TL082.
![InversorTL082.JPG](/Imagens/parte1/saturaçãoinversoraTL082.JPG)

## Conclusão.
Diante do que foi analisado pode-se verificar que o valor de ganho foi de -10, sendo assim a tensão de entrada deverá ficar dez vezes maior e com a senoide invertida e de fato ocorreu na Análise gráfica.

Já quanto a saturação dos dois ampops verificou-se que ambos tem limites de 12V, pois é a tensão de alimentação desde. Partindo da analise individual se verificou que o LM324N tem como valor máximo para saturação -11.33V para a parte da onda negativa e 10.77V para a parte da onda positiva.

O TL082 apresentou valores de saturação diferentes do LM324N,mas estes valores foram iguais para a parte positiva e negativa da curva sendo estes de +-10.44V.

Com isso, fica claro que para cada projeto a ser executado deve-se tem em mente a distinção entre os componentes e que estes podem apresentar valores diferentes de tensão para a parte negativa e positiva quando em saturação.



### Parte 03: Amplificador não-inversor

Objetivo específico: Medir o ganho de um amplificador não-inversor.

Experimento: Utilizando um Amp.OP. Lm324N e o TL082 monte dois amplificadores não inversores
use o resistor de realimentação com valor 20 kΩ e o outro resistor igual à 2kΩ.
Utilize a alimentação simétrica de +/-12V. (limite a corrente em 0,05A)
Procedimento:

1. Monte o circuito no LTSPICE.
2. Configure a fonte de tensão de entrada senoidal com 0,5Vp @ 1 kHz.
3. Verifique o valor do ganho obtido;
4. Qual o valor da queda de tensão com relação a tensão de alimentação?

## Análise teórica.

![nãoinversor](/Imagens/parte1/nãoinversor.JPG)

### AMPOP LM324N circuito e gráfico de Vin e Vout.

![InvesorLM324N](/Imagens/parte1/nãoinversoraLM324.JPG)



### AMPOP TL082 circuito e gráfico de Vin e Vout.

![nãonversoraTL082](/Imagens/parte1/nãoinversoraTL082.JPG)


## Conclusão.

Com demostrado na figura o ganho esperado é de 11 unidades o que de fato se percebe na simulação do circuito,Mas uma ponto importante a se expor é que o Ampop LM324 tem uma ganho de tensão de aproximadamente 0,021V já o TL082 tem queda de aproximadamente 0,007V.
O valor de referencia é de 5.5 V, já que o ganho multiplica o valor de entrada de 0,5V, tais situações somente poderiam ser comprovadas na prática.



### Parte 04: Amplificador subtrator.

Objetivo específico: verificar as não idealidades dos ampops aplicadas em um circuito subtrator.

Experimento: Utilizando um Amp.OP. Lm324N e o TL082 monte dois amplificadores subtratores.

use o resistor de realimentação com valor 510kΩ e ganho igual á 10V/V.

Utilize a alimentação simétrica de +/-12V. (limite a corrente em 0,05A)


Procedimento:
1. Monte o circuito no LTSPICE.

![subtratorTL082](/Imagens/parte1/modelo4_1.JPG)

2. Compare os resultados para o LM324N e para TL082.


![Subtrator](/Imagens/parte1/subtrator.JPG)

### AMPOP LM324N circuito e gráfico de Vout.

![InvesorLM324N](/Imagens/parte1/subtratorLM324.JPG)

De acordo com a  análise teórica o valor de tensão sobre o resistor de 1 ohm será de 96,6962 V, fazendo um divisor de tensão entre os resistores de 620 e 1 Ohm. desconsiderando a carga(ampop).
Feito isso, se verificou que a tensão de saída sobre o LM324 ficou em aproximadamente 130mV, já o TL082 teve uma melhor aproximação de tensão do valor teórico ficando em 95,14mV.

### AMPOP TL082 circuito e gráfico de Vout.

![subtratorTL082](/Imagens/parte1/subtratorTL082.JPG)


3. Caso a fonte V1 tenha o valor igual á 0(zero)V, qual o valor da tensão de saída, para ambos os circuitos? Explique.

### V1 igual a zero LM324N.

![subtratorTL082](/Imagens/parte1/LMZEROVOLTS.JPG)

### V1 igual a zero TL082.

![subtratorTL082](/Imagens/parte1/subtratortensaozero.JPG)


4. Caso o seja alterado para o circuito abaixo, existe alguma variação na saída? Explique.

![subtratorTL082](/Imagens/parte1/modelo4_2.JPG)


### Alteração do circuito com LM324N.

![InvesorLM324N](/Imagens/parte1/subtrator2LM324.JPG)


### Alteração do circuito com TL082.

![subtratorTL082](/Imagens/parte1/subtrator2TL082.JPG)


Após a comparação entre os gráficos pode-se observar que há uma pequena melhora nos valores de tesão de saída se aproximando mais ao valor de 96,6962V esperado e mais uma vez o TL082 se mostrou fiel ao resultado teórico com 96,80V Vout.

5. Justifique as dissimilaridades encontradas utilizando os dados do datasheet.


## Conclusão.

O amplificador subtrator é um excelente modelo quando se quer buscar um parâmetro de referência de tensão, pois uma pequena diferença de tensão pode ser multiplicada pelo ganho podendo ser usada para outras finalidades.
Quando se fala nos amplificadores testados pode-se verificar que há diferença entre eles tendo o LM324N alcançado valores mais discrepantes quando comparados ao valor teórico.
Já o TL082 teve valores muito próximos ao desejado.
