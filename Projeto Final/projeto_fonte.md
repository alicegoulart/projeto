# Instituto Federal de Santa Catarina - Campus Florianópolis Departamento Acadêmico de Eletrônica Curso de Engenharia Eletrônica

Alunos:

*Luís André G. da Silva


## Objetivos
Integração dos blocos de uma fonte linear.

## Introdução
Neste roteiro iremos integrar os circuitos estudados anteriormente, para isso, revise os conceitos de reguladores LDO e tenha em mãos os roteiros anteriores.

## Especificações técnicas básicas:

Construir um regulador de tensão com as seguintes características:

•	Corrente de saída: 1 A;

•	Rede Elétrica: 220 V +- 10% , 60 Hz;

•	Ondulação da tensão de saída a plena carga: a melhor possível;

•	Regulação da tensão de saída: No máximo 1%;

•	Tensões de saída 15V.

## Componentes utilizados para a construção da fonte.
1-Transformador de 220/12 V;

2-Diodos 1N4007;

3-Diodos Zener DTDZV27 e EDZV11B;

4-Capacitores de 2,5mF e 9,1mF;

5-Transistores tipo BJT 2n3904 e 2SA1774;

6-Transistores tipo MOS 2N7002 e IRF540;

7-Aplificador operacional LM324;

8- Resistores.

## Concepção geral da fonte

Um regulador de tensão em geral esta divido em blocos sendo este inicialmente o bloco de transformação onde um transformador, geralmente abaixador, diminui a tensão para valores próximos ao valor desejado.
O segundo bloco consta de um processo de retificação podendo ser de meia onda, onda completa com ponto médio ou onda completa em ponte, todos possuem vantagens e desvantagem. Para este relatório será usando o retificador de onda completa com center tap.
O terceiro bloco busca fazer o papel de filtro com a finalidade de retirar o máximo de ripple da onda, deixando-a mais próxima de uma linha contínua.
No quarto bloco está o regulador propriamente dito, pois neste bloco poderá se utilizado um modelo de regulação. Podendo ser montado com transistores, resistores, diodos zener e amplificadores operacionais.

![primeiro bloco](/Imagens/parte5/esquemaemblocos.JPG)


## Transformador.


![primeiro bloco](/Imagens/parte5/transformador1.JPG)

Neste primeiro momento é importante destacar que a melhor metodologia para a construção da fonte linear seria partir da carga até o transformador, haja vista, que para se compreender qual o transformador ideal para o regulador seria necessário se entender todas as quedas de tensão no circuito, ou  pelo menos estaria mais próximo do valor real necessário.
Neste relatório foi feito inicialmente uma projeção das quedas de tensão e se colocou para um valor que não ficasse tão distante do valor final da fonte e que ao mesmo tempo  o transformador fosse um item comercial e que pudesse suprir a tensão necessária para a carga.
Sendo assim, inicialmente, os seguintes dados abaixo foram especificados e se concluiu que será preciso  um transformador com relação de transformação de 220 V para 12v; corrente máxima de saída de 2 A; e frequência de 60Hz. para o pior caso quando a tensão de entrada estiver em 198V ou 242V. conforme especificado para este projeto.

![primeiro bloco](/Imagens/parte5/transformador.JPG)
#### Figura 3.

Conforme já esperado a tensão de saída ficou em 12V RMS e 17,05V de pico.

### Projeto do retificador

![tensaomaxeficmedcarga220](/Imagens/parte2/ondacompletacomderivacao.JPG)
#### Figura 4.

Um circuito retificador, ou simplesmente retificador, corresponde aos circuitos elétricos de tensão elaborados para a conversão de corrente alternada em corrente de passagem .
Utiliza-se para este processo elementos semicondutores, tais como os diodos e tiristores, além de um transformador. Em outras palavras, trata-se de um dispositivo que permite que uma tensão, ou corrente alternada (CA) (normalmente senoidal) seja constante, ou seja transformada em contínua.
Existem alguns tipos de retificadores: meia onda, onda completa com ponte ou onda completa com ponto médio. Para este trabalho foi adotado o onda completa com center tap.

![primeiro bloco](/Imagens/parte5/retificação.JPG)
#### Figura 5.

Foi incluído neste circuito uma carga de 16ohms para a simulação de aproximadamente 1A de corrente. De fato se verifica o processo de retificação da onda senoidal de entrada.

## Projeto do Filtro

![primeiro bloco](/Imagens/parte5/filtragem.JPG)


Como já visto na figura anterior o retificador fez o processo de transformar a corrente alternada em corrente contínua, porém ainda não é o ideal para dispositivos que funcionam em CC. Para que seja obtida uma tensão mais "lisa" é fundamental o emprego de filtro. Podendo esse se apresentar capacitivo, capacitivo-indutivo ou até capacitivo-indutivo-resistivo.
Neste trabalho será aplicado o filtro tipo capacitivo devido a sua facilidade de cálculos e de implementação.
Para se obter o filtro corretamente se verifica alguns parâmetros como: tensão de ondulação e regulação de tensão.
para a filtragem foi adotado que a tensão de Ripper de saída será de 1Vpp e que a corrente do circuito será de 1,1A, sendo 0,1A o valor para gasto com componentes do circuito sendo assim:

![primeiro bloco](/Imagens/parte5/Ripper.JPG)
#### Figura 7.

C=I/(f*Vr);
C=1.1/(120*1);
C=9,166667mF

![primeiro bloco](/Imagens/parte5/Ripper1.JPG)

