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

| salariovelho | salariovelho < 0 | salariovelho =< 500 | saída |  
| -- | -- | -- | -- | -- |
|      -1     |     T      |      --     |      O seu salário novo é 0      | 
| 500    | F    | T   |  O seu salário novo é 600   |
| 1000   | F         | F        | O seu salário novo é 1100 | 

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

| nota1| nota2 | media | saída |  | 
|      -1      |      --      |      --      |    Nota inválida    |     
| 7   | -1       | --   |  Nota inválida    |     
| 7   | 7          | 7      | Você foi aprovado | 
| 7|6.5|6.75|Você foi reprovado|
## Exercício 04 (3 pontos)
Represente, em fluxograma e pseudocódigo, um algoritmo que, a partir da idade do candidato(a), determinar se pode ou não tirar a CNH. 
Caso não atender a restrição de idade, calcular quantos anos faltam para o candidato estar apto.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite sua idade aqui"
B-->C[\idade\]
C-->D{idade < 18}
D--T-->E
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
9 ESCREVA "Faltam"faltam"anos para você poder tirar a CNH"
10SENAO
11ESCREVA"Você pode tirar a CNH"
12 FIM_SE
13FIM_ALGORITMO

```

#### Teste de mesa (1.0 ponto)

| nome_coluna1 | nome_coluna2 | nome_coluna3 | nome_coluna4 | nome_coluna5 | 
|      --      |      --      |      --      |      --      |      --      | 
| Adicione     | espaço       | se quiser    |  alinhar     | as barras    |
| verticais,   | mas          | não é        | obrigatório. | Entendido ?  |



