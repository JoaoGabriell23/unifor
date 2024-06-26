
**Curso:** Engenharia Civil <br>
**Disciplina:** Raciocinio Lógico e ALgorítimo <br>
**Código/Turma:** T998-21 <br>
**Professor:** Ricardo Carubbi <br>
**Data:** 02/04 <br>
**Aluno(a):** Joao Gabriel Lemos Gomes <br>
**Matrícula:** 2410597 <br>

**1a chamada (Sim/Não):** não <br>
**2a chamada (Sim/Não):** sim <br>

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
A([INICIO]) --> B{{"Digite o valor de A"}}
B --> C[/A/]
C --> D{{"Digite o valor de B"}}
D --> E[/B/]
E --> F(Mem = B)
F --> G(B = A)
G --> H(A = Mem)
H --> I{{A, B}}
I --> J([FIM])
```

#### Pseudocódigo (1 ponto)
```
Algoritmo TrocaValores
DECLARE A, B, Mem: float// declara as variaveis e o ponto de flutuacão 
INICIO
ESCREVA "Digite o valor de A"
LEIA A // variavel que atribui o valor a a
ESCREVA "Digite o valor de B"
LEIA B // variavel atribui o valor a b
Mem = B // armazena o valor de b
B = A // atribui o valor A a b
A = Mem // fazendo a trocan de valores
ESCREVA A, B
FIM_ALGORITMO
```
#### Teste de mesa

| A  | B | Mem = B | B = A | A = Mem | Saida |
| -- | -- | -- | -- | -- | -- |
| 10 | 4 | 4 | 10 | 4 | 4, 10

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
A([INICIO])
A --> C[N_aprov = 0]
C --> D{{Digite a quanidade de notas para avaliar}}
D --> E[/N_notas/]
E --> F{N_notas > 0}
F --FALSE--> G{{Digite uma quantidade válida}}
G --> E
F --TRUE--> H{N_notas = N_ver}
H --TRUE--> I{{A quantidade de notas aprovadas foi N_aprov}}
H --FALSE--> J{{Insira a nota}}
J --> K[/nota/]
K --> L{nota >= 50 e nota <= 100}
L --TRUE--> M[N_aprov =+ 1]
M --> N[N_ver =+ 1]
L --FALSE--> N
N --> H
I --> Z([FIM])
```
#### Pseudocódigo 01 (1 ponto)

```
Algoritmo aprovação
DECLARE N_ver, N_aprov, N_notas, i: Int  // Declaração de variáveis: 
	notas: Float                        // Declaração da variável notas como ponto flutuante
INICIO
N_aprov = 0                            
ESCREVA "Digite a quantidade de notas para avaliar" 
LEIA N_notas                            // variavel sobre a quantidade de notas avaliadas
ENQUANTO N_notas <= 0 REPITA            // Enquanto o número de notas for menor ou igual a 0
	ESCREVA "Digite uma quantidade válida"    // Exibe uma mensagem de erro
	LEIA N_notas                     
PARA N_ver DE 1 ATÉ N_notas FAÇA [PASSO 1] // Loop de 1 até N_notas, com passo 1
	ESCREVA "Insira a nota"                   
	LEIA nota                       
	SE nota >= 50 E nota <= 100               // Se a nota estiver entre 50 e 100
		N_aprov =+ 1                             // Incrementa o contador de notas aprovadas
		N_ver =+ 1                               // Incrementa o contador de notas verificadas
	SENÃO                                   
		N_ver =+ 1                               // Apenas incrementa o contador de notas verificadas
	FIM_SE                                   // Fim da estrutura condicional SE
FIM_PARA                                 // Fim do loop PARA
ESCREVA "A quantidade de notas aprovadas foi", N_aprov
FIM_ALGORÍRIMO                           

```

#### Teste de mesa 01
##### Chat GPT
| Iteração | Ação                                              | Entrada/Saída  | N_aprov | N_ver |
|----------|---------------------------------------------------|----------------|---------|-------|
|         | **Inicialização das Variáveis**                   |                | 0       | 0     |
|         | **Entrada do Número de Notas**                    | 5              |         |       |
| 1        | Mensagem: "Insira a nota"                         |                |         |       |
|          | Entrada: nota                                     | 70             |         |       |
|          | Condição SE: 70 >= 50 e 70 <= 100 (verdadeiro)   |                |         |       |
|          |  N_aprov += 1                                    |                | 1       | 1     |
|          |  N_ver += 1                                      |                |         | 1     |
| 2        | Mensagem: "Insira a nota"                         |                |         |       |
|          | Entrada: nota                                     | 30             |         |       |
|          | Condição SE: 30 >= 50 e 30 <= 100 (falso)        |                |         |       |
|          |  N_ver += 1                                      |                |         | 2     |
| 3        | Mensagem: "Insira a nota"                         |                |         |       |
|          | Entrada: nota                                     | 85             |         |       |
|          | Condição SE: 85 >= 50 e 85 <= 100 (verdadeiro)   |                |         |       |
|          |  N_aprov += 1                                    |                | 2       | 3     |
|          |  N_ver += 1                                      |                |         | 3     |
| 4        | Mensagem: "Insira a nota"                         |                |         |       |
|          | Entrada: nota                                     | 95             |         |       |
|          | Condição SE: 95 >= 50 e 95 <= 100 (verdadeiro)   |                |         |       |
|          |  N_aprov += 1                                    |                | 3       | 4     |
|          |  N_ver += 1                                      |                |         | 4     |
| 5        | Mensagem: "Insira a nota"                         |                |         |       |
|          | Entrada: nota                                     | 40             |         |       |
|          | Condição SE: 40 >= 50 e 40 <= 100 (falso)        |                |         |       |
|          |  N_ver += 1                                      |                |         | 5     |
| -        | **Saída de Resultados**                           |                |         |       |
| -        | Mensagem: "A quantidade de notas aprovadas foi 3"|                |         |       |

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
A([INICIO])
A --> C[soma = 0]
C --> D{{Digite o número de elementos do conjunto que você quer somar}}
D --> E[/num_som/]
E --> F{num_som > 0}
F--FALSE--> G{{Digite uma quantidade válida}}
G --> E
G --TRUE--> H{num_som = num_somados}
H --FALSE--> I{{Digite um número}}
I --> J[/num/]
J --> K[soma = soma + num]
K --> L[num_somados =+ 1]
L --> H
H --TRUE--> M{{A valor da soma total é soma}}
M --> N([FIM])
```

#### Pseudocódigo (1 ponto)
```
Algoritmo soma_de_valores
DECLARE num_somados, num_soma: Int        // Declaração de variáveis
	num, soma: Float                   // Declarando que numeros sao reais
INICIO
soma = 0                                 // Inicio da variável soma com 0
ESCREVA "Digite o número de elementos do conjunto que você quer somar" 
LEIA num_soma                            // Lê a variavel para quantidade de numeros que o usuario que adicionar
ENQUANTO num_soma <= 0 FAÇA              // e um loop condional o número tem que ser  menor ou igual a 0
	ESCREVA "Digite uma quantidade válida"   // Exibe uma mensagem de erro para o usuário 
	LEIA num_soma                    
FIM_ENQUANTO                            // Fim do loop 
PARA num_somados DE 1 até Num_soma [PASSO 1] FAÇA // Loop de 1 até num_soma, com passo 1
	ESCREVA "Digite um número"       
	LEIA num                         
	soma =+ num                           // Adiciona o número à variável soma
