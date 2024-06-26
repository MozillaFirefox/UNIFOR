# UNIFOR
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

#### Pseudocódigo
```java
ALGORTIMO verifica_par_impar
DECLARE numero, resto: INTEIRO

INICIO

    // Entrada do usuário de um número inteiro qualquer armezando na variável "numero"
    ESCREVA "Digite um número: "
    
    // Dado de entrada armazenado na variável numero
    LEIA numero
    
    //Executa as instruções sob a condição "numero >= 0" for verdadeira
    SE numero >= 0 ENTAO

        // O resto da divisão por 2 da variável 'numero' é atribuido na variável "resto"
        resto <- numero % 2

        // Executa a instrução de exibir "O número é par" sob a condição "resto == 0" é verdadeira
        SE resto == 0 ENTAO
            ESCREVA "O número é par!"

        //Executa a instrução de exibir "O número é ímpar" sob a condição "resto == 0" é falsa
        SENAO
          ESCREVA "O número é impar!"

        FIM_SE

    //Executa a instrução de exibir "O número deve ser positivo" sob a condição "numero >= 0" é falsa
    SENAO             
        ESCREVA "O número deve ser postivo!"

    FIM_SE

FIM
```

#### Tabela de testes (0,25 ponto)
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
A([INICIO]) --> B{{"Digite seu salário atual:"}}
B --> C[/sal_atual/]
C --> D{sal_atual <= 500}
D --FALSE--> E[sal_reaj = sal_atual * 1.1]
D --TRUE--> F[sal_reaj = sal_atual * 1.2]
E --> G{{O novo salário é, sal_reaj}}
F --> G
G --> H([FIM])
```

#### Pseudocódigo (1.0 ponto)

```java
ALGORTIMO ReajusteSalario
DECLARE sal_atual, sal_reaj: REAL

INICIO

    // Exibe a mensagem com a solicitação de um número real ao usuário
    ESCREVA "Digite seu salário atual:"

    // Dado de entrada armazenado na variável sal_atual
    LEIA sal_atual

    // Executa a instrução de atribuir o valor ´sal_atual*1.2´ à variável 'sal_reaj' sob a condição "sal_atual <= 500" é verdadeira
    SE sal_atual <= 500 ENTAO
        sal_reaj = sal_atual * 1.2

    // Executa a instrução de atribuir o valor ´sal_atual*1.1´ à variável 'sal_reaj' sob a condição "sal_atual <= 500" é falsa
    SENAO
        sal_reaj = sal_atual * 1.1

    FIM_SE

    //  Exibe a mensagem concatenando aos caracteres "O novo salário é R$" com a variável "sal_reaj".
    ESCREVA "O novo salário é R$", sal_reaj

FIM
```

#### Tabela de testes (1.0 ponto)

| sal_atual | sal_atual >= 500 |sal_reaj       | saída                   | 
| --        | --               | --            | --                      | 
| 400       | False            | 400*1.2 = 480 | O novo salário é R$ 480 |
| 500       | True             | 500*1.2 = 600 | O novo salário é R$ 600 |
| 600       | True             | 600*1.1 = 660 | O novo salário é R$ 660 |

## Exercício 03 (3 pontos)
Represente, em fluxograma e pseudocódigo, um algoritmo para calcular a média aritmética entre duas notas de um aluno e mostrar sua situação, que pode ser aprovado ou reprovado.

#### Fluxograma (1 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{"Digite a nota 1:"}}
B --> C[/nota1/]
C --> D{{"Digite a nota 2:"}}
D --> E[/nota2/]
E --> F{nota1 >= 0<br> OU <br>nota2 >= 0}  
F --FALSE--> K{{"A nota deve ser maior que zero!"}}
K --> L([FIM])
F --TRUE--> G["media = (nota1 + nota2)/2"]
G --> H{media >= 7}
H --FALSE--> I{{"O aluno está reprovado!"}}
H --TRUE--> J{{"O aluno está aprovado!"}}
I --> L
J --> L
```

#### Pseudocódigo (1 ponto)

