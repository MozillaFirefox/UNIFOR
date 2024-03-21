# UNIFOR Lista 1
**Nome**: Aaron Magno Campos Nogueira
**Disciplina**: Raciocínio lógico algorítmico

## Lista de exercícios 01

### Exercício 01 (1 ponto)
Represente, em fluxograma e pseudocódigo, um algoritmo para determinar se um número inteiro e positivo é par ou impar.

#### Fluxograma (0,25 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite um número:}}
B --> C[\numero\]
C --> D{numero >= 0}
D --FALSE--> E[O número não é positivo!]
D --TRUE--> F[resto = numero % 2]
E --> Z([FIM])
F --> G{resto == 0}
G --FALSE--> H{{O número é impar!}}
G --TRUE--> I{{O número é par!}}
H --> Z
I --> Z
```

#### Pseudocódigo (0,5 ponto)
```
1  ALGORTIMO verifica_par_impar
2  DECLARE numero, resto: INTEIRO
3  ESCREVA "Digite um número: "
4  INICIO
4  LEIA numero
5  SE numero >= 0 ENTAO                  // verifica se o inteiro é positivo
6    resto = numero % 2                 // calcula o resto da divisão por 2
7    SE resto == 0 ENTAO                // verifica se o resto é igual a zero
8      ESCREVA "O número é par!"
9    SENAO
10     ESCREVA "O número é impar!"
11   FIM_SE
11  SENAO                                // caso inteiro for negativo (condição linha 5)
12    ESCREVA "O número deve ser postivo!"
13  FIM_SE
13 FIM
```

#### Teste de mesa (0,25 ponto)
| numero | numero >= 0 | resto | resto == 0 | Saída |
| -- | -- | -- | -- | -- | 
| -1 | F |   |   | "O número deve ser postivo!" |
| 0  | V | 0 | V | "O número é par!" |
| 13 | V | 1 | F | "O número é impar!" |
| 30 | V | 0 | V | "O número é par!" |

## Exercício 02 (3 pontos)
Represente, em fluxograma e pseudocódigo, um algoritmo para calcular o novo salário de um funcionário. 
Sabe-se que os funcionários que recebem atualmente salário de até R$ 500 terão aumento de 20%; os demais terão aumento de 10%.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite seu salário}}
B --> C[\salariovelho\]
C --> D{salariovelho <0}
D --V--> E[salarionovo = 0]
D--F--> F{salariovelho =<500}
F--V-->G[salarionovo = salariovelho*1.2]
F--F-->H[salarionovo = salariovelho*1.1]
E-->J[\salarionovo\]
G-->J
H-->J
J-->K{{"O seu novo salário é "salarionovo}}
K-->L([FIM])

```

#### Pseudocódigo (1.0 ponto)

```
1 ALGORITMO salarionovo
2 DECLARE salariovelho, salarionovo:REAL
3 ESCREVA "Digite seu salário"
4 INICIO
5 LEIA salariovelho
6 SE salariovelho < 0 ENTAO
7    salarionovo = 0
8 SENAO
9   SE salariovelho =< 500 ENTAO
10  salarionovo = salariovelho*1.2
11  SENAO salarionovo = salariovelho*1.1
12  FIM_SE
13FIM_SE
14LEIA salarionovo
15ESCREVA "O seu novo salário é" salarionovo 
16FIM_ALGORITMO
```

#### Teste de mesa (1.0 ponto)
| salariovelho | salariovelho < 0 | salario velho =< 500 | salarionovo | Saída |
| -- | -- | -- | -- | -- | 
| -1 | T |   | 0  | "O seu novo salário é 0" |
| 500  | F | T | 600 | "O seu novo salário é 600" |
| 1000 | F | T | 1100 | "O seu novo salário é 1100" |



## Exercício 03 (3 pontos)
Represente, em fluxograma e pseudocódigo, um algoritmo para calcular a média aritmética entre duas notas de um aluno e mostrar sua situação, que pode ser aprovado ou reprovado.

#### Fluxograma (1 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{"Digite sua primeira nota"}}
B-->C[\nota1\]
C-->D{nota1 > 10 or nota1<0}
D--T--> E{{"Nota inválida"}}
D--F--> F{{Digite sua segunda nota}}
F--> G[\nota2\]
G--> H{nota2> 10 or nota2<0}
H--T--> I{{"Nota inválida"}}
H--F-->J[nota1 + nota2=media*2]
J--> L[\media\]
L--> M{media <7}
M--T--> N{{"Você foi reprovado"}}
M--F--> O{{"Você foi aprovado"}}
E-->P([FIM])
I-->P
N-->P
O-->P
```

#### Pseudocódigo (1 ponto)

```
1 ALGORITMO Contaaprovações
2 DECLARE nota1,nota2,média:REAL
3 ESCREVA "Digite sua primeira nota"
4 INICIO
5 LEIA nota1
6 SE nota1 > 10 or nota1 <0 ENTAO
7   ESCREVA"Nota inválida"
8 SENAO
9   ESCREVA "Digite sua segunda nota" 
10  LEIA nota2
11  SE nota2 > 10 or nota2 <0 ENTAO
12     ESCREVA"Nota inválida"
13  SENÃO
14   media*2 = nota1+nota2
15   FIM_SE
16FIM_SE
17 LEIA media
18 SE media < 7 ENTAO
19 ESCREVA "Você foi reprovado"
20 SENAO
21 ESCREVA "Você foi aprovado"
22 FIM_SE
23 FIM_ALGORITMO
```

#### Teste de mesa (1 ponto)
| nota1 | nota2 | média | Saída |
| -- | -- | -- | -- | 
| -1 |  |      | "Nota inválida" |
| 7  | -1 |  |   "Nota inválida" |
| 7 | 7 | 7 | "Você foi aprovado" | 
| 7 | 6.5 | 6.75 | "Você foi reprovado" | 
## Exercício 04 (3 pontos)
Represente, em fluxograma e pseudocódigo, um algoritmo que, a partir da idade do candidato(a), determinar se pode ou não tirar a CNH. 
Caso não atender a restrição de idade, calcular quantos anos faltam para o candidato estar apto.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{"Digite sua idade aqui"}}
B-->C[\idade\]
C-->D{idade < 18}
D--T-->E[18 -idade=faltam]
D--F-->F{{Você pode tirar a CNH}}
E-->G[\faltam\]
G-->H{{"Faltam faltam ano(s) para você poder tirar a CNH"}}
F-->I([FIM])
H-->I
```