FIM_PARA                                // Fim do loop para
ESCREVA "O valor da soma total é", soma  
FIM_ALGORITMO                           
```

#### Teste de mesa
##### Chat GPT

| Iteração | Ação                                              | Entrada/Saída | soma | num_somados |
|----------|---------------------------------------------------|---------------|------|-------------|
| -        | **Inicialização das Variáveis**                   |               | 0    | 0           |
| -        | **Entrada do Número de Elementos a Somar**        | 7             |      |             |
| 1        | Mensagem: "Digite um número"                      |               |      |             |
|          | Entrada: num                                      | 0.5           |      |             |
|          |  soma += num                                     |               | 0.5  |             |
|          |  num_somados += 1                                |               |      | 1           |
| 2        | Mensagem: "Digite um número"                      |               |      |             |
|          | Entrada: num                                      | -1.25         |      |             |
|          |  soma += num                                     |               | -0.75|             |
|          |  num_somados += 1                                |               |      | 2           |
| 3        | Mensagem: "Digite um número"                      |               |      |             |
|          | Entrada: num                                      | 2.75          |      |             |
|          |  soma += num                                     |               | 2    |             |
|          |  num_somados += 1                                |               |      | 3           |
| 4        | Mensagem: "Digite um número"                      |               |      |             |
|          | Entrada: num                                      | 0             |      |             |
|          |  soma += num                                     |               | 2    |             |
|          |  num_somados += 1                                |               |      | 4           |
| 5        | Mensagem: "Digite um número"                      |               |      |             |
|          | Entrada: num                                      | -3.5          |      |             |
|          |  soma += num                                     |               | -1.5 |             |
|          |  num_somados += 1                                |               |      | 5           |
| 6        | Mensagem: "Digite um número"                      |               |      |             |
|          | Entrada: num                                      | 1.75          |      |             |
|          |  soma += num                                     |               | 0.25 |             |
|          |  num_somados += 1                                |               |      | 6           |
| 7        | Mensagem: "Digite um número"                      |               |      |             |
|          | Entrada: num                                      | -2.25         |      |             |
|          |  soma += num                                     |               | -2    |             |
|          |  num_somados += 1                                |               |      | 7           |
| -        | **Saída de Resultados**                           |               |      |             |
| -        | Mensagem: "O valor da soma total é -2"            |               |      |             |


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
A([INICIO]) --> B[S = 0]
B --> D{{Digite a quantidade de termos da série que voce quer somar}}
D --> E[/Num_termo/]
E --> F{Num_termo > 0}
F --FALSE--> G{{Digite uma quantidade válida}}
G --> E
F --TRUE--> H{Num_termo = termo}
H --FALSE--> I[termo =+ 1]
I --> J["S =+ (2 * termo - 1)/(2 * termo)"]
J --> H
H --TRUE--> K{{"O valor da soma de Num_termos termo(s) da série é S"}}
K --> L([FIM])
```

#### Pseudocódigo (1 ponto)

```
Algoritmo soma_da_serie
DECLARE Num_termo, termo: Int   // Declaração das variáveis
    S: Float                    // Declaração da variável S como número de ponto flutuante
INICIO
S = 0                           
ESCREVA "Digite a quantidade de termos da série que você quer somar"   
LEIA Num_termo                  // Lê o número de termos que foi adicionado pelo usuario
ENQUANTO Num_termo < 0 FAÇA      // Enquanto o número de termos for menor que 0
    ESCREVA "Digite uma quantidade válida"   // Exibe uma mensagem de errro
    LEIA Num_termo               // Lê de novo a variavel 
FIM_ENQUANTO                   
PARA termo DE 1 ATÉ Num_termo [PASSO 1] FAÇA   // Loop de 1 até o número de termos da série, com passo 1
    S =+ (2 * termo - 1)/(2 * termo)          
FIM_PARA                        // Fim do loop para
ESCREVA "O valor da soma de", Num_termo, "termo(s) da série é", S   
FIM_ALGORITMO                  

```

#### Teste de mesa (0.25 ponto)
##### Chat GPT

