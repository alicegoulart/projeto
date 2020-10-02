# Instituto Federal de Santa Catarina - Campus Florianópolis Departamento Acadêmico de Eletrônica Curso de Engenharia Eletrônica

## Alunos:  Luís André G. da Silva

## Relatório sobre retificadores de meia onda.

# objetivos.

##  Os objetivos desta aula são:

1- Estudar retificadores de meia onda, onda completa em ponte e onda completa com
derivação central, medindo as principais grandezas nos circuitos montados;

2- Verificar o funcionamento dos retificadores;

3- Implementar filtros capacitivos nos retificadores e verificar seu funcionamento com a
presença destes elementos.
## Em todas as montagens, o resistor de carga Ro será de 270 Ω x 5 W.

### Parte 01_a: Circuito Retificador de Meia Onda.

1- Simule o circuito do retificador de meia onda mostrado na Figura 1, inicialmente sem capacitor, anotando os valores na Tabela 1.

![meia onda](/Imagens/parte2/meiaonda.JPG)
Fonte:internet.

### Resultados.
 ### tensão de pico, eficaz e média no secundário.

![tensão de pico no secundário](/Imagens/parte2/tensaopicoeficazmediasecundario.JPG)

### tensão de pico, eficaz e média na carga.

  ![tensão de pico no secundário](/Imagens/parte2/tensaomaxmedcarga2.JPG)

2- Em seguida adicione um capacitor eletrolítico de 330 μF na saída do retificador, conforme mostrado
na Figura 2. Anote os valores solicitados na Tabela 1.

![tensão de pico no secundário](/Imagens/parte2/meiaondacomcapacitor.JPG)

Fonte:internet.

### Resultados.

### tensão de pico, eficaz e média na carga com capacitor de 330u.
![tensaomaxeficmedcarga330](/Imagens/parte2/tensaomaxeficmedcarga330u.JPG)


3- Substitua o capacitor eletrolítico de 330 μF por um de 2200 μF e observe a forma da tensão de saída
do circuito, meça as grandezas solicitadas e anote na Tabela 1.
### Resultados.

### tensão de pico, eficaz e média na carga com capacitor de 2200u.
![tensaomaxeficmedcarga330](/Imagens/parte2/tensaomaxeficmedcarga2200u2.JPG)

### Resultados gerais.
![tabela1](/Imagens/parte2/tabela_1.JPG)

##  Parte 01_b: Circuito Retificador de Meia Onda
Adicione um circuito para medir a corrente. Lembre-se na aula anterior foi estudados os circuitos com Ampop que são utilizados para medir a corrente em um circuito.

1-Pesquise sobre resistores shunt, respondendo as perguntas:
O que são?

Em eletrônica, um shunt é um dispositivo que cria um caminho de baixa resistência para a corrente elétrica, permitindo que ela passe em outro ponto do circuito. A origem do termo está no verbo 'desviar' que significa virar-se ou seguir um caminho diferente.
fonte: <https://en.wikipedia.org/wiki/Shunt_(electrical)>.

2- Como determinar o valor do resistor para o circuito?


Uma resistência shunt tem um valor muito pequeno, mas precisa de resistência e pode ser utilizado para determinar a corrente através de uma carga . O resistor é colocado em série com a carga . A resistência é muito pequena , de modo que a maior parte da corrente passa para a carga . A corrente pode ser determinada por medição da queda de tensão através da resistência de derivação em seguida, utilizando a lei de Ohm para calcular a corrente através do shunt .

1-Encontre o máximo de corrente que vai passar pelo resistor. Na maioria dos casos isso será determinado pelas necessidades atuais da carga.

2-Encontre o valor do resistor shunt quando você sabe a corrente máxima . Isso não é tão simples como parece. Se a resistência for demasiado alta , a queda de tensão através da resistência será demasiado elevado , tendo o poder de distância a partir da carga . Se a resistência for muito baixa , a tensão através da resistência de derivação é demasiado baixo , fazendo com que a medição seja menos precisa . Como regra geral , evitar a queda mais do que 1 por cento de tensão através da resistência de derivação . Por exemplo , se a corrente de carga máxima é de 1A a 10 volts , não mais do que 0,1 V deve ser eliminada através da resistência de derivação em corrente máxima . O valor do resistor shunt deve ser R = Vs /I = .1V/1A = 0,1 ohm, onde Vs é a queda de tensão através do resistor shunt .

3-Calcule a dissipação de energia necessária para a resistência . O resistor de derivação deve ser capaz de passar a corrente máxima, para a tensão nominal sem sobreaquecer ou queimando -se . Para calcular a potência em watts , multiplique a corrente máxima ao quadrado pela resistência shunt P = I x I x R. Para o exemplo no passo 2, a dissipação de potência será P = 1 x 1 x 0,1 = 0,1 Watt . < Br >

fonte:<http://ptcomputador.com/Ferragens/computer-drives-storage/49366.html#:~:text=Como%20regra%20geral%20%2C%20evitar%20a,R%20%3D%20Vs%20%2FI%20%3D%20>
