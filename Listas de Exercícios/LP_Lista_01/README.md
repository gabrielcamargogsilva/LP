![senai_logo](https://transparencia.sp.senai.br/Content/img/logo-senai.png)

# Lista de Exercícios 01: Fluxogramas

Profº.: Cainã Antunes Silva  
Faculdade de Tecnologia **SENAI Sorocaba**  
Tecnólogo em Análise e Desenvolvimento de Sistemas (ADS)
___


> O objetivo desta aula é exercitar o raciocínio lógico para a criação de algoritmos através de fluxogramas.  

O fluxo de um algorítmo poder ser representado graficamente através de fluxogramas. Um conjunto de símbolos, representam cada ação realizada pelo programa, além disso, setas conectam estes símbolos uns com os outros indicando a sequencia em que as ações são executadas.

Para mais informações acesse [Aula 01: Fluxogramas.](https://www.notion.so/cainaantunes/Aula-01-Fluxogramas-188bde521b3b80de90f7dbd9407af71e)

***

1. Crie o fluxograma de um programa que solicita que o usuário digite sua nota e em seguida o programa exibe se o aluno foi “Aprovado” ou “Reprovado”. Leve em consideração que a nota deve estar entre 0 e 100 e que a condição para aprovação é ter uma nota igual ou superior à 50.
   
    ```mermaid
   
    flowchart TD
        start(( Início )) --> input[\ Digite sua Nota \]
        input --> verification{ Nota >= 50? }
        verification --> |Sim| A[/ Aprovado /]
        verification --> |Não| B[/ Reprovado /]
        A --> finish([ Fim ])
        B --> finish
    ```
   
2. Altere o exemplo anterior, acrescentando as seguintes condições: para ser o aprovado, o aluno precisar ter nota igual ou superior à 50 e frequência igual ou superior a 75%.
   
   ```mermaid
   flowchart TD
    start(( Início )) --> input1[\ Digite sua Nota \]
    input1 --> input2[\ Digite sua frequência \]
    
    input2 --> checkNota{ Nota >= 50? }

    checkNota --> |Sim| checkFreq{ Frequência >= 75%? }
    
    checkFreq --> |Sim| aprovado[/ Aprovado /]
    checkFreq --> |Não| reprovadoFreq[/ Reprovado por falta /]

    checkNota --> |Não| reprovadoNota[/ Reprovado por nota /]

    aprovado --> finish([ Fim ])
    reprovadoFreq --> finish
    reprovadoNota --> finish
   ```
   
3. Crie um fluxograma para calcular a soma de dois números fornecidos pelo usuário.
   
   ```mermaid
   flowchart TD
    A(( Início )) --> B[\ Digite o primeiro número \]
    B --> C[\ Digite o segundo número \]
    C --> D[ Resultado = N1 + N2 ]
    D --> E[/ Mostrar Resultado /]
    E --> F([ Fim ])
   ```
   
4. Elabore um fluxograma que leia um número e exiba se ele é positivo ou negativo.
   
   ```mermaid
   flowchart TD
      A((Início)) --> input[\Digite um número\]
      input -->checkNum{Número >= 0?}

      checkNum --> |Sim| aprovado[/Esse número é positivo/]
      checkNum --> |Não| reprovado[/Esse número é negativo/]
      aprovado --> Finish([Fim])
      reprovado --> Finish([Fim])

   ```
   
5. Desenvolva um fluxograma que leia a idade de uma pessoa e indique se ela pode votar.
   
   ```mermaid
   flowchart TD
      D((Início)) --> input[\Digite sua idade \]
      input --> checkIdade{Idade >= 16?}
      checkIdade --> |Sim| aprovado[/Você pode votar/]
      checkIdade --> |Não| reprovado[/Você não pode votar/]
      aprovado --> Finish([Fim])
      reprovado --> Finish([Fim])
   ```
   
6. Crie um fluxograma que leia dois números e determine o maior entre eles.
   
   ```mermaid
   flowchart TD
      E((Início)) --> input[\Digite o primeiro número\]
      input --> input2[\Digite o segundo número\]
      input2 --> checkNum{N1 > N2?}
      checkNum --> |Sim| printN1[/Número 1 é maior/]
      checkNum --> |Não| printN2[/Número 2 é maior/]
      printN1 --> Finish([Fim])
      printN2 --> Finish([Fim])
   ```
   
7. Crie um fluxograma que leia três números e determine o maior entre eles.
   
   ```mermaid
   flowchart TD
    start(( Início )) --> input1[\ Digite N1, N2 e N3 \]
    input1 --> check1{N1 > N2?}
    check1 -- Sim --> check2{N1 > N3?}
    check2 -- Sim --> printN1[/ N1 é o maior /]
    check2 -- Não --> printN3_1[/ N3 é o maior /]
    check1 -- Não --> check3{N2 > N3?}
    check3 -- Sim --> printN2[/ N2 é o maior /]
    check3 -- Não --> printN3_2[/ N3 é o maior /]
    printN1 --> finish([ Fim ])
    printN2 --> finish
    printN3_1 --> finish
    printN3_2 --> finish
   ```
   
8. Construa um fluxograma para calcular o fatorial de um número fornecido pelo usuário.
   
   ```mermaid
   flowchart TD
      G(( Início )) --> input[\ Digite um número N \]
      input --> init[ fatorial = 1 ]
      
      init --> check{ N > 1? }
      
      
      check -- Sim --> calc[ fatorial = fatorial * N ]
      calc --> decrement[ N = N - 1 ]
      decrement --> check
      
      check -- Não --> output[/ Exibir fatorial /]
      output --> finish([ Fim ])
   ```
   
9. Elabore um fluxograma para verificar se um número digitado pelo usuário é par.
   
   > Em várias linguagens de programação, o operador % retorna o resto da divisão entre dois números.    
   > 
   >**Exemplos**:  
   > - 9 % 2 = 1  
   > - 11 % 3 = 2
   
   ```mermaid
   flowchart TD
    A(( Início )) --> input[\ Digite um número N \]
    input --> checkNum{ N % 2 == 0? }
    
    checkNum -- Sim --> par[/ O número é PAR /]
    checkNum -- Não --> impar[/ O número é ÍMPAR /]
    
    par --> Finish([ Fim ])
    impar --> Finish
   ```
   
10. Elabore um fluxograma para verificar se um número digitado pelo usuário é primo.
   
   ```mermaid
   flowchart TD
    A(( Início )) --> input[\ Digite um número N \]
    input --> checkNum{ N < 2? }
    
    
    checkNum -- Sim --> No[/ Não é Primo /]
    
   
    checkNum -- Não --> D[ divisor = 2 ]
    D --> E{ divisor < N? }
    
    
    E -- Sim --> F{ N % divisor == 0? }
    F -- Sim --> No
    F -- Não --> G[ divisor = divisor + 1 ]
    G --> E
    
    
    E -- Não --> Yes[/ É Primo /]
    
    No --> Finish([ Fim ])
    Yes --> Finish
   ```