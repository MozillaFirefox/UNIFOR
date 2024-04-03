# UNIFOR
**Nome**: Aaron Magno Campos Nogueira
**Disciplina**: Raciocínio lógico algorítm

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
```java
ALGORITMO calReajuste
DECLARE  sal, sal_reaj: real, prof: caractere

INICIO
    //Exibe mensagem para entrada de dados
    ESCREVA "Digite o salário e profissão"
    // Dados de entrada armazenado nas variável sal e prof
    LEIA sal, prof

    // Executa as instruções sob a condição de um dos casos for verdadeiro
    ESCOLHA

        // Executa a instrução de atribuir à variável sal_reaj o valor 1.5*sal sob a condição de prof == "Técnico"  
        CASO prof == “Técnico”		
            sal_reaj ← 1.5 * sal

        // Executa a instrução de atribuir à variável sal_reaj o valor 1.3*sal sob a condição de prof == "Gerente"  
        CASO prof = “Gerente”		
            sal_reaj ← 1.3 * sal

    // Executa a instrução de atribuir à variável sal_reaj o valor 1.1*sal sob a condição de nenhum dos casos posteriores for verdadeiro
    SENÃO
        sal_reaj ← 1.1 * sal

    FIM_ESCOLHA

    // Exibe a mensagem concatenando "Salário Reajustado = “ com a variável sal_reaj
    ESCREVA “Salário Reajustado = “, sal_reaj

FIM
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
A([INICIO]) --> B{{"Digite o número 1:"}}
B --> C[/num1/]
C --> D{{"Digite o número 2:"}}
D --> E[/num2/]
E --> F{{"Digite o número 3:"}}
F --> G[/num3/]
G --> H{{"Digite o número 2:"}}
H --> I[/num4/]
I --> J["media = (num1 + num2 + num3 + num4)/4"]
J --> K{{A média é, media}}
K --> L([FIM]) 
```

#### Pseudocódigo (1.0 ponto)

```java
ALGORTIMO Media
DECLARE num1, num2, num3, num4: REAL

INICIO

    //  Exibe a mensagem com a solicitação de um número ao usuário

    ESCREVA "Digite o número 1:"

    // Dado de entrada armazenado na variável num1

    LEIA num1

    // Exibe a mensagem com a solicitação de um número ao usuário

    ESCREVA "Digite o número 2:"

    // Dado de entrada armazenado na variável num2
    LEIA num2

    // Exibe a mensagem com a solicitação de um número ao usuário

    ESCREVA "Digite o número 3:"

    // Dado de entrada armazenado na variável num3
    LEIA num3

    // Exibe a mensagem com a solicitação de um número ao usuário 
    ESCREVA "Digite o número 4:"

    // Dado de entrada armazenado na variável num2
    LEIA num4

    // Calcula a média das notas atribuindo o valor de (num1 + num2 + num3 + num4)/4 à variável media, por fim exibe a mensagem concatenando "A média é" com a variável media

    media <- (num1 + num2 + num3 + num4)/4
    ESCREVA "A média é", media

FIM
```

#### Teste de mesa (0.5 ponto)

| num1 | num2 | num3 | num4 | saída | 
| --   | --   | --   | --   | --    | 
| 0.25 | 0.25 | 2.50 | 1.00 | 1.00  | 

### Exercício 02 (2.5 pontos)
Leia uma temperatura dada em Celsius (C) e imprima o equivalente em Fahrenheit (F). (Fórmula de conversão: F = (9/5) * C + 32)

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{"Digite a temperatura em Celisus:"}}
B --> C[/C/]
C --> D["F = (9/5) * C + 32"]
D --> E{{A temperatura em Fahrenheit é, F, graus}}
E --> F([FIM])
```

#### Pseudocódigo (1.0 ponto)

```java
ALGORTIMO ConverteCelsiusFarenheit
DECLARE C, F: REAL

INICIO

    //  Exibe a mensagem com a solicitação de um número real ao usuário
    ESCREVA "Digite a temperatura em Celisus:"

    // Armazena o valor de entrada na variável "C"

    LEIA C

    // Calcula a temperatura em Farenheit atribuindo o valor da expressão (9/5) * C + 32 à variável F
    F <- (9/5) * C + 32

    //   Exibe a mensagem relativa à temperatura em Fº

    ESCREVA "A temperatura em Fahrenheit é", F, "graus"

