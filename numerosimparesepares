```mermaid 
flowchart TD

A([Ínicio])-->B{{Digite um número:}}

B --> C[/numero/]

C -->D{numero < 0} 

D --F-->E{{o numero não pode ser negativo ou zero!}}
D --V-->F[Resto=número %2]
F-->G{Resto = 0}
G--S-->H{{É par}}
G--Ñ-->I{{Não é par}}
H-->J([Fim])
I-->J([Fim])
E-->J([Fim])
```
```
ALGORITMO verifica_par_impar
DECLARE numero, resto INTEIRO
ESCREVA "Digite um número:"
LEIA numero
SE numero > 0 ENTAO
     resto = numero% 
     SE resto == 0 ENTAO
     ESCREVA "O número é par!"
     SENAO 
     ESCREVA "O número é ímpar"
SENAO
    ESCREVA"O número deve ser positivo"
FIM

