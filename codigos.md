```mermaid

flowchart TD
A([Ínicio])-->B{{Digite um número:}}

B --> C[/numero1/]
C --> D{{Digite outro número}}
D --> E[/numero2/]
E --> F{{Digite outro número}}
F --> G[/numero3/]
G --> H{{Digite um último número}}
H --> I[/numero4/]
I --> J[/ "(numero1 + numero 2+numero3 +numero4)/2" /]
J -->K ((Resultado))
K -->L ([Fim]) 

