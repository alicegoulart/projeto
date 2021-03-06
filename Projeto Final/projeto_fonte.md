# Instituto Federal de Santa Catarina - Campus Florianópolis Departamento Acadêmico de Eletrônica Curso de Engenharia Eletrônica

Alunos:

* Luís André G. da Silva


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

1-Transformador de 220/12V;

2-Diodos 1N4007;

3-Diodos Zener DTDZV27 e EDZV11B;

4-Capacitores de 2,5mF e 9,1mF;

5-Transistores tipo BJT 2n3904 e 2SA1774;

6-Transistores tipo MOS 2N7002 e IRF540;

7-Aplificadores operacionais LM324;

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
Sendo assim, inicialmente, os seguintes dados abaixo foram especificados e se concluiu que será preciso  um transformador com relação de transformação de 220v para 12v; corrente máxima de saída de 2 A; e frequência de 60Hz. para o pior caso quando a tensão de entrada estiver em 198V ou 242V. conforme especificado para este projeto.

![primeiro bloco](/Imagens/parte5/transformador.JPG)
#### Figura 3.

Conforme já esperado a tensão de saída ficou em 12V RMS e 17,05V de pico.

### Projeto do retificador

![tensaomaxeficmedcarga220](/Imagens/parte2/ondacompletacomderivacao.JPG)
#### Figura 4.

Um circuito retificador, ou simplesmente retificador, corresponde aos circuitos elétricos de tensão elaborados para a conversão de corrente alternada em corrente de contínua .
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
para a filtragem foi adotado que a tensão de Ripper de saída será de 1Vpp e que a corrente do circuito será de 1,1A, sendo 0,1A o valor para gasto com componentes do circuito, sendo assim:

![primeiro bloco](/Imagens/parte5/ripper.JPG)
#### Figura 7.

C=I/(f*Vr);

C=1.1/(120*1);

C=9,166667mF

![primeiro bloco](/Imagens/parte5/ripper1.JPG)
#### Figura 8.


De fato se verifica que quando passar 1A Vr será de aproximadamente 1Vpp.


## Projeto do Regulador.


### Parte 01

Considerando o circuito da figura 01 que representa uma fonte linear com regulador MOSFET, temos o seguinte problema:

![primeiro bloco](/Imagens/parte5/figura1.JPG)
#### Figura 9.

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
#### Figura 10.

Nota-se que o valor alcançado está levemente, Vr=3,04 V, abaixo do valor calculado Vr=3,3V. Com isso, o circuito deve ser melhorado para se obter um valor de tensão mais estável com intuito de diminuir a tensão de ripper na entrada do ampop, sendo este o principal problema.
umas das medidas seria aumentar o valor dos capacitores do dobrador, outra forma seria a inclusão de um potenciômetro em paralelo com o diodo zener o que permitiria a variação da tensão de 0 a 27V.

Outro ponto a se observar é a corrente de pico nos diodos quando o circuito é ligado, está ficou em aproximadamente, 15A, bem abaixo do valor de datashhet do diodo que é de 30A. este fato é importante, pois se houver exagerada elevação dos capacitores a corrente de pico ficará com valor elevado podendo vir a queimar os diodos.

![primeiro bloco](/Imagens/parte5/correntedepico.JPG)
#### Figura 11.

### Circuito proposto (02) para a alimentação do AmpOp:

Considere: AmpOp LM324, MOSFET IRF540, VOUT = 15V, IOUT = 1A, vin+ = 12Vrms, vripple pós-retificador =1V, considere as quedas de tensão nos diodos de 0,7V.

![primeiro bloco](/Imagens/parte5/figura2.JPG)
#### Figura 12.


Tensão de saída(Vout) após inclusão de alguns componentes.

![primeiro bloco](/Imagens/parte5/figura2_1.JPG)
#### Figura 13.

Observa-se que a tensão Vout está com um pequeno ripper na saída de aproximadamente 20uV.
A alimentação do amplificador pode ser melhorada colocando os capacitores C2 E C3 de maior valor no dobrador de tensão o que diminuirá consideravelmente o ripper, mas com valores cada vez maior o tempo para entrarem regime permanente também aumenta tornando-se elevado demais. outra forma é incluir um transistor com alto ganho E com um pequeno capacitor o que deverá deixar a tesão com menor ripper, além de incluir um potenciômetro em paralelo com D6 para regular a fonte de 0 a 27V.  

### Parte 02 Calculando e dimensionando outros componentes.

![figura3](/Imagens/parte5/figura3.JPG)
#### Figura 15.
a) Para o primeiro bloco (D1, D2 e C1) considere vin+ = 12Vrms, vripple_pós_retificador = 1V e I_carga =1,1A. (Vide roteiro 02)

b) Circuito referência de tensão zener (R1 e D3): Ver roteiro 03. Podemos melhorar esse circuito?

![primeiro bloco](/Imagens/parte5/transistor.JPG)
#### Figura 16.

![primeiro bloco](/Imagens/parte5/questão2.JPG)
#### Figura 17.

### Tensão e Corrente de saida.

![primeiro bloco](/Imagens/parte5/correntediodo.JPG)
#### Figura 18.

Foram escolhidos os transistores PNP 2SA1774 para a fonte de corrente por possuírem um hfe de 300 e com a potência devida pelo circuito.