#### Pseudocódigo (1.0 ponto)

```
1 ALGORITMO CNH
2DECLARE:idade,faltam :INTEIRO
3ESCREVA "Digite sua idade aqui"
4INICIO
5LEIA idade
6SE idade <18 ENTAO
7 18-idade=faltam
8 LEIA faltam
9 ESCREVA "Faltam"faltam"ano(s) para você poder tirar a CNH"
10SENAO
11ESCREVA"Você pode tirar a CNH"
12 FIM_SE
13FIM_ALGORITMO

```

#### Teste de mesa (1.0 ponto)

| idade | idade < 18 | faltam | Saída |
| -- | -- | -- | -- | 
| 18 | F |      | "Você pode tirar a CNH" |
| 17  | T | 1 |   "Faltam 1 ano(s) para você poder tirar a CNH" |
| -1 | T | 19 | "Faltam 19 anos para você poder tirar a CNH" | 


# UNIFOR Lista 2
**Nome**: Aaron Magno Campos Nogueira.
**Disciplina**: Raciocínio lógico algorítmico

## Exercício exemplo
Represente, em fluxograma e pseudocódigo, um algoritmo para calcular o adicional de salário de funcionário por cargo de uma empresa fictícia. Sabe-se que os funcionários de cargo técnico receberão reajuste de 50%, cargo de gerência, um reajuste de 30% e demais, um reajuste de 10%. 

#### Fluxograma
```mermaid
flowchart TD
A([INICIO]) --> B{{Digite o salário e profissão}}
B --> C[\sal, prof\]
C --> D{prof == 'Tecnico'}
D --FALSE--> E{prof == 'Gerente'}
D --TRUE--> F[sal_reaj = 1.5 * sal]
E --FALSE--> H[sal_reaj = 1.1 * sal]
E --TRUE--> G[sal_reaj = 1.3 * sal]
G --> I([FIM])
F --> I
H --> J{{'Salário Reajustado = ', sal_reaj}}
J --> I
```

#### Pseudocódigo
```
1  ALGORITMO calReajuste
2  DECLARE  sal, sal_reaj: real, prof: caractere
3  INICIO
4  LEIA sal, prof
5  ESCOLHA
6   CASO prof == “Técnico”		// caso 1
7     sal_reaj ← 1.5 * sal
8   CASO prof = “Gerente”		// caso 2
9     sal_reaj ← 1.3 * sal
10  SENÃO
11    sal_reaj ← 1.1 * sal
12 FIM_ESCOLHA
13 ESCREVA “Salário Reajustado = “, sal_reaj
14 FIM
```

#### Teste
| sal | prof | prof == “Técnico” | prof = “Gerente” | sal_reaj | Saída |
| -- | -- | -- | -- | -- | -- |
| 1000 | Técnico | V | F | 1500 | “Salário Reajustado = 1500“ |
| 2000 | Gerente | F | V | 2600 | “Salário Reajustado = 2600“ |
| 9000 | Diretor | F | F | 9900 | “Salário Reajustado = 9900“ |

## Lista de exercícios 02

### Exercício 01 (2.5 pontos)
Calcule a média de quatro números inteiros dados.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite quatro números inteiros}}
B-->C[\numero1,numero2,numero3,numero4\]
C-->D[media*4 = numero1+ numero2 + numero 3 + numero4]
D-->E[\media\]
E-->F{{"Essa é a média:" media}}
F-->G([FIM])
```

#### Pseudocódigo (1.0 ponto)

```
1 ALGORITMO Media
2 DECLARE: numero1,numero2,numero3,numero4: INTEIRO
media:REAL
3ESCREVA "Digite quatro números inteiros"
4INICIO
5LEIA numero1,numero2,numero3,numero4
6 media*4 = numero1 + numero2 + numero3 + numero4
7LEIA media
8ESCREVA "Essa é a média"media 
9FIM_ALGORITMO
```

#### Teste de mesa (0.5 ponto)

| numeros | media | saída | 
| -- | -- | -- |
| 1,2,3,4 | 2.5   |  Essa é a média: 2.5       |       
| -3,-4,-5,6 | -1.5  | Essa é a média:-1.5    |  
| 0,2,3,10   | 3.75  | Essa é a média: 3.75      | 

### Exercício 02 (2.5 pontos)
Leia uma temperatura dada em Celsius (C) e imprima o equivalente em Fahrenheit (F). (Fórmula de conversão: F = (9/5) * C + 32)

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO])-->B{{"Dê uma tempertaura em Celsius"}}
B-->C[\temp_celsius\]
C-->D[ 9/5 * temp_celsius  + 32 = temp_farenheit]
D-->E[\temp_farenheit\]
E-->F{{"Essa é a temperatura em F°"temp_farenheit}}
F-->G([FIM])
```

#### Pseudocódigo (1.0 ponto)

```
1ALGORITMO ConverteCelsiusFarenheit
2DECLARE temp_celsius, temp_farenheit:REAL
3ESCREVA "Dê uma temperatura em Celsius"
4INICIO
5LEIA temp_celsius
6temp_celsius*(9/5) + 32 = temp_farenheit
7LEIA temp_farenheit
8ESCREVA "Essa é a temperatura em F°"temp_farenheit
9FIM_ALGORITMO
```

