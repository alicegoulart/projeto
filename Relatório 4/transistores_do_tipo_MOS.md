# Objetivos
## Estudo das características e aplicações de circuitos com transistores do tipo MOS.
### Introdução
Para este experimento, será empregado o transistor 2N7002.
Primeiro passo faça uma busca nos fabricantes e verifique o modelo SPICE do
componente e compare no mínimo dois fabricantes.

R: Após verificação em alguns sites na internet foi de fácíl acesso o Datasheet do componente 2N7002, no entanto há poucos modelos spice para comparação. Dos encontrados um é da Diodes Incorporated e outro da Texas instruments este ultimo e um componente equivalente.
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

![rdsteorico](/Imagens/parte4/curva2.JPG)

Quando comparadas as curvas encontradas na simulação com as do datasheet se percebe uma sigficativa diferença, provavelmente, porque o modelo spice formula o componente de forma generalizada sem levar em consideração muitos fatores críticos, sendo um deles a potência dissipada. Desta forma há expressamente diferença nas correntes de saturação.

4-Utilizando a curva ID x VDS obtenha os valores RDS e compare com os valores teóricos.

![rdsteorico](/Imagens/parte4/RDS2.JPG)

Os valores encontrados são muito discrepantes em relação aos teóricos e mais uma vez acredito que seja pela analise superficial do modelo spice.


### Parte 02: Polarização de transistores do tipo NMOS:

Simule o circuito da Figura 01, com os seguintes valores: VCC = 9,0 V, R3 = R4 = 10 kΩ, R1 = 2 kΩ, R2 = 1 kΩ.

![rdsteorico](/Imagens/parte4/modelo.JPG)

1- Em qual região o transistor se encontra polarizado?
![resolução teórica](/Imagens/parte4/mos.jpg)

Conforme verificado na análise teórica pode-se observar que o transistor está na região de saturação.


2- Compare os resultados obtidos com os valores teóricos.

![rdsteorico](/Imagens/parte4/mossaturação.JPG)

Com a análise da simulação pode-se verificar que os valores de correntes e tensões estão bem próximas e fica ratificado que o transistor está na região de saturação.

### Parte 03: Espelho de corrente com transistores do tipo NMOS:

Simule o circuito da Figura 02, com os seguintes valores: R1 = 1,0 kΩ, VCC= 10,0 V. Para R2,variando entre 0 e 100kΩ.

![espelho de corrente ](/Imagens/parte4/espelho.JPG)

1 Explique o funcionamento deste circuito comparando as corrente ID1 e ID2.

2 Variando a resistência R2, trace a curva ID2 x V2.

3 Obtenha o máximo valor de R2 para o espelho de corrente funcionar corretamente.

4 Compare os resultados obtidos com a teoria.




### Parte 04: Inversor com transistor do tipo NMOS (NMOS Inverter):

Simule o circuito da Figura 03, com os seguintes valores: R1 = 10 kΩ e VCC= 5,0 V.
VIN = forma de onda quadrada com 1 kHz e amplitude de 5,0 Vpp (sem valor negativo, ou seja de 0 a 5V ).

![inversor com MOS ](/Imagens/parte4/inversorcommos.JPG)

1 Compare as formas de onda de entrada e de saída.

2 Obtenha o valor de RDS para esse transistor para esta 3ondição de operação.

4 Caso sinal de entrada tenha(VIN) a amplitude reduzida para 2,5 V, qual o valor de RDS?

5 Compare os resultados obtidos com a teoria.