| Iteração | Ação                                                 | Entrada/Saída | S     |
|----------|------------------------------------------------------|---------------|-------|
| -        | **Inicialização das Variáveis**                      |               | 0     |
| -        | **Entrada do Número de Termos da Série**            |               |       |
| 1        | Mensagem: "Digite a quantidade de termos da série"  |               |       |
|          | Entrada: Num_termo                                   |               | -3    |
|          |                                                      |               |       |
| 2        | **Verificação do Número de Termos**                  |               |       |
|          | Enquanto Num_termo < 0 FAÇA                         |               |       |
|          |   Mensagem: "Digite uma quantidade válida"          |               |       |
|          |   Entrada: Num_termo                                 |               |       |
|          | FIM_ENQUANTO                                        |               |       |
|          |                                                      |               |       |
| -        | **Saída de Resultados (Nenhum Cálculo Realizado)**  |               |       |
| -        | Mensagem: "O valor da soma de -3 termo(s) da série é" |             |       |
|          |                  0                                   |               |       |


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
A([INICIO]) --> B[fato = 1]
B --> R[n_mult = 0]
R-->C{{Digite o numero do fatorial que voce quer calcular}}
C --> D[/n/]
D --> E{n >= 0}
E --FALSE--> F{{Digite um fatorial válido}}
F --> D
E --TRUE--> G{n = n_mult}
G --FALSE--> H[n_mult =+ 1]
H --> I[fato = fato * n_mult]
I --> G
G --TRUE--> Y{{O valor do fatorial de n é fato}}
Y --> Z([FIM]) 
```
#### Pseudocódigo (2 pontos)

```
Algoritmo fatorial
DECLARE fato, n_mult, n: Int       // Declaração das variáveis
INICIO
n_mult = 0                         
ESCREVA "Digite o numero do fatorial que voce quer calcular" 
LEIA n                              // Lê o número digitado pelo usuario
ENQUANTO n < 0 FAÇA                 // Enquanto o número for menor que 0
    ESCREVA "Digite um fatorial válido"   // Exibe uma mensagem de erro
    LEIA n                          
FIM_ENQUANTO                        // Fim do loop 
PARA n_mult DE 1 PARA n [PASSO 1] FAÇA  // Loop de 1 até o número digitado pelo usuário
    n_mult =+ 1                        // Incrementa  n_mult
    fato = fato * n_mult               // Calcula o fatorial multiplicando fato pelo contador n_mult
FIM_PARA                           
ESCREVA "O valor do fatorial de", n, "é", fato   
FIM_ALGORITMO                       