#### Teste de mesa (0.5 ponto)

| Temperatura Celsius | Temperatura Farenheit | Saída | 
|      --      |      --      |   --        |     
| 0   | 32       | Essa é a temperatura em F° 32   | 
| 100  |  257         | Essa é a temperatura em F°  212    |

### Exercício 03 (2.5 pontos)
Receba dois números reais e um operador e efetue a operação correspondente com os valores recebidos (operandos). 
O algoritmo deve retornar o resultado da operação selecionada simulando todas as operações de uma calculadora simples.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{"Digite dois numero e faça uma operação aritimética com eles"}}
B-->C[\numero1,numero2\]
C-->D{+}
D--T-->E[resultado = numero1 + numero2]
E-->F[\resultado\]
F-->G{{"Resultado ="resultado}}
D--F-->H{-}
H--T-->I[resultado = numero1 - numero2]
I-->F
H--F-->J{*}
J--T-->K[resultado = numero1 * numero2]
K-->F
J--F-->L{/}
L--T-->M[resultado = numero1 / numero2]
M-->F
L--F-->N([FIM])
G-->N
```

#### Pseudocódigo (1.0 ponto)

```
1ALGORITMO Calculadora
2DECLARE numero1,numero2,resultado:REAL +,-,*,/:LÓGICO
3ESCREVA "Digite dois números e faça uma operação aritmética com eles"
4INICIO
5LEIA numero1,numero2
6ESCOLHA
7CASO "+" resultado = numero1 + numero2
8CASO "-" resultado = numero1 - numero2
9CASO "*" resultado = numero1 * numero2
10CASO "/" resultado = numero1 / numero2
11SENAO
12FIM_ALGORITMO
13FIM_ESCOLHA
14ESCREVA "Resultado =" resultado
15FIM_ALGORITMO
```

#### Teste de mesa (0.5 ponto)

| numeros | soma | subtração | multiplicação | divisão |  
|      --      |      --      |      --      |      --      |      --      | 
| 1,2     | 3   | -1    |  2     | 0.5    |
| 3,4   | 7          | -1        | 12 | 0.75  |

### Exercício 04 (2.5 pontos)
Elaborar um algoritmo que, dada a idade, classifique nas categorias: infantil A (5 - 7 anos), infantil B (8 -10 anos), juvenil A (11 - 13 anos), juvenil B (14 -17 anos) e adulto (maiores que 18 anos).

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{"Escreva aqui sua idade"}}
B-->C[\idade\]
C-->D{4< e <8}
D--T-->E{{Infantil A}}
D--F-->F{7< e <11}
F--T-->G{{Infantil B}}
F--F-->H{10< e <14}
H--T-->I{{Juvenil A}}
H--F-->J{13< e <18}
J--T-->K{{Juvenil B}}
J--F-->L{17< Idade}
L--T-->M{{Adulto}}
L--F-->N{{Jovem demais}}
N-->O([FIM])
E-->O
G-->O
I-->O
K-->O
M-->O

```

#### Pseudocódigo (1.0 ponto)

```
1ALGORITMO ClassificaCategoria
2DECLARE idade:INTEIRO 
3ESCREVA:"Digite aqui a sua idade"
4INICIO
5LEIA Idade
5ESCOLHA
6CASO idade <8 and<4 ENTAO
8 ESCREVA Infatil A
9CASO idade<11 and >7
11 ESCREVA Infantil B
12CASO idade<14 and >10
13ESCREVA Juvenil A
14CASO idade<18 and >13
15ESCREVA Juvenil B
16CASO idade<17
17ESCREVA Adulto
18SENAO
19ESCREVA "Jovem demais"
20FIM_ESCOLHA
21FIM_ALGORITMO
```

#### Teste de mesa (0.5 ponto)

| Idade | 4< e <8 | 7< e <11 | 10< e <14 | 13< e <18 | 17< Idade | Saída |
|      --      |      --      |      --      |      --      |      --      | -- | -- |  
|  4    |    F   |  F   |   F    | F    | F | Jovem demais |
| 15 |    F       |    F     | F | T  | | Juvenil B |
|  18    |  F     |   F  |  F     | F    | T | Adulto |
|   8   |  F     |  T   |       |     | | Infantil B |
# UNIFOR Lista 3
**Nome**: Aaron Magno Campos Nogueira
**Disciplina**: Raciocínio lógico algorítm

## Exercício exemplo 1
Implemente e teste um programa que imprima os n primeiros números.

#### Fluxograma
```mermaid
flowchart TD
A([INICIO]) --> B{{Digite um número: }}
B --> C[\n\]
C --> D[\num = 1\]
D --> E{num <= n}
E --FALSE--> I([FIM])
E --TRUE--> F{{"Num", num}}
F --> G[num =+ 1]
G --LOOP--> E
```

#### Pseudocódigo
```
1 ALGORITMO print_n_primeiros
2 DECLARE n, num: INTEIRO
3 INICIO
4 ESCREVA “Digite um número: ”
4 LEIA n			// variável de entrada n
4 num ← 1			// variável num inicializada
5 ENQUANTO num <= n FAÇA	// n iterações
7	ESCREVA “Número ”, num
8	num ← num + 1		// num =+ 1 (incremento)
8 FIM_ENQUANTO
9 FIM
```

