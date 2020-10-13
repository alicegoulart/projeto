# Instituto Federal de Santa Catarina - Campus Florianópolis Departamento Acadêmico de Eletrônica Curso de Engenharia Eletrônica

## Aluno: Luís André G. da Silva.

## Relatório sobre transistores tipo MOS.

# Objetivos

## Estudo das características e aplicações de circuitos com transistores do tipo MOS.

### Introdução
Para este experimento, será empregado o transistor 2N7002.
Primeiro passo faça uma busca nos fabricantes e verifique o modelo SPICE do
componente e compare no mínimo dois fabricantes.

R: Após verificação em alguns sites na internet foi de fácíl acesso o Datasheet do componente 2N7002, no entanto há poucos modelos spice para comparação. Dos encontrados um é da Diodes Incorporated e outro da Texas instruments este último e um componente equivalente.
há semelhanças entre os modelos como tensão,60V, tipo N, mas também há grades diferenças como potencia, RDS, corrente de saturação entre outras.

### Parte 01: Determinar os parâmetros do transistor:
1- Quais os parâmetros L, W, uo, Cox, VA e Vt?
R: Realizada analise do Datasheet no transistor da Diodes Incorporated pode-se verificar algumas informações, mas não conseguir verificar os itens solicitados, porém se analisando o modelo spice encontrado pode-se obter algumas informações, sendo:
L=10u
W=10u
Kp=u0*Cox=0,4654 A/V^2
Vt0=2,154 V
Va= Não encontrado.

2-Calcule o valor de RDS para as tensões VGS de 2V, 3V, 4V, 5V e 10V.

![rdsteorico](/Imagens/parte4/rdsteorico.JPG)

Aqui já se percebe algo estranho com o valor de RDS quando comparado ao valor do datasheet da Diodes Incorporated, uma vez que no datasheet quando valor de Vgs é de 5V o valor de Rds deve ser de 7,5 ohms já o valor de Rds encontrado na fórmula ficou em 0,755 Omhs,ou seja, muito menor que os 7,5 Ohms.

3-Quais as tensões máximas de operação deste componente?

4-Obtenha as curvas ID x VDS para esse componente para as tensões VGS de 2V, 3V, 4V, 5V e 10V e compare os resultados com as curvas presentes no Datasheet.

![curva2](/Imagens/parte4/curva2.JPG)

Quando comparadas as curvas encontradas na simulação com as do datasheet se percebe uma significativa diferença, provavelmente, porque o modelo spice formula o componente de forma generalizada sem levar em consideração muitos fatores críticos, sendo um deles a potência dissipada. Desta forma há expressamente diferença nas correntes de saturação.

4-Utilizando a curva ID x VDS obtenha os valores RDS e compare com os valores teóricos.

![rds2](/Imagens/parte4/RDS2.JPG)

Os valores encontrados são muito discrepantes em relação aos teóricos e mais uma vez acredito que seja pela analise superficial do modelo spice.


### Parte 02: Polarização de transistores do tipo NMOS:

Simule o circuito da Figura 01, com os seguintes valores: VCC = 9,0 V, R3 = R4 = 10 kΩ, R1 = 2 kΩ, R2 = 1 kΩ.

![modelo](/Imagens/parte4/modelo.JPG)

1- Em qual região o transistor se encontra polarizado?
![resolução teórica](/Imagens/parte4/mos.jpg)

Conforme verificado na análise teórica pode-se observar que o transistor está na região de saturação.


2- Compare os resultados obtidos com os valores teóricos.

![MOS Saturado](/Imagens/parte4/mossaturação.JPG)

Com a análise da simulação pode-se verificar que os valores de correntes e tensões estão bem próximas e fica ratificado que o transistor está na região de saturação.

### Parte 03: Espelho de corrente com transistores do tipo NMOS:

Simule o circuito da Figura 02, com os seguintes valores: R1 = 1,0 kΩ, VCC= 10,0 V. Para R2,variando entre 0 e 100kΩ.

![espelho de corrente ](/Imagens/parte4/espelho.JPG)

1- Explique o funcionamento deste circuito comparando as corrente ID1 e ID2.

Resposta:

A configuração mostra o transistor Q1 com os polos Gate e Dreno curto-circuitados desta forma Q1 está funcionando como um diodo e ID1 é a corrente que passa sobre o resistor R1. Também conhecida como IRef.
IRef pode ser encontrada da seguinte forma IRef=(VCC-VGS)/R
A corrente que transita sobre o circuito de Q1 gera uma tensão VGS , essa tensão polariza o transistor Q2. A corrente ID2 será a mesma corrente que transita em Q1, logo, ID1= ID2, ou seja, é um espelho de corrente, pois a relação entre IRef. e ID2 está nas características dos transistores Kn’,W,L. como transistores devem ser iguais sendo Q1 um conversor de corrente para tensão e Q2 um conversor de tensão para corrente podemos confirmar que ID1=ID2.


2- Variando a resistência R2, trace a curva ID2 x V2.

![inversor com MOS ](/Imagens/parte4/0a100k.JPG)
Verifica-se que a corrente encontrada é de 7,638mA muito próxima ao valor calculado de 7,664mA.

3 Obtenha o máximo valor de R2 para o espelho de corrente funcionar corretamente.

![inversor com MOS ](/Imagens/parte4/teoricomos.jpg)

de acordo com o descrito o valor máximo de R2 será de 1023 Ohms, pois desta forma o transistor Q2 permanece tendo o valor mínimo de tensão Vt=2,154 V para condução.


4 Compare os resultados obtidos com a teoria.

![inversor com MOS ](/Imagens/parte4/zeroohms.JPG)

Após analise de simulação se verificou que o valor encontrado ficou próximo ao valor teórico sendo esse de 840 Ohms frente aos 1023 Ohms teórico.


### Parte 04: Inversor com transistor do tipo NMOS (NMOS Inverter):

Simule o circuito da Figura 03, com os seguintes valores: R1 = 10 kΩ e VCC= 5,0 V.
VIN = forma de onda quadrada com 1 kHz e amplitude de 5,0 Vpp (sem valor negativo, ou seja de 0 a 5V ).

![inversor com MOS ](/Imagens/parte4/inversorcommos.JPG)

1 Compare as formas de onda de entrada e de saída.

![inversor MOS](/Imagens/parte4/curvainveroramos.JPG)

2 Obtenha o valor de RDS para esse transistor para esta condição de operação e caso o sinal de entrada tenha(VIN) a amplitude reduzida para 2,5 V, qual o valor de RDS?


![inversor MOS](/Imagens/parte4/cálculords.jpg)


4 Compare os resultados obtidos com a teoria.
![inversor MOS](/Imagens/parte4/resultado1.jpg)

![inversor MOS](/Imagens/parte4/resultado1.jpg)

Conforme já esperando a tensão de entrada praticamente não se modificou ficando em 4,9999V. Desta forma podemos crer que resistência RDS é muito pequena quando comparada ao resistor R1. Com isso, a queda de tensão é mínima para ambos os casos, além de que o transistor parece operar apenas como chave e fazendo o processo de inversão da tensão de entrada.