```

#### Teste de mesa

##### Chat GPT
| Iteração | Ação                                                          | Entrada/Saída | fato | n_mult |
|----------|---------------------------------------------------------------|---------------|------|--------|
| -        | **Inicialização das Variáveis**                               |               | 0    | 0      |
| -        | **Entrada do Número para o Cálculo do Fatorial**             |               |      |        |
| 1        | Mensagem: "Digite o número do fatorial que você quer calcular"|               |      |        |
|          | Entrada: n                                                    |               | -50  |        |
|          |                                                               |               |      |        |
| 2        | **Verificação da Validade do Número**                         |               |      |        |
|          | Mensagem: "Digite um fatorial válido"                         |               |      |        |
|          | Entrada: n                                                    |               | -50  |        |
|          |                                                               |               |      |        |
| -        | **Saída do Resultado**                                        |               |      |        |
| -        | (nenhuma saída, pois o número não é válido)                   |               |      |        |

| Iteração | Ação                                                          | Entrada/Saída | fato | n_mult |
|----------|---------------------------------------------------------------|---------------|------|--------|
| -        | **Inicialização das Variáveis**                               |               | 1    | 0      |
| -        | **Entrada do Número para o Cálculo do Fatorial**             |               |      |        |
| 1        | Mensagem: "Digite o número do fatorial que você quer calcular"|               |      |        |
|          | Entrada: n                                                    |               | 1    |        |
|          |                                                               |               |      |        |
| 2        | **Verificação da Validade do Número**                         |               |      |        |
|          | (nenhuma ação necessária, 0 é válido)                         |               |      |        |
|          |                                                               |               |      |        |
| -        | **Saída do Resultado**                                        |               |      |        |
| -        | Mensagem: "O valor do fatorial de 0 é 1"                      |               | 1    |        |

| Iteração | Ação                                                          | Entrada/Saída | fato | n_mult |
|----------|---------------------------------------------------------------|---------------|------|--------|
| -        | **Inicialização das Variáveis**                               |               | 1    | 0      |
| -        | **Entrada do Número para o Cálculo do Fatorial**             |               |      |        |
| 1        | Mensagem: "Digite o número do fatorial que você quer calcular"|               |      |        |
|          | Entrada: n                                                    |               | 6    |        |
|          |                                                               |               |      |        |
| 2        | **Verificação da Validade do Número**                         |               |      |        |
|          | (nenhuma ação necessária, 6 é válido)                         |               |      |        |
|          |                                                               |               |      |        |
| 3        | **Cálculo do Fatorial**                                       |               |      |        |
|          | n_mult = 1                                                    |               |      | 1      |
|          | fato = fato * n_mult                                          |               | 1    | 1      |
|          |                                                               |               |      |        |
| 4        | n_mult = 2                                                    |               |      | 2      |
|          | fato = fato * n_mult                                          |               | 1    | 2      |
|          |                                                               |               |      |        |
| 5        | n_mult = 3                                                    |               |      | 3      |
|          | fato = fato * n_mult                                          |               | 2    | 3      |
|          |                                                               |               |      |        |
| 6        | n_mult = 4                                                    |               |      | 4      |
|          | fato = fato * n_mult                                          |               | 6    | 4      |
|          |                                                               |               |      |        |
| 7        | n_mult = 5                                                    |               |      | 5      |
|          | fato = fato * n_mult                                          |               | 24   | 5      |
|          |                                                               |               |      |        |
| 8        | n_mult = 6                                                    |               |      | 6      |
|          | fato = fato * n_mult                                          |               | 120  | 6      |
|          |                                                               |               |      |        |
| -        | **Saída do Resultado**                                        |               |      |        |
| -        | Mensagem: "O valor do fatorial de 6 é 720"                    |               | 720  |        |

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
Algoritmo fibonacci
DECLARE T1, T2, Tmem, TS, i: Int     // Declaração das variáveis 
INICIO
T1 = 0                              
T2 = 1                                
ESCREVA "Digite qual termo de fibonacci você quer calcular"   
LEIA TS                             // Lê a variavel 
ENQUANTO TS <= 0 FAÇA               // Enquanto o número do termo de Fibonacci for menor ou igual a 0
    ESCREVA "Digite um termo válido"   // Exibe uma mensagem de erro
    LEIA TS                         // Lê novamente o número do termo de Fibonacci
FIM_ENQUANTO                        // Fim do loop enquanto
PARA i DE 1 ATÉ TS [PASSO 1] FAÇA   // Loop de 1 até o termo de Fibonacci
    ESCREVA T1      
    Tmem = T1 + T2                  
    T1 = T2                         // Atualiza o primeiro termo (T1) com o valor do segundo termo anterior (T2)
    T2 = Tmem                       // Atualiza o segundo termo (T2) com o valor do termo temporário (Tmem)
FIM_PARA                           
FIM_ALGORITMO                       
```
#### Teste de mesa

