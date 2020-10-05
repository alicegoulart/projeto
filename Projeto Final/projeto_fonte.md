##### Instituto Federal de Santa Catarina - Campus Florianópolis Departamento Acadêmico de Eletrônica Curso de Engenharia Eletrônica

Alunos:

*Luís André G. da Silva


# Objetivos
Integração dos blocos de uma fonte linear.

## Introdução
Neste roteiro iremos integrar os circuitos estudados anteriormente, para isso, revise os conceitos
de reguladores LDO e tenha em mãos os roteiros anteriores.

### Parte 01

Considerando o circuito da figura 01 que representa uma fonte linear com regulador MOSFET, temos o seguinte problema:

![primeiro bloco](/Imagens/parte5/figura1.JPG)
Figura 1.

1- Qual relação entre a tensão de alimentação do ampop e a tensão de saída?

Sabe-se que o ampop tem um limite de saturação, por isso a tensão de saída do ampop esta diretamente relacionada a tensão de alimentação, uma vez que a tensão máxima de saída será levemente menor que a tensão de alimentação do ampop.


2- O que devemos considerar para esse circuito operar como um LDO? Como obter as tensões de alimentação para o AmpOp (VCC e VEE)?


Para que possa operar como LDO a queda de tensão na saída deve ser baixa, geralmente, 0,1V a 0,5V. A tensão de saída está diretamente ligada a tensão de referência e a relação dos resistores, logo Vout=Vref(1+R1/R2).
as características elétricas do ampop devem ser retiradas do DATASHEET e para o amplificador em questão, LM324 a alimentação pode ser de +-16V ou 0 a 32Vcc.
para se obter a tensão desejada se utilizou da tipologia dobrador de tensão, sendo assim a tensão será de VP= (2*12*2^1/2)-(0,7)=33,3V.

3- Utilizando o circuito dobrador de tensão, qual valor de VCC você obtêm para um sinal Vin+ de 12Vrms? Quais problemas apresentam esse circuito? Podemos melhorar?

Nota-se que o valor alcançado está levemente acima do desejado, com isso o circuito deve ser melhorado para se obter um valor de tensão mais próximo do desejado, além de diminuir a tensão de ripper na entrada do ampop sendo este o principal problema.

### Circuito proposto (02) para a alimentação do AmpOp:

![primeiro bloco](/Imagens/parte5/figura2.JPG)

Vamos projetar esse circuito?
Considere: AmpOp LM324, MOSFET IRF540, VOUT = 15V, IOUT = 1A, vin+ = 12Vrms, vripple_pós_retificador =1V, considere as quedas de tensão nos diodos de 0,7V.

A alimentação do amplificador pode ser melhorada colocando um capacitor de maior valor nos dobrador de tensão o que diminuirá consideravelmente o ripper, mas com valores cada vez maior o tempo para entrarem regime permanente também aumenta tornando-se elevado demais. outra forma é incluir um transistor com alto ganho com um pequeno capacitor o que deverá deixar a tesão com menor ripper.  

### Parte 02 Calculando e dimensionando os componentes.

![primeiro bloco](/Imagens/parte5/figura3.JPG)


a) Para o primeiro bloco (D1, D2 e C1) considere vin+ = 12Vrms, vripple_pós_retificador = 1V e I_carga =1,1A. (Vide roteiro 02)

b) Circuito referência de tensão zener (R1 e D3): Ver roteiro 03. Podemos melhorar esse circuito?

![primeiro bloco](/Imagens/parte5/transistor.JPG)

![primeiro bloco](/Imagens/parte5/questão2.JPG)

### Tensão e Corrente diodo EDZV11B.

![primeiro bloco](/Imagens/parte5/correntediodo.JPG)

Foram escolhidos os transistores PNP 2SA1774 para a fonte de corrente por possuírem um hfe de 300 e com a potência devida pelo circuito.

### Tensão de saída do regulador após inserção dos componentes.

![primeiro bloco](/Imagens/parte5/vout.JPG)

Quais problemas podemos identificar nesta topologia?
Sugestão de melhoria:

O principal problema da fonte de corrente do circuito está em depender do hfe e nas pequenas diferenças características de cada transistor fazendo com que possa haver uma leve variação de tensão VCE.
Uma forma de melhorar o circuito seria usar um espelho de corrente com compensação de base ou o espelho de Wilson entre outras. vale destacar que estes modelos podem ser feitos com MOS o que melhora o circuito.