```java
ALGORTIMO SituacaoAluno
DECLARE nota1, nota2, media: REAL

INICIO

    // Exibe a mensagem de entrada para o valor da variável nota1
    ESCREVA "Digite a nota 1:"

    // Dado de entrada armazenado na variável nota1
    LEIA nota1

    // Exibe a mensagem de entrada para o valor da variável nota2
    ESCREVA "Digite a nota 2:"

    // Dado de entrada armazenado na variável nota2
    LEIA nota2

    // Executa as instruções sob a condição "nota1 >= 0 E nota2 >= 0" é verdadeira
    SE nota1 >= 0 E nota2 >= 0 ENTAO

        // O valor de (nota1 + nota2)/2 é atribuido na variável "média"

        media =  (nota1 + nota2)/2

        //   Executa as instruções sob a condição "media >= 7" é verdadeira
        SE media >= 7 ENTAO
            ESCREVA "O aluno está aprovado!"

        // Executa as instruções sob a condição "media >= 7" é falsa
        SENAO
          ESCREVA  "O aluno está reprovado!"

        FIM_SE

    //  Executa as instruções sob a condição "nota1 >= 0 E nota2 >= 0" é falsa
    SENAO
        ESCREVA "A nota deve ser maior que zero!"

    FIM_SE

FIM
```

#### Tabela de testes (1 ponto)

| nota1 | nota2 | nota1 >= 0 E nota2 >= 0 | media        | saĩda | 
| --    | --    | --                      | --           | --    | 
| -1    | 0     | False                   |              | A nota deve ser maior que zero! | 
| 0     | 0     | True                    | (0+0)/2 = 0  | O aluno está reprovado!|
| 4     | 8     | True                    | (4+8)/2 = 6  | O aluno está reprovado!|
| 4     | 10    | True                    | (4+10)/2 = 7 | O aluno está aprovado!|

## Exercício 04 (3 pontos)
Represente, em fluxograma e pseudocódigo, um algoritmo que, a partir da idade do candidato(a), determinar se pode ou não tirar a CNH. 
Caso não atender a restrição de idade, calcular quantos anos faltam para o candidato estar apto.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{"Digite a sua idade:"}}
B --> C[/idade/]
C --> D{idade < 0}
D --FALSE--> E{idade >= 18}
E --FALSE--> F[anos_apto = 18 - idade]
F --> G{{Faltam, anos_apto, anos para o candidato estar apto!}}
G --> H([FIM])
E --TRUE--> I{{"O candidato está apto a tirar a CNH!"}}
I --> H
D --TRUE--> J{{"A idade deve ser maior que zero!"}}
J --> H 
```

#### Pseudocódigo (1.0 ponto)

```java
ALGORTIMO AptoCNH
DECLARE idade, anos_apto: INTEIRO

INICIO

    // Exibe a mensagem com a solicitação de um número inteiro ao usuário
    ESCREVA ""Digite a sua idade:"

    // Dado de entrada armazenado na variável idade 
    LEIA idade

    //  Executa a instrução sob a condição "idade <= 0" é verdadeira
    SE idade < 0 ENTAO
        ESCREVA "A idade deve ser maior que zero!"

    // Executa as instruções sob a condição "idade <= 0" é falso
    SENAO

        // Executa a instrução de exibir "O candidato está apto a tirar a CNH!" sob a condição "idade >= 18" é verdadeira
        SE idade >= 18 ENTAO
            ESCREVA "O candidato está apto a tirar a CNH!"

        // Executa as instruções sob a condição "idade >= 18" é falso
        SENAO

            // O valor 18 - idade é atribuido à variável anos_apto
            anos_apto <- 18 - idade

            // Exibe a mensagem de quantos anos faltam para o candidato estar apto  .
            ESCREVA "Faltam", anos_apto, "ano(s) para o candidato estar apto!"

        FIM_SE

    FIM_SE

FIM
```

#### Tabela de testes (1.0 ponto)

| idade | idade < 0 | idade >= 18 | anos_apto | saída                                         | 
| --    | --        | --          | --        | --                                            | 
| -1    | True      |             |           |                                               |
| 0     | False     | False       | 18-0 = 18 | Faltam 18 ano(s) para o candidato estar apto! |
| 17    | False     | False       | 18-17 = 1 | Faltam 1 ano(s) para o candidato estar apto!  |
| 18    | False     | True        |           | O candidato está apto a tirar a CNH!          |