| Iteração | Ação                                                             | Entrada/Saída | T1  | T2  | Tmem | TS |
|----------|------------------------------------------------------------------|---------------|-----|-----|------|----|
| -        | **Inicialização das Variáveis**                                  |               | 0   | 1   |      |    |
| -        | **Entrada do Termo de Fibonacci a ser calculado**               |               |     |     |      | 5  |
| 1        | Mensagem: "Digite qual termo de Fibonacci você quer calcular"   |               |     |     |      |    |
|          | Entrada: TS                                                      |               |     |     |      | 5  |
|          |                                                                  |               |     |     |      |    |
| 2        | **Verificação da Validade do Número**                            |               |     |     |      |    |
|          | (nenhuma ação necessária, 5 é válido)                           |               |     |     |      |    |
|          |                                                                  |               |     |     |      |    |
| 3        | **Cálculo do Termo de Fibonacci**                                |               |     |     |      |    |
|          | PARA i DE 1 ATÉ 5 [PASSO 1] FAÇA                                 |               |     |     |      |    |
|          |                                                                  |               |     |     |      |    |
| 4        | i = 1                                                            |               |     |     |      |    |
|          | Escreva: T1                                                      |               | 0   | 1   |      |    |
|          |                                                                  |               |     |     |     |    |
|          | Tmem = T1 + T2                                                   |               |     |     | 1     |    |
|          | T1 = T2                                                          |               | 1   |     |      |    |
|          | T2 = Tmem                                                        |               |     | 1   |      |    |
|          |                                                                  |               |     |     |      |    |
| 5        | i = 2                                                            |               |     |     |      |    |
|          | Escreva: T1                                                      |               | 1   | 1   |      |    |
|          |                                                                  |               |     |     |    |    |
|          | Tmem = T1 + T2                                                   |               |     |     | 2     |    |
|          | T1 = T2                                                          |               | 1   |     |      |    |
|          | T2 = Tmem                                                        |               |     | 2   |      |    |
|          |                                                                  |               |     |     |      |    |
| 6        | i = 3                                                            |               |     |     |      |    |
|          | Escreva: T1                                                      |               | 1   | 2   |      |    |
|          |                                                                  |               |     |     |      |    |
|          | Tmem = T1 + T2                                                   |               |     |     |  3    |    |
|          | T1 = T2                                                          |               | 2   |     |      |    |
|          | T2 = Tmem                                                        |               |     | 3   |      |    |
|          |                                                                  |               |     |     |      |    |
| 7        | i = 4                                                            |               |     |     |      |    |
|          | Escreva: T1                                                      |               | 2   | 3   |      |    |
|          |                                                                  |               |     |     |    |    |
|          | Tmem = T1 + T2                                                   |               |     |     | 5     |    |
|          | T1 = T2                                                          |               | 3   |     |      |    |
|          | T2 = Tmem                                                        |               |     | 5   |      |    |
|          |                                                                  |               |     |     |      |    |
| 8        | i = 5                                                            |               |     |     |      |    |
|          | Escreva: T1                                                      |               | 3   | 5   |      |    |
|          |                                                                  |               |     |     |      |    |
|          | Tmem = T1 + T2                                                   |               |     |     |   8   |    |
|          | T1 = T2                                                          |               | 5   |     |      |    |

| Iteração | Ação                                                             | Entrada/Saída | T1  | T2  | Tmem | TS |
|----------|------------------------------------------------------------------|---------------|-----|-----|------|----|
| -        | **Inicialização das Variáveis**                                  |               | 0   | 1   |      |    |
| -        | **Entrada do Termo de Fibonacci a ser calculado**               |               |     |     |      | 0  |
| 1        | Mensagem: "Digite qual termo de Fibonacci você quer calcular"   |               |     |     |      |    |
|          | Entrada: TS                                                      |               |     |     |      | 0  |
|          |                                                                  |               |     |     |      |    |
| 2        | **Verificação da Validade do Número**                            |               |     |     |      |    |
|          | Mensagem: "Digite um termo válido"                               |               |     |     |      |    |
|          | (Loop de entrada será repetido até que um número válido seja dado) |             |     |     |      |    |
|          |                                                                  |               |     |     |      |    |

| Iteração | Ação                                                             | Entrada/Saída | T1  | T2  | Tmem | TS |
|----------|------------------------------------------------------------------|---------------|-----|-----|------|----|
| -        | **Inicialização das Variáveis**                                  |               | 0   | 1   |      |    |
| -        | **Entrada do Termo de Fibonacci a ser calculado**               |               |     |     |      | -90|
| 1        | Mensagem: "Digite qual termo de Fibonacci você quer calcular"   |               |     |     |      |    |
|          | Entrada: TS                                                      |               |     |     |      | -90|
|          |                                                                  |               |     |     |      |    |
| 2        | **Verificação da Validade do Número**                            |               |     |     |      |    |
|          | Mensagem: "Digite um termo válido"                               |               |     |     |      |    |
|          | (Loop de entrada será repetido até que um número válido seja dado) |             |     |     |      |    |
|          |                                                                  |               |     |     |      |    |

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
Algoritmo Inver
DECLARE Num, Num_inv, mem, mem2: Int   // Declaração das variáveis
INICIO
ESCREVA "Digite o número que você quer inverter" 
LEIA Num                            // Lê o número digitado pelo usuário e o armazena em Num
mem2 = Num                         // Armazena o valor original de Num em mem2 para exibição posterior
ENQUANTO Num <= 9 FAÇA             // Enquanto o número for menor ou igual a 9
    ESCREVA "O número precisa ser positivo e ter mais de dois algarismos"   // Exibe uma mensagem de erro
    ESCREVA "Digite o número que você quer inverter"   