FIM
```

#### Teste de mesa (0.5 ponto)

| C  | F  | saída                                  | 
| -- | -- | --                                     |
| 0  | 32 | A temperatura em Fahrenheit é 32 graus |

### Exercício 03 (2.5 pontos)
Receba dois números reais e um operador e efetue a operação correspondente com os valores recebidos (operandos). 
O algoritmo deve retornar o resultado da operação selecionada simulando todas as operações de uma calculadora simples.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{"Operações válidas: 1(soma), 2(subtração), 3(multiplicação) e 4(divisão)"}}
B --> C{{Digite uma operação:}}
C --> D[/op/]
D --> E{{Digite um número:}}
E --> F[/num1/]
F --> G{{Digite outro número:}}
G --> H[/num2/]
H --> I{op == 1}
I --FALSE--> J{op == 2}
J --FALSE--> L{op == 3}
L --FALSE--> O{op == 4}
O --FALSE--> Q{{Operação inválida!}}
Q --> R([FIM])
I --TRUE--> M[res = num1 + num2]
M --> S{{num1, + , num2, =, res}}
J --TRUE--> K[res = num1 - num2]
K --> T{{num1, - , num2, =, res}}
L --TRUE--> N[res = num1 * num2]
N --> U{{num1, * , num2, =, res}}
O --TRUE--> P{num2 != 0}
P --FALSE--> X{{Impossível dividir!}}
P --TRUE--> Z[res = num1 / num2]
Z --> V{{num1, / , num2, =, res}}
X --> R
S --> R
T --> R
U --> R
V --> R
```

#### Pseudocódigo (1.0 ponto)

```java
ALGORITMO CalculadoraSimples
DECLARE op: INTEIRO; num1,num2,res: REAL

INICIO

    // Exibe a mensagem com as operações válidas 

    ESCREVA "Operações válidas: 1(soma), 2(subtração), 3(multiplicação) e 4(divisão)"

    // Exibe a mensagem com a solicitação de um número ao usuário de 1 à 4 referente às operações

    ESCREVA "Digite uma operação:"

    // Armazena o valor de entrada na variável "op"

    LEIA op

    // Exibe a mensagem solicitando um número real o qual é atribuido à variável num1
    ESCREVA "Digite um número:"
    LEIA num1

    // Exibe a mensagem solicitando um número real o qual é atribuido à variável num2
    ESCREVA "Digite outro número:"
    LEIA num2

    // Executa as instruções sob a condição de um dos casos for verdadeiro
    ESCOLHA

        // Executa as instruções  sob a condição de op == 1  
        CASO op == 1

            // É atribuido à variável res o valor num1 + num2
            res = num1 + num2

            // Exibe a mensagem concatenando a variável num1, o caractere +, a variável num2, o caractere =, e a variável res nessa ordem. 
            ESCREVA num1, "+", num2, "=", res

        // Executa as instruções  sob a condição de op == 2  
        CASO op == 2

            // É atribuido à variável res o valor num1 - num2
            res = num1 - num2

            // Exibe a mensagem concatenando a variável num1, o caractere -, a variável num2, o caractere =, e a variável res nessa ordem. 
            ESCREVA num1, "-", num2, "=", res

        //Executa as instruções  sob a condição de op == 3  
        CASO op == 3

            // É atribuido à variável res o valor num1 * num2
            res = num1 * num2

            // Exibe a mensagem concatenando a variável num1, o caractere *, a variável num2, o caractere =, e a variável res nessa ordem.  
            ESCREVA num1, "*", num2, "=", res

        // Executa as instruções  sob a condição de op == 4  
        CASO op == 4

            // Executa as instruções  sob a condição de num2 != 0
            SE num2 != 0 ENTAO

                // É atribuido o valor num1 / num2 à variável res
                res = num1 / num2

                // Exibe a mensagem concatenando a variável num1, o caractere /, a variável num2, o caractere =, e a variável res nessa ordem.  
                ESCREVA num1, "/", num2, "=", res

            //  Executa as instruções  sob a condição de num2 != 0 ser falso
            SENAO
                ESCREVA "Impossível dividir!"

            FIM_SE

    // Executa as instruções  sob a condição de nenhum dos casos posteriores for verdadeiro.
    SENAO
        ESCREVA "Operação inválida!"

    FIM_ESCOLHA

FIM
```