#### Teste de mesa
| it | n  | num | num <= n | Saída      | num =+ 1 |
| -- | -- | --  | --       | --         | --       |
| 1  | 10 | 1   | True     | Número 1   | 2        |
| 2  | 10 | 2   | True     | Número 2   | 3        |
| 3  | 10 | 3   | True     | Número 3   | 4        |
| 4  | 10 | 4   | True     | Número 4   | 5        |
| 5  | 10 | 5   | True     | Número 5   | 6        |
| 6  | 10 | 6   | True     | Número 6   | 7        |
| 7  | 10 | 7   | True     | Número 7   | 8        |
| 8  | 10 | 8   | True     | Número 8   | 9        |
| 9  | 10 | 9   | True     | Número 9   | 10       |
| 10 | 10 | 11  | True     | Número 10  | 11       |
| 11 | 10 | 11  | False    |            |          |

## Exercício exemplo 2
Implemente e teste um programa que some os n primeiros números.

#### Fluxograma
```mermaid
flowchart TD
A([INICIO]) --> B{{Digite um número: }}
B --> C[\n\]
C --> D[\soma = 0\]
D --> E[[i=1 ATÉ n PASSO 1]]
E --> G([FIM])
E --> F[soma =+ i]
F --LOOP--> E
```

#### Pseudocódigo
```
1  ALGORITMO	soma_n_numeros()
2  DECLARE	n, i, soma: INTEIRO
3  INICIO
4  ESCREVA “Digite a quantidade de números: ”
5  LEIA n		// variável de entrada n
7  soma ← 0		// variável soma inicializada
6  PARA i DE 1 ATÉ n PASSO 1 FAÇA
7	soma ← soma + i	// soma =+ i (incremento)
8  FIM_PARA
9  ESCREVA “A soma é igual a ”, soma
10 FIM
```

#### Teste de mesa
| it | n  | soma | i  | soma =+ i |
| -- | -- | --   | -- | --        |
| 1  | 10 | 0    | 1  | 1         |
| 2  | 10 | 1    | 2  | 3         |
| 3  | 10 | 3    | 3  | 6         |
| 4  | 10 | 6    | 4  | 10        |
| 5  | 10 | 10   | 5  | 15        |
| 6  | 10 | 15   | 6  | 21        |
| 7  | 10 | 21   | 7  | 28        |
| 8  | 10 | 28   | 8  | 36        |
| 9  | 10 | 36   | 9  | 45        |
| 10 | 10 | 45   | 10 | 55        | 

## Lista de exercícios 03

### Exercício 01 (2.5 pontos)
Atualize o algoritmo para determinar se um número inteiro e positivo é par ou ímpar, usando uma laço condicional para aceitar apenas números maiores ou iguais a zero. 

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD                                                 
A([INICIO]) --> B{{Digite um número positivo!: }}              
B --> C[\num\]
C --> D{num >= 0}                                                     
D--FALSE/LOOP--> B                              
D --TRUE--> F[resto = numero % 2]
F --> G{resto == 0}
G --FALSE--> H{{O número é impar!}}
G --TRUE--> I{{O número é par!}}
H --> Z([FIM])
I --> Z

```

#### Pseudocódigo (1.0 ponto)

```
1  ALGORTIMO Classifica Categoria          
2  DECLARE num, resto: INTEIRO
3  ESCREVA "Digite um número positivo!: "
4  INICIO
4  LEIA num
5  SE num >= 0
6    resto = numero %2
7   SE resto == 0
8  ESCREVA "O número é ímpar"
9   SENÃO
10    ESCREVA"O número é par"
12  FIM_SE
13 SENAO
14  ENQUANTO num < 0 FAÇA
15  ESCREVA "Digite um número positivo!: "
16  FIM_ENQUANTO
17  FIM_SE
18 FIM ALGORITMO

```

#### Teste de mesa (0.5 ponto)

| Número | >= 0 | resto ==0 | Saída |  
|      --      |      --      |      --      |    -- | 
| -1 |   F     |     | Digite um número positivo  |
| 0   | T          | T        | O número é par |
| 2     | T      | T    | O número é par |
| 1  | T         | F    |  O número é ímpar |
### Exercício 02 (2.5 pontos)
Faça um algoritmo que exiba na tela uma contagem de 0 até 30, exibindo apenas os múltiplos de 3.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B[n = 30]
B --> C[\n\]
C --> D[\num = 0\]
D --> E{num <= 30}
E --FALSE--> I([FIM])
E --TRUE--> F{{"Num", num}}
F --> G[[num =+ 3]]
G --LOOP--> E
```

#### Pseudocódigo (1.0 ponto)

```
1 ALGORITMO print_multiplos_de_3
2 DECLARE n, num: INTEIRO
3 INICIO
4 ESCREVA n = 30
4 LEIA n			
4 num ← 0			
5 ENQUANTO num <= n FAÇA	
7	ESCREVA “Número ”, num
8	num ← num + 3		
8 FIM_ENQUANTO
9 FIM
```

#### Teste de mesa (0.5 ponto)

| it | n  | num | num <= n | Saída      | num =+ 3 |
| -- | -- | --  | --       | --         | --       |
| 1  | 30 | 0   | True     | Número 1   | 3        |
| 2  | 30 | 3   | True     | Número 2   | 6        |
| 3  | 30 | 6   | True     | Número 3   | 9        |
| 4  | 30 | 9   | True     | Número 4   | 12        |
| 5  | 30 | 12   | True     | Número 5   | 15        |
| 6  | 30 | 15   | True     | Número 6   | 18        |
| 7  | 30 | 18   | True     | Número 7   | 21        |
| 8  | 30 | 21   | True     | Número 8   | 24        |
| 9  | 30 | 24   | True     | Número 9   | 27       |
| 10 | 30 | 27  | True     | Número 10  | 30       |
| 11 | 30 | 30  | True   | Número 11    | 33       |
| 12 | 30 | 33  | False   |      --      |    --      |

### Exercício 03 (2.5 pontos)
Dada uma sequência de números inteiros, calcular a sua soma. 
Por exemplo, para a sequência {12, 17, 4, -6, 8, 0}, o seu programa deve escrever o número 35.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite os números}}
B-->C[\n,x\]
C-->D[[ i de 1 ATÉ x PASSO 1]]  
D-->E[soma =+ n]
E-->H{i = x}
H--T-->F{{A soma é soma}}
H--F-->E
F-->G([FIM])





```

#### Pseudocódigo (1.0 ponto)

```
1 ALGORITMO Soma_os_números
2 DECLARE n,i,x,soma:INTEIRO
3 ESCREVA "Digite os números"
4 INICIO
5 LEIA [\n,x\] // n são os números e x é a quantidade de números.
6 PARA i DE 1 ATÉ x PASSO 1 FAÇA 
9 soma ← soma + n
10 FIM_PARA
11 LEIA soma
12 ESCREVA "A soma é soma"
13 FIM_ALGORITMO
```

#### Teste de mesa (0.5 ponto)

| iteração | i | saída | n |  x |
|      --      |      --      |      --      |      --      |   -- |   
|      0      |      1      |      A soma é 0      |          12, 17, 4, -6, 8, 0 | 6  |
|      1      |      1      |      A soma é 12      |                 17,4,-6,8,0       | 6 |
|      2      |      2      |      A soma é 29     |              4,-6,8,0         | 6 | 
|      3      |      3      |      A soma é 33     |                -6,8,0      | 6 |
|      4      |      4      |      A soma é  27    |              8,0        |  6 | 
|      5      |      5      |      A soma é  35    |                 0        | 6 |
| 6 | 6 | A soma é  35 | | 6 |


### Exercício 04 (2.5 pontos)
Escreva um programa que leia a nota de diversos alunos, até que seja digitada uma nota negativa. 
Nesse momento, ele mostra a média aritmética de todas as notas lidas e quantas notas foram lidas. 
Ex. Foram lidas 14 notas. A média aritmética é 6.75!

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite as notas}}
B-->C[\n\]
B-->X[ x = i+y do número negativo]
X-->Z[ y = any positive integral number]
C-->D[i <- 1]
D-->E{i != x}
E--T-->H[soma =+ ni,i =+1]
E--F-->G[ soma = media * x-1]
H--LOOP-->E
G-->M[\media, x-1, soma\]
M-->N{{Foram lidas x-1 notas e a média aritmética é media}}
N-->O([FIM])

```

#### Pseudocódigo (1.0 ponto)

```
1ALGORITMO ClassificaCategoria
2DECLARE x,i,y:INTEIROS media, soma, n:REAL
3ESCREVA"Digite as notas"
4INICIO
5LEIA n // as notas
6 x = i + y do n negativo
7 y c Inteiros
8 i <- 1
9ENQUANTO i != x  FAÇA
10soma =+ni e i=+1
11FIM_ENQUANTO
12SE i = x ENTÃO
13soma - nx = media*(x-1)
14FIM_SE
15LEIA media,soma,x-1
16ESCREVA Foram lidas x-1 notas e a média aritmética é media
17FIM


 
FIM_ALGORITMO
```

#### Teste de mesa (0.5 ponto)

| notas | média | x |  soma | nx | saída |
|      --      |      --      |      --      |      --      |      --      |  -- |
| 10, 9,8,7.5, -30   |   8.625     | 5    |  4.5     | -30    | Foram lidas 4 notas e a média aritmética foi 8.625|
| 10, 8, 7 ,4,5,-2   |    6.75       | 6        | 32  | -2 | Foram lidas 5 notas e a média aritmética foi 8.625|   




<img src="https://drive.google.com/uc?id=1SOzRTjUt7cuBJpSqoK90fcAiKBrnpUJo" width="400">

**Curso:** Ciências da Computação
**Disciplina:** Raciocínio Lógico algoritmico
**Código/Turma:** T160-60
**Professor:** Ricardo Carubbi <br>
**Data:** 21/03/24
**Aluno(a):** Aaron Magno Campos Nogueira
**Matrícula:** 2413085

**1a chamada (Sim/Não):** Sim
**2a chamada (Sim/Não):** Não

# Avaliação Diagnóstica 1

## Normas e exigências

Avaliação diagnóstica (**AD**) consiste em exercícios ou projetos desenvolvidos em grupo ao longo da disciplina. <br>
A primeira avaliação diagnóstica (**AD1**) será composta por exercícios e equivale a 30% da nota da primeira avaliação (**AV1**).

Segue abaixo a expressão para o cálculo da **AV1**, sendo sendo **AF1** equivale a primeira avaliação formativa e **AD1**, a primeira avaliação diagnóstica.

$$AV_1 = AF_1 \times 0,30 + AD_1 \times 0,70$$

A **AD1** é formada pela entrega dos exercícios (**EX1**) na data prevista e apresentação (**AP1**) de um dos exercícios escolhido pelo professor.
Segue abaixo a expressão para o cálculo da **AD1**.

$$AD_1 = (EX1_1 + AP_1)/2 $$

A **EX1** é avaliada mediante a **correção dos exercícios**, sendo a avaliação no intervalo de 0% (não atende a questão), 50% (atende parcialmente) e 100% (atende em sua totalidade).
Por exemplo, se o exercício equivale a 2 pontos e sua correção atente parcialmente a questão, então sua avaliação deste exercício será 1 ponto.

A **AP1** é avaliada mediante aos pré-requisitos de **clareza, organização e domínio do conteúdo**. Portanto, o aluno deve demonstrar um bom entendimento do algoritmo, explicando seus princípios fundamentais, seu propósito e como ele funciona passo a passo. <br>

A avaliação da **AP1** é apenas considerada no intervalo de 0% (não atende os pré-requisitos), 25% (pouco atende os pré-requisitos), 50% (atende de forma mediana os pré-requisitos), 75% (atende de forma razoável os pré-requisitos) e 100% (atende em a totalidade dos pré-requisitos).
Por exemplo, se na apresentação do exercício, o aluno atenter de forma razoável a questão, então sua avaliação da apresentação será 7.5 pontos.