### Tensão de saída do regulador após inserção dos componentes.

![primeiro bloco](/Imagens/parte5/vout.JPG)
#### Figura 19.

### Tensão de saída do regulador após inserção de uma carga de 15 Ohms para simular uma I=1A.

![primeiro bloco](/Imagens/parte5/ripper_saida.JPG)
#### Figura 20.

Podemos verificar que corrente de saída realmente está próxima a 1A e Vr está em, aproximadamente, 7,5uV. o que permite verificar que a tensão RMS quase não sofreu alteração com a inclusão da carga.

Quais problemas podemos identificar nesta topologia?
Sugestão de melhoria:

O principal problema da fonte de corrente do circuito está em depender do hfe e nas pequenas diferenças características de cada transistor fazendo com que possa haver uma leve variação de tensão VCE.
Uma forma de melhorar o circuito seria usar um potenciômetro em paralelo com o diodo D3 o que permitiria ter um melhor controle sobre a tensão de saída.

## Parte 03

Adicionando um circuito de proteção de sobre corrente ao regulador linear.

1-Primeiramente reflita e pesquise sobre o que é sobrecorrente?

De acordo com os site https://brainly.com.br/sobrecorrente. Sobrecorrente  é definida como sendo qualquer corrente elétrica que flui por um equipamento com magnitude acima da qual o equipamento foi projetado para funcionar. As sobrecorrentes podem ser sob a forma de uma sobrecarga ou curto-circuito.

2-Quais os impactos neste circuito?

Uma elevada corrente num circuito certamente queimará alguns componentes podendo ser os diodos, transistores, resistores ou até mesmo o transformador que outrora fora projetado para um limite máximo de 2A, mas com a concepção feita no circuito com proteção de sobrecorrente a queima dificilmente ocorrerá, uma vez que foi feito um circuito para proteção da fonte e caso haja elevação na carga ou um curto circuito na saída da fonte está ira diminuir a tensão de saída para que não aconteça nenhum problema.

3-O que deve fazer um circuito de proteção de sobrecorrente?
Assim como diz a nomenclatura o circuito deve ser capaz de atuar quando a corrente na saída seja maior que a projetada para o circuito seja por sobrecarga ou por curto circuito.
Para o projeto em questão a fonte foi projetada para 15W, 1A tendo seu limite de atuação quando a corrente do circuito ultrapassar 1,2A.

4- O que é a proteção foldback? Pesquise as topologias disponíveis, caso deseja-se fazer um circuito LDO, o que devemos levar
em consideração para o regulador?

De acordo com o site https://qastack.com.br/electronics/2931/what-is-foldback-short-circuit-protection-in-a-power-supply foldback é o método usado em fontes de alimentação para protegê-las de situações atuais, como curto-circuito na saída com um fio ou conexão de muitos equipamentos à fonte de alimentação.

Com a corrente normal (lado alto) limitando, há uma tampa de corrente dura que o suprimento é limitado para protegê-lo. À medida que a resistência da carga se aproxima de 0, a corrente é limitada a um valor fixo e a tensão começa a cair. Isso pode causar uma grande quantidade de dissipação de energia no suprimento.

Com a proteção foldback, quando a tensão cai, o limite de corrente também cai de maneira bastante linear. Isso fornece proteção mais segura contra curtos-circuitos, pois um curto-circuito "muito ruim" resultará em muito pouco consumo de corrente, para que o suprimento não fique sentado assando na corrente máxima.

### Análise final do regulador linear.

Em ultimo instante foi realizada a implementação de um sistema de proteção da fonte colocando-se um resistor shunt subtrator para elevar a queda de tensão na saída do AMPOP.
sabendo-se que a tensão VDS é aproximadamente 2,154V houve a necessidade de se fazer o cálculo do divisor de tensão na saída do circuito subtrator para que o transistor M2 se comportasse como uma chave e isso para isso a tensão VGS deverá ser valor que a tensão VDS.
Em primeiro momento foi escolhido um resistor comercial Shunt de 51m ohms e se deseja que a corrente de corte seja de 1,2A, além de ser querer uma tensão de aproximadamente 4,4V sobre o divisor de tensão, sendo assim temos.

Vshunt=1,2*51^10-3

Vshunt=61,2mV

Ganho do subtrator=4,4/(0,0612)
Ganho do subtrator=71,89

Após análise do ganho Podemos optar por uma imensa gama de resistores que possuam a devida relação e sabendo que a tensão de saída do subtrator será de Vout=R10/R9(Va-vb) foram adotados os resistores de R9=10K e R10=720K.

![primeiro bloco](/Imagens/parte5/esquemafinal.JPG)
#### Figura 21.



![primeiro bloco](/Imagens/parte5/final.JPG).
#### Figura 22.


Após implementação de todos os componentes consegue-se observar que o objetivo foi cumprido a tensão de saída está muito próxima aos 15v desejados a corrente sobre a carga é de aproximadamente 1A e a correntes sobre os diodos ficam bem abaixo dos 30A, valor máximo sobre estes.
Ressalto que o regulador poderia ser aperfeiçoado com potenciômetro podendo ser sobre o diodo D3 ou a troca do resistor R10 por esse.