#### Teste de mesa (0.5 ponto)

| num1 | num2 | op | num2 != 0 | res | saída               | 
| --   | --   | -- | --        | --  | --                  |
| 1    | 0    | 1  |           | 1   | 1 + 0 = 1           |
| 1    | 0    | 2  |           | 1   | 1 - 0 = 1           |
| 1    | 0    | 3  |           | 0   | 1 * 0 = 0           |
| 1    | 0    | 4  | False     |     | Impossível dividir! |
| 1    | 2    | 4  | True      | 0.5 | 1 / 2 = 0,5         |
| 1    | 2    | 5  |           |     | Operação inválida!  |

### Exercício 04 (2.5 pontos)
Elaborar um algoritmo que, dada a idade, classifique nas categorias: infantil A (5 - 7 anos), infantil B (8 -10 anos), juvenil A (11 - 13 anos), juvenil B (14 -17 anos) e adulto (maiores que 18 anos).

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{"Digite a idade do aluno:"}}
B --> C[/idade/]
C --> D{idade >=5 <br>E <br>idade <= 7}
D --FALSE--> F{idade >=8 <br>E <br>idade <= 10}
F --FALSE--> G{idade >=11 <br>E <br>idade <= 13}
G --FALSE--> H{idade >=14 <br>E <br>idade <= 17}
H --FALSE--> I{idade >=18}
I --FALSE--> P{{"Digite uma idade válida!"}}
P --> Z([FIM])
D --TRUE--> Q{{Infantial A}}
F --TRUE--> K{{"Infantial B"}}
G --TRUE--> L{{Juvenil A}}
H --TRUE--> M{{Juvenil B}}
I --TRUE--> N{{Adulto}}
Q --> Z
K --> Z
L --> Z
M --> Z
N --> Z
```

#### Pseudocódigo (1.0 ponto)

```
ALGORTIMO ClassificaCategoria
DECLARE idade: INTEIRO

INICIO

    // Exibe a mensagem com a solicitação de um número (da idade) ao usuário
    ESCREVA "Digite a idade do aluno:"

    //  Armazena o valor de entrada na variável "idade"
    LEIA idade

    //  Executa as instruções sob a condição de um dos casos for verdadeiro
    ESCOLHA

        // Executa as instruções  sob a condição de idade >=5 e idade <= 7
        CASO idade >=5 E idade <= 7

            // Exibe a mensagem com a categoria do aluno conforme a idade deste
            ESCREVA "Infantial A"

        // Executa as instruções  sob a condição de idade >=8 e idade <= 10
        CASO idade >=8 E idade <= 10

            // Exibe a mensagem com a categoria do aluno conforme a idade deste
            ESCREVA "Infantial B"

        // Executa as instruções  sob a condição de idade >=11 e idade <= 13
        CASO idade >=11 E idade <= 13

            // Exibe a mensagem com a categoria do aluno conforme a idade deste
            ESCREVA "Juvenil A"

        // Executa as instruções  sob a condição de idade >=14 e idade <= 17
        CASO idade >=14 E idade <= 17

            // Exibe a mensagem com a categoria do aluno conforme a idade deste
            ESCREVA "Juvenil B"

        // Executa as instruções  sob a condição de idade >=18 
        CASO idade >=18

            // Exibe a mensagem com a categoria do aluno conforme a idade deste
            ESCREVA "Adulto"

    // Executa as instruções  sob a condição de a variavel idade não for válida.
    SENAO

        // Exibe a mensagem caso a idade inserida não seja válida
        ESCREVA "Digite uma idade válida!"

    FIM_ESCOLHA

FIM
```

#### Teste de mesa (0.5 ponto)

| idade | idade >=8 E idade <= 10 | idade >=11 E idade <= 13 | idade >=14 E idade <= 17 | idade >=18 | saída                       | 
| --    | --                      | --                       | --                       | --         | --                          |
| 4     | False                   | False                    | False                    | False      | Digite uma idade válida!    |
| -4    | False                   | False                    | False                    | False      | Digite uma idade válida!    |
| 8     | True                    | False                    | False                    | False      | Infantial A                 |
| 11    | False                   | True                     | False                    | False      | Infantial B                 |
| 17    | False                   | False                    | True                     | False      | Infantial C                 |
| 21    | False                   | False                    | False                    | True       | Adulto                      |