## Datas
- Entrega da primeira avaliação formativa (**AF1**) composta pelas listas de exerciícios 1, 2 e 3: 21/03/24
- Entrega dos exercícios da primeira avaliação diagnóstica (**EX1**): 21/03/24
- Apresentação da primeira avaliação diagnóstica (**AP1**): 21/03/24

## Lista de questões

### Questão 1 - Troca dos valores de duas variáveis (1 ponto)

Dadas duas variáveis, $a$ e $b$, implemente e teste um algoritmo para trocar os valores atribuídos a elas.

#### Descrição geral do algoritmo

1. Guardar o valor original da variável $a$ em uma variável auxiliar $aux$;
2. Atribuir à variável $a$ o valor original da variável $b$;
3. Atribuir à variável $b$ o valor original da variável $a$, que está armazenado na variável auxiliar $aux$.
4. Exibir os novos valores de $a$ e $b$.

#### Fluxograma

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite o valor da a: }}
B --> C[\a\]
C --> D{{Digite o valor da b: }}
D --> E[\b\]
E --> F[aux = a]
F --> G[a = b]
G --> H[b = aux]
H --> I{{"a =", a}}
I --> J{{"b =", b}}
```

#### Pseudocódigo (1 ponto)

```
Algoritmo TrocaValores
INICIO
ESCREVA "Digite o valor de a:"
LEIA a
ESCREVA"Digite o valor d b:"
LEIA b
aux = a
a = b
b = aux
ESCREVA ""a =" a"
ESCREVA ""b ="b"
FIM
```

#### Teste de mesa

| a  | b  | aux | a  | b  | saída 1 | saída 2 | 
| -- | -- | --  | -- | -- | --      | --      | 
| 0  | 1  | 0   | 1  | 0  | a = 1   | b = 0   |

### Questão 2 - Contagem (1 ponto)

Dado um conjunto $n$ de notas de alunos em um exame, implemente e teste um algoritmo para fazer uma contagem $cont$ do número de alunos que foram aprovados no exame. 
Será considerado aprovado o aluno que tirar $nota$ 50 ou maior (no intervalo de 0 a 100).

#### Descrição geral do algoritmo

1. Obter o número de notas $n$ a serem processadas;
2. Inicializar a contagem $cont$ com zero;
3. Enquanto houver notas a serem processadas, fazer repetidamente:
    - obter a próxima nota;
    - se a nota for suficiente para passar no exame ($n ≥ 50$) então adicionar 1 (um) à contagem $cont$;
4. Exibir a contagem $cont$ (número total de aprovações).

#### Fluxograma 01
Fluxograma conforme descrição do algoritmo acima, usando o loop ENQUANTO.

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite o número de alunos: }}
B --> C[\n\]
C --> D[\cont = 0\]
D --> E[\i = 1\]
E --> F{i <= n}
F --FALSE--> W{{Número de alunos aprovados: cont}}
W --> Z([FIM])
F --TRUE--> G{{Digite a nota do aluno, i}}
G --> H[\nota\]
H --> I{"nota >= 50 <br>E <br>nota <=100"}
I --TRUE--> J[\cont =+ 1\]
I --FALSE--> K[\i =+ 1\]
J --> K
K --LOOP--> F
```

#### Fluxograma 02
Fluxograma opcional usando o loop PARA.
ALGORITMO Loop_enquanto
INICIO
ESCREVA "Digite o número de alunos:"
LEIA n
LEIA cont = 0
LEIA i = 1
SE i <= n ENTÃO
ESCREVA "Digite a nota do aluno" i
SENAO 
ESCREVA "Número de alunos aprovados"cont
FIM_SE
LEIA nota
ENQUANTO nota >= 50 <br>E <br>nota <=100 FAÇA
cont=+1 
i =+1
LOOP ESCREVA "Digite a nota do aluno" i
FIM_ENQUANTO
FIM


```mermaid
flowchart TD
A([INICIO]) --> B{{Digite o número de notas: }}
B --> C[\n\]
C --> D[\cont = 0\]
D --> E[[i=1 ATE n PASSO 1]]
E --"i=1,2...,n"--> F{{Digite nota, i}}
E --"i > n"--> K{{Número de alunos aprovados: , cont}}
K --> L([FIM])
F --> G[\nota\]
G --> H{"nota >= 50 <br>E <br>nota <=100"}
H --FALSE/LOOP--> E
H --TRUE--> J[\cont =+ 1\]
J --LOOP--> E
```

#### Pseudocódigo 01 (1 ponto)

```
Algoritmo ContaAprovacoes
ALGORITMO Loop_enquanto
INICIO
ESCREVA "Digite o número de alunos:"
LEIA n
LEIA cont = 0
LEIA i = 1
SE i <= n ENTÃO
ESCREVA "Digite a nota do aluno" i
SENAO 
ESCREVA "Número de alunos aprovados"cont
FIM_SE
LEIA nota
ENQUANTO nota >= 50 <br>E <br>nota <=100 FAÇA
cont=+1 
i =+1
LOOP ESCREVA "Digite a nota do aluno" i
FIM_ENQUANTO
FIM
```

#### Teste de mesa 01
Teste de mesa referente ao algoritmo usando o loop ENQUANTO.

| it | n  | i  | cont | i<=n  | nota, i | nota | nota_valida | cont+1 | i+1 | saída        | 
| -- | -- | -- | --   | --    | --      | --   | --          | --     | --  | --           |
| 1  | 3  | 1  |  0   | True  | nota 1  | 60   | True        | 1      | 2   |              |
| 2  | 3  | 2  |  1   | True  | nota 2  | 40   | False       | 1      | 3   |              |
| 3  | 3  | 3  |  1   | True  | nota 3  | 90   | True        | 2      | 4   |              |
| 4  | 3  | 4  |  2   | False |         |      |             |        |     | Aprovados: 2 |