FIM_ENQUANTO             
ENQUANTO Num > 0 FAÇA              // Enquanto o número for maior que 0
    mem = Num % 10                 // Calcula o último dígito do número e o armazena em mem
    Num = Num // 10                 // Remove o último dígito do número
    Num_inv = Num_inv * 10         // Multiplica o número invertido por 10
    Num_inv = Num_inv + mem        // Adiciona o último dígito ao número invertido
FIM_ENQUANTO                       
ESCREVA "O número", mem2, "após inverter os algarismos é", Num_inv  
FIM_ALGORITMO                 

```

#### Teste de mesa
##### Chat GPT

| Iteração | Ação                                      | Entrada/Saída | Num    | Num_inv | mem  |
|----------|-------------------------------------------|----------------|--------|---------|------|
| -        | **Inicialização**                         |                | 12345  | 0       | -    |
| 1        | Leitura do número a ser invertido         |                | 12345  | 0       | -    |
| -        | Verificação da validade do número         |                | 12345  | 0       | -    |
| -        | (Número válido)                            |                | 12345  | 0       | -    |
| 2        | Início do loop de inversão                |                | 12345  | 0       | -    |
| 2.1      | Cálculo do resto da divisão por 10 (mem)  |                | 12345  | 0       | 5    |
| 2.2      | Atualização do número (Num //= 10)        |                | 1234   | 0       | 5    |
| 2.3      | Multiplicação e adição (Num_inv)          |                | 1234   | 5       | 5    |
| 3        | Próxima iteração                          |                | 1234   | 5       | -    |
| 3.1      | Cálculo do resto da divisão por 10 (mem)  |                | 1234   | 5       | 4    |
| 3.2      | Atualização do número (Num //= 10)        |                | 123    | 5       | 4    |
| 3.3      | Multiplicação e adição (Num_inv)          |                | 123    | 54      | 4    |
| 4        | Próxima iteração                          |                | 123    | 54      | -    |
| 4.1      | Cálculo do resto da divisão por 10 (mem)  |                | 123    | 54      | 3    |
| 4.2      | Atualização do número (Num //= 10)        |                | 12     | 54      | 3    |
| 4.3      | Multiplicação e adição (Num_inv)          |                | 12     | 543     | 3    |
| 5        | Próxima iteração                          |                | 12     | 543     | -    |
| 5.1      | Cálculo do resto da divisão por 10 (mem)  |                | 12     | 543     | 2    |
| 5.2      | Atualização do número (Num //= 10)        |                | 1      | 543     | 2    |
| 5.3      | Multiplicação e adição (Num_inv)          |                | 1      | 5432    | 2    |
| 6        | Próxima iteração                          |                | 1      | 5432    | -    |
| 6.1      | Cálculo do resto da divisão por 10 (mem)  |                | 1      | 5432    | 1    |
| 6.2      | Atualização do número (Num //= 10)        |                | 0      | 5432    | 1    |
| 6.3      | Multiplicação e adição (Num_inv)          |                | 0      | 54321   | 1    |
| 7        | Próxima iteração                          |                | 0      | 54321   | -    |
| 7.1      | (Condição de saída do loop)               |                | 0      | 54321   | -    |
| -        | **Saída do Resultado**                    | O número 12345 após inverter os algarismos é 54321| 0      | 54321   | -    |