De fato se verifica que quando passar 1A Vr será de aproximadamente 1Vpp.


## Projeto do Regulador.


### Parte 01

Considerando o circuito da figura 01 que representa uma fonte linear com regulador MOSFET, temos o seguinte problema:

![primeiro bloco](/Imagens/parte5/figura1.JPG)
Figura 1.

1- Qual relação entre a tensão de alimentação do ampop e a tensão de saída?

Resposta:
Sabe-se que o ampop tem um limite de saturação, por isso a tensão de saída do ampop esta diretamente relacionada a tensão de alimentação, uma vez que a tensão máxima de saída será levemente menor que a tensão de alimentação do ampop.


2- O que devemos considerar para esse circuito operar como um LDO? Como obter as tensões de alimentação para o AmpOp (VCC e VEE)?

Resposta:

Para que possa operar como LDO a queda de tensão na saída deve ser baixa, geralmente, 0,1V a 0,5V. A tensão de saída está diretamente ligada a tensão de referência e a relação dos resistores, logo Vout=Vref(1+R1/R2).
as características elétricas do ampop devem ser retiradas do DATASHEET e para o amplificador em questão, LM324 a alimentação pode ser de +-16V ou 0 a 32Vcc.
para se obter a tensão desejada se utilizou da tipologia dobrador de tensão, sendo assim a tensão será de VP= (2*12*2^1/2)-(0,7)=33,3V.

3- Utilizando o circuito dobrador de tensão, qual valor de VCC você obtêm para um sinal Vin+ de 12Vrms? Quais problemas apresentam esse circuito? Podemos melhorar?

Primeiramente vamos encontrar o capacitor para este circuito considerando 0,5A de corrente somente para alimentação dos AmpOp, VP 33,3V, f=60Hze Vr=10% de VP.

C=I/(f*Vr);
C=0,5/(60*0,1*33,3);
C=2,5mF

![primeiro bloco](/Imagens/parte5/3vdobrador.JPG)

Nota-se que o valor alcançado está levemente,Vr=3,04 V, abaixo do valor calculado Vr=3,3V. com isso o circuito deve ser melhorado para se obter um valor de tensão mais próximo estável com intuito de diminuir a tensão de ripper na entrada do ampop, sendo este o principal problema.
umas das medidas seria aumentar o valor dos capacitores do dobrador, outra forma seria a inclusão de um potenciômetro em paralelo com o diodo zener o que permitiria a variação da tensão de 0 a 27V.

Outro ponto a se observar é a corrente de pico nos diodos quando o circuito é ligado, está ficou em aproximadamente, 15A, bem abaixo do valor de datashhet do diodo que é de 30A.

![primeiro bloco](/Imagens/parte5/correntedepico.JPG)

### Circuito proposto (02) para a alimentação do AmpOp:

Considere: AmpOp LM324, MOSFET IRF540, VOUT = 15V, IOUT = 1A, vin+ = 12Vrms, vripple pós-retificador =1V, considere as quedas de tensão nos diodos de 0,7V.

![primeiro bloco](/Imagens/parte5/figura2.JPG)

Tensão de saída(Vout) após inclusão de alguns componentes.

![primeiro bloco](/Imagens/parte5/figura2_1.JPG)

observa-se que a tensão Vout está com um pequeno ripper na saída de aproximadamente 20uV.
A alimentação do amplificador pode ser melhorada colocando os capacitores C2 E C3 de maior valor no dobrador de tensão o que diminuirá consideravelmente o ripper, mas com valores cada vez maior o tempo para entrarem regime permanente também aumenta tornando-se elevado demais. outra forma é incluir um transistor com alto ganho E com um pequeno capacitor o que deverá deixar a tesão com menor ripper, além de incluir um potenciômetro em paralelo com D6 para regular a fonte de 0 a 27V.  

### Parte 02 Calculando e dimensionando outros componentes.

![figura3](/Imagens/parte5/figura3.JPG)


a) Para o primeiro bloco (D1, D2 e C1) considere vin+ = 12Vrms, vripple_pós_retificador = 1V e I_carga =1,1A. (Vide roteiro 02)

b) Circuito referência de tensão zener (R1 e D3): Ver roteiro 03. Podemos melhorar esse circuito?

![primeiro bloco](/Imagens/parte5/transistor.JPG)

![primeiro bloco](/Imagens/parte5/questão2.JPG)

### Tensão e Corrente de saida.

![primeiro bloco](/Imagens/parte5/correntediodo.JPG)

Foram escolhidos os transistores PNP 2SA1774 para a fonte de corrente por possuírem um hfe de 300 e com a potência devida pelo circuito.

### Tensão de saída do regulador após inserção dos componentes.

![primeiro bloco](/Imagens/parte5/vout.JPG)

### Tensão de saída do regulador após inserção de uma carga de 15 Ohms para simular uma I=1A.

![primeiro bloco](/Imagens/parte5/ripper_saida.JPG)

Podemos verificar que corrente de saída realmente está próxima a 1A e Vr está em, aproximadamente, 7,5uV. o que permite verificar que a tensão RMS quase não sofreu alteração com a inclusão da carga.

Quais problemas podemos identificar nesta topologia?
Sugestão de melhoria:

O principal problema da fonte de corrente do circuito está em depender do hfe e nas pequenas diferenças características de cada transistor fazendo com que possa haver uma leve variação de tensão VCE.
Uma forma de melhorar o circuito seria usar um potenciômetro em paralelo com o diodo D3 o que permitiria ter um melhor controle sobre a tensão de saída.