#### Teste de mesa 02
Teste de mesa referente ao algoritmo usando o loop PARA.

| it | n  | cont | i  | nota, i | nota | nota_valida | cont+1 | saída        | 
| -- | -- | --   | -- | --      | --   | --          | --     | --           |
| 1  | 3  | 0    | 1  | nota 1  | 60   | True        | 1      |              |
| 2  | 3  | 1    | 2  | nota 2  | 40   | False       | 1      |              |
| 3  | 3  | 1    | 3  | nota 3  | 90   | True        | 2      | Aprovados: 2 |

### Questão 3 - Soma de um conjunto de números (1 ponto)

Dado um conjunto de $n$ números, implemente e teste um algoritmo para calcular a soma desses números. <br>
Aceite apenas $n$ maior ou igual a zero.

#### Descrição geral do algoritmo

1. Obter a quantidade de números $n$ a serem somados.
2. Inicializar a variável $soma$ com 0 (zero).
3. Enquanto menos do que $n$ números tiverem sido somados, fazer repetidamente:
    - obter o próximo número $i$;
    - calcular a soma atual, adicionando o número $i$ obtido à soma mais recente;
4. Exibir a soma dos $n$ números

#### Fluxograma

```mermaid
flowchart TD
A([INICIO]) --> B{{"Digite a quantidade de números<br> (n >= 0):"}}
B --> C[\n\]
C --> D{n >= 0}
D --FALSE-->N{{"O valor deve ser maior ou igual a zero!"}}
N --> M([FIM])
D --TRUE--> E[/soma = 0/]
E --> F[i = 1]
F --> G{i <= n}
G --FALSE--> L{{"A soma dos numeros é , soma"}}
L --> M
G --TRUE--> H{{Digite um número: }}
H --> I[\num\]
I --> J[soma =+ num]
J --> K[i =+ 1]
K --LOOP--> G
```

#### Pseudocódigo (1 ponto)

```
Algoritmo SomaNumeros
INICIO
ESCREVA "Digite a quantidade de números<br> (n >= 0):"
LEIA n
CASO n >= 0 ENTAO
soma = 0
CASO n < o ENTAO
ESCREVA "O valor deve ser maior ou igual a zero!"
...
FIM
```

#### Teste de mesa

| it | n  | n >= 0 | soma | i  | i <= n | num | soma =+ num  | saída                   |
| -- | -- | --     | --   | -- | --     | --  | --           | --                      |
|    | -3 | False  |      |    |        |     |              | O valor deve ser ...    |
| 1  | 0  | True   | 0    | 1  | False  |     |              | A soma dos números é 0  |
| 1  | 3  | True   | 0    | 1  | True   | 5   | 0 + 5 = 5    |                         |
| 2  | 3  | True   | 5    | 2  | True   | 10  | 5 + 10 = 15  |                         |
| 3  | 3  | True   | 15   | 3  | True   | 20  | 15 + 20 = 35 |                         |
| 4  | 3  | True   | 35   | 4  | False  |     |              | A soma dos números é 35 |

### Questão 4 - Cálculo de uma série (1 ponto)

Dado um conjunto de $n$ termos da série, implemente e teste um algoritmo para calcular o valor de S, conforme definido abaixo:

$$ S = \frac{1}{2} + \frac{3}{4} + \frac{5}{6} + \frac{7}{8} + \dots $$

#### Descrição geral do algoritmo

1. Obter o número de termos $n$;
2. Inicializar a variável $S$ com 0 (zero).
3. Iterar o valor de $n$ na variável $i$ iniciando com 0 (zero), de acordo com as instruções abaixo:
    - calcular o numerador na variável $numerador$;
    - calcular o denominador  na variável $denominador$;;
    - calcular o termo da série na variável $termo$, onde $termo = numerador/denominador$;
    - adicionar esse termo à variável $S$.
4. Exibir o valor da série $S$.

#### Fluxograma

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite o número de termos da série S: }}
B --> C[/n/]
C --> D[S = 0]
D --> E[[i=0 ATE n PASSO 1]]
E --i > n--> J{{"Soma da série S é ", S}}
J --> K([FIM])
E --"i=0,1,2,..,n"--> F[numerador = 2 * i + 1]
F --> G[denominador = 2 * i + 2]
G --> H[termo = numerador / denominador]
H --> I[S += termo]
I --LOOP--> E
```

#### Pseudocódigo (1 ponto)

```
Algoritmo SomaSerie
INICIO
...
FIM
```

#### Teste de mesa (0.25 ponto)

| it | n  | S  | i | numerador | denominador | termo | S += termo     | saída                  |
| -- | -- | -- |-- | --        | --          | --    | --             | --                     |
|    | 0  | 0  |   |           |             |       |                |                        |
| 1  | 4  | 0  | 0 | 2*0+1 = 1 | 2*0+2 = 2   | 1/2   | 0+1/2 = 1/2    |                        |
| 2  | 4  | 0  | 1 | 2*1+1 = 1 | 2*1+2 = 2   | 3/4   | 1/2+3/4 = 1.25 |                        |
| 3  | 4  | 0  | 2 | 2*2+1 = 1 | 2*2+2 = 2   | 5/6   | 0+1/2 = 2.08   |                        |
| 4  | 4  | 0  | 3 | 2*3+1 = 1 | 2*3+2 = 2   | 7/8   | 0+1/2 = 2.96   | Soma da série S é 2.96 |

### Questão 5 - Cálculo fatorial (2 pontos)

Dado um número $n$, implemente e teste um algoritmo para calcular o fatorial de $n$ (escrito como $n!$), onde $n ≥ 0$.

#### Descrição geral do algoritmo

1. Obter o número $n$, onde $n \geq 0$;
2. Inicializar a variável $fator$ com 1 (um) para armazenar o resultado do cálculo do fatorial;
3. Iterar o valor de $n$ na variável $i$, ou seja, executar $n$ vezes, as instruções abaixo:
    - Incrementar o valor atual $fator$ multiplicando pelo valor de $i$;
4. Exibir o resultado ($n!$).

#### Fluxograma

```mermaid
flowchart TD
A([INICIO]) --> B{{"Digite um numero inteiro nao-negativo:"}}
B --> C[/n/]
C --> D{n >= 0}
D --TRUE--> E[fator = 1]
D --FALSE--> J{{O valor deve ser maior ou igual a zero!}}
J --> I([FIM])
E --> F[[i=1 ATÉ n PASSO 1]]
F --"i > n"--> H{{O fatorial de, n, é:, fator}}
F --"i=1,2,..n"--> G[fator = fator * i]
G --LOOP--> F
H --> I
```

#### Pseudocódigo (2 pontos)

```
Algoritmo CalcFatorial
INICIO
...
FIM
```

#### Teste de mesa

| n  | fator | i  | fator = fator * i | saída               |
| -- | --    | -- | --                | --                  |
| 3  | 1     | 1  | 1*1 = 1           |                     |
| 3  | 1     | 2  | 1*2 = 2           |                     |
| 3  | 2     | 3  | 2*3 = 6           | O fatorial de 3 é 6 |

### Questão 6 - Geração da sequência de Fibonacci (2 pontos)

Gerar e imprimir os $n$ primeiros termos da sequência de Fibonacci, onde $n ≥ 1$. <br>
Os primeiros termos são: $0, 1, 1, 2, 3, 5, 8, 13, \dots$. Cada termo, além dos dois primeiros, é derivado da soma dos seus dois antecessores mais próximos.

#### Descrição geral do algoritmo

1. Obter o número de termos $n$, onde $n \geq 1$;
2. Inicializar os dois primeiros termos da série nas variável $a$ e $b$ com 0 (zero);
3. Iterar o valor de $n$, ou seja, executar $n$ vezes, as instruções abaixo:
    - Imprimir o termo inicial $a$ (instrução para exibir a sequência ao atualizar a variável $a$);
    - Somar os termos $a$ e $b$ na variável $termo_atual$;
    - Atribuir a variável $a$ o valor da variável $b$;
    - Atribuir a variável $b$ o valor da variável $termo_atual$.

#### Fluxograma

```mermaid
flowchart TD
A([INICIO]) --> B{{"Número de termos da série Fibonacci:"}}
B --> C[a = 0]
C --> D[b = 1]
D --> E[[i=1 ATÉ n PASSO 1]]
E --"i > n"--> J([FIM])
E --"i=1,2,...,n"--> F{{a}}
F --> G[termo_atual = a + b]
G --> H[a = b]
H --> I[b = termo_atual]
I --LOOP--> E 
```

#### Pseudocódigo (2 pontos)

```
Algoritmo GeraFibonacci
INICIO
...
FIM
```
#### Teste de mesa

| it | n  | a  | b  | i  | saída | termo_atual = a + b | a = b | b = termo_atual |
| -- | -- | -- | -- | -- | --    | --                  | --    | --              |
| 1  | 5  | 0  | 1  | 1  | 0     | 0 + 1 = 1           | 1     | 1               |
| 2  | 5  | 1  | 1  | 2  | 1     | 1 + 1 = 2           | 1     | 2               |
| 3  | 5  | 1  | 2  | 3  | 1     | 1 + 2 = 3           | 2     | 3               |
| 4  | 5  | 2  | 3  | 4  | 2     | 2 + 3 = 5           | 3     | 5               |
| 4  | 5  | 3  | 5  | 5  | 3     | 3 + 5 = 8           | 5     | 8               |

### Questão 7 - Inversão dos dígitos de um número inteiro (2 pontos)

Implemente e teste um algoritmo para inverter a ordem dos dígitos de um número inteiro positivo.

#### Descrição geral do algoritmo

1. Obter o número inteiro positivo $num$ a ser invertido;
2. Inicializar a variável $num \textunderscore inv$ com 0 (zero);
3. Enquanto o número for maior que zero ($num > 0$), faça repetidamente:
    - Calcular o último dígito do número na variável $digito$;
    - Adicionar o dígito ao número invertido $num \textunderscore inv$;
    - Remover o último dígito do número original $num$; 
4. Exibir o número invertido.

#### Fluxograma

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite um número inteiro: }}
B --> C[\num\]
C --> D{num >= 0}
D --TRUE--> G[num_inv = 0]
G --> H{num > 0}
H --FALSE--> Z{{"Número invertido:", numero_inv}}
Z --> W([FIM])
H --TRUE--> I[digito = num % 10]
I --> J[num_inv = num_inv * 10 + digito]
J --> K[numero = numero // 10]
K --LOOP--> H
D --FALSE--> E{{O número deve ser positivo!}}
E --> W
```

#### Pseudocódigo (2 pontos)

```
Algoritmo InverteInteiro
INICIO
...
FIM
```

#### Teste de mesa

| it | num | num_inv | num > 0 | digito | num = num // 10 | num_inv = (num_inv * 10) + digito | Saída                       |
| -- | --  | --      | --     | --      | --              | --                                | --                          |
|    | -1  | 0       | False  |         |                 |                                   | O número deve ser positivo! |
| 1  | 0   | 0       | False  |         |                 |                                   | Número invertido:: 0        |
| 1  | 42  | 0       | True   | 2       | 4               | 2                                 |                             |
| 2  | 4   | 2       | True   | 4       | 0               | 24                                |                             |
| 3  | 0   | 24      | False  |         |                 |                                   | Número invertido:: 24       |














