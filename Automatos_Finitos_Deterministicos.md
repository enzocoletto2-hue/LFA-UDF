# Lista de Exercícios — Autômatos Finitos Determinísticos (AFD)

> **Disciplina:** Teoria das Linguagens e Autômatos  
> **Tema:** Autômatos Finitos Determinísticos  
> **Modalidade:** Atividade prática em grupo  
> **Objetivo:** identificar, interpretar, construir e testar AFDs.

---

## Identificação do grupo

| Campo | Preenchimento |
|---|---|
| Turma | |
| Data | |
| Integrante 1 |Enzo Coletto Costa |
| Integrante 2 |Bianca Cristina das Neves |
| Integrante 3 |Davi Mendes Borges |
| Integrante 4 |Riandro Deian |

# Lista de Exercícios — Autômatos Finitos Determinísticos (AFD)

## Identificação do grupo

- **Disciplina:** Linguagens Formais e Autômatos
- **Tema:** Autômatos Finitos Determinísticos (AFD)

---

## Exercício 1

Uma lâmpada pode estar em dois estados:

- **Desligado**
- **Ligado**

Ao apertar o botão, a lâmpada troca de estado.

### Respostas

1. **Quantos estados existem?**  
   2 estados: Desligado e Ligado.

2. **Qual é o estado inicial?**  
   Desligado.

3. **Qual é a entrada?**  
   O botão sendo pressionado.

4. **Depois de 1 aperto, qual é o estado?**  
   Ligado.

5. **Depois de 2 apertos, qual é o estado?**  
   Desligado.

6. **Raciocínio:**  
   Cada aperto faz a lâmpada trocar de estado. Por isso, ela fica alternando entre ligado e desligado.

---

## Exercício 2

A porta automática possui dois estados:

- **Fechada**
- **Aberta**

As entradas são:

- `pessoa_detectada`
- `nenhuma_pessoa`

### Tabela de transição

| Estado | pessoa_detectada | nenhuma_pessoa |
|---|---|---|
| Fechada | Aberta | Fechada |
| Aberta | Aberta | Fechada |

### Estado inicial

**Fechada**

### Diagrama

```text
Fechada --pessoa_detectada--> Aberta
Fechada --nenhuma_pessoa----> Fechada

Aberta --pessoa_detectada--> Aberta
Aberta --nenhuma_pessoa----> Fechada
```

### Raciocínio

Se uma pessoa for detectada, a porta abre. Se não houver pessoa, ela fica ou volta para fechada.

---

## Exercício 3

O AFD possui:

- Alfabeto: `Σ = {0,1}`
- Estados: `Q = {q0,q1}`
- Estado inicial: `q0`
- Estado final: `q1`

### Respostas

- **Alfabeto:** `{0,1}`, porque são os símbolos que podem aparecer nas entradas.
- **Estados:** `q0` e `q1`.
- **Estado inicial:** `q0`.
- **Conjunto de estados finais:** `{q1}`.
- **Símbolos das transições:** `0` e `1`.
- **Duplo círculo:** indica que o estado é final.
- **Seta sem origem:** indica o estado inicial.

### Raciocínio

Para saber se uma palavra é aceita, começamos em `q0`, lemos os símbolos e seguimos as transições. Se terminarmos em `q1`, a palavra é aceita.

---

## Exercício 4

Um AFD é representado pela quíntupla:

```text
M = (Σ, Q, δ, q0, F)
```

### Significado

- `Σ` = alfabeto de entrada.
- `Q` = conjunto de estados.
- `δ` = função de transição.
- `q0` = estado inicial.
- `F` = conjunto de estados finais.

### Raciocínio

Essas cinco partes definem o autômato: quais símbolos podem ser lidos, quais estados existem, para onde cada símbolo leva, onde começa e quais estados representam aceitação.

---

## Exercício 5

AFD:

```text
Σ = {0,1}
Q = {q0,q1,q2}
q0 = estado inicial
F = {q1}
```

### Tabela de transição

| Estado | 0 | 1 |
|---|---|---|
| q0 | q0 | q1 |
| q1 | q2 | q1 |
| q2 | q1 | q1 |

### Respostas

- `δ(q0,0) = q0`
- `δ(q0,1) = q1`
- `δ(q1,0) = q2`
- `δ(q2,1) = q1`
- Estado final: `q1`

### Transições

```text
q0 --0--> q0
q0 --1--> q1
q1 --0--> q2
q1 --1--> q1
q2 --0--> q1
q2 --1--> q1
```

### Por que é determinístico?

Porque para cada estado existe exatamente uma transição para cada símbolo do alfabeto.

---

## Exercício 6

Usando o AFD do Exercício 5:

### a) `1`

```text
q0 --1--> q1
```

Terminou em `q1`, que é final.

**Resultado: ACEITA**

### b) `0011001`

```text
q0 --0--> q0
   --0--> q0
   --1--> q1
   --1--> q1
   --0--> q2
   --0--> q1
   --1--> q1
```

Terminou em `q1`.

**Resultado: ACEITA**

### c) `010010`

```text
q0 --0--> q0
   --1--> q1
   --0--> q2
   --0--> q1
   --1--> q1
   --0--> q2
```

Terminou em `q2`, que não é final.

**Resultado: REJEITA**

### d) `1101`

```text
q0 --1--> q1
   --1--> q1
   --0--> q2
   --1--> q1
```

Terminou em `q1`.

**Resultado: ACEITA**

### e) `000011010`

```text
q0 --0--> q0
   --0--> q0
   --0--> q0
   --0--> q0
   --1--> q1
   --1--> q1
   --0--> q2
   --1--> q1
   --0--> q2
```

Terminou em `q2`.

**Resultado: REJEITA**

---

## Exercício 7

Construir um AFD que aceite palavras que **terminam em `1`**.

### Ideia

- `q0` = a palavra terminou em `0` ou ainda está vazia.
- `q1` = a palavra terminou em `1`.

### Quíntupla

```text
M = ({0,1}, {q0,q1}, δ, q0, {q1})
```

### Tabela de transição

| Estado | 0 | 1 |
|---|---|---|
| q0 | q0 | q1 |
| q1 | q0 | q1 |

### Transições

```text
q0 --0--> q0
q0 --1--> q1
q1 --0--> q0
q1 --1--> q1
```

`q1` é o estado final.

### Testes

**Aceitas:**

- `1`
- `01`
- `101`
- `0001`
- `1101`

**Rejeitadas:**

- `ε`
- `0`
- `10`
- `100`
- `1110`

### Raciocínio

Se o último símbolo for `1`, terminamos em `q1` e aceitamos. Se o último símbolo for `0`, terminamos em `q0` e rejeitamos.

---

## Exercício 8

Construir um AFD que aceite palavras com **quantidade par de `1`s**.

### Estados

- `q0` = quantidade par de `1`s.
- `q1` = quantidade ímpar de `1`s.

### Quíntupla

```text
M = ({0,1}, {q0,q1}, δ, q0, {q0})
```

### Tabela de transição

| Estado | 0 | 1 |
|---|---|---|
| q0 | q0 | q1 |
| q1 | q1 | q0 |

### Raciocínio

Cada `1` troca o estado. Assim, `q0` representa quantidade par e `q1` quantidade ímpar. O símbolo `0` não muda a quantidade de `1`s.

### Testes

| Palavra | Resultado |
|---|---|
| `ε` | Aceita |
| `0` | Aceita |
| `1` | Rejeita |
| `11` | Aceita |
| `101` | Aceita |
| `1100` | Aceita |
| `10101` | Rejeita |

---

## Exercício 9

Construir um AFD que aceite palavras que possuem **pelo menos dois `0`s consecutivos**.

### Estados

- `q0` = ainda não encontramos dois `0`s juntos.
- `q1` = encontramos um `0`.
- `q2` = encontramos `00`. É o estado final.

### Quíntupla

```text
M = ({0,1}, {q0,q1,q2}, δ, q0, {q2})
```

### Tabela de transição

| Estado | 0 | 1 |
|---|---|---|
| q0 | q1 | q0 |
| q1 | q2 | q0 |
| q2 | q2 | q2 |

### Transições

```text
q0 --0--> q1
q0 --1--> q0

q1 --0--> q2
q1 --1--> q0

q2 --0--> q2
q2 --1--> q2
```

### Testes aceitos

- `00`
- `001`
- `100`
- `1001`
- `110011`
- `0000`

### Testes rejeitados

- `ε`
- `0`
- `1`
- `01`
- `10`
- `10101`

### Raciocínio

Quando aparece o primeiro `0`, vamos para `q1`. Se aparecer outro `0` logo depois, vamos para `q2`, que é final. Depois que encontramos `00`, continuamos em `q2`.

---

## Exercício 10

Modelar um semáforo com os estados:

- Verde
- Amarelo
- Vermelho

A entrada é `tempo`.

### Quíntupla

```text
M = ({tempo}, {Verde,Amarelo,Vermelho}, δ, Verde, ∅)
```

### Tabela de transição

| Estado | tempo |
|---|---|
| Verde | Amarelo |
| Amarelo | Vermelho |
| Vermelho | Verde |

### Transições

```text
Verde --tempo--> Amarelo
Amarelo --tempo--> Vermelho
Vermelho --tempo--> Verde
```

### Raciocínio

O semáforo fica mudando de estado em um ciclo:

```text
Verde → Amarelo → Vermelho → Verde
```

Nesse caso, não existe um estado final específico, porque o semáforo continua funcionando em ciclo.

---

## Exercício 11

Criar um AFD para um sistema de login que bloqueia depois de **3 senhas incorretas**.

### Estados

- `q0` = nenhuma tentativa errada.
- `q1` = 1 tentativa errada.
- `q2` = 2 tentativas erradas.
- `q3` = conta bloqueada.
- `q4` = usuário autenticado.

### Alfabeto

```text
Σ = {senha_correta, senha_incorreta}
```

### Estado inicial

```text
q0
```

### Estado final

```text
F = {q4}
```

### Tabela de transição

| Estado | senha_correta | senha_incorreta |
|---|---|---|
| q0 | q4 | q1 |
| q1 | q4 | q2 |
| q2 | q4 | q3 |
| q3 | q3 | q3 |
| q4 | q4 | q4 |

### Raciocínio

O autômato precisa saber quantas vezes a senha foi digitada errada. Por isso existem estados diferentes para 0, 1 e 2 erros. No terceiro erro, vai para `q3`, que representa a conta bloqueada.

---

## Exercício 12 — Implementação no JFLAP

Foi escolhido o **Exercício 7** para implementar no JFLAP.

O objetivo é aceitar palavras que terminam em `1`.

### Autômato usado

```text
M = ({0,1}, {q0,q1}, δ, q0, {q1})
```

### Testes realizados no JFLAP

| Entrada | Resultado esperado | Resultado no JFLAP |
|---|---|---|
| `1` | Aceita | Accept |
| `01` | Aceita | Accept |
| `101` | Aceita | Accept |
| `0` | Rejeita | Reject |
| `10` | Rejeita | Reject |
| `100` | Rejeita | Reject |

### Caminhos dos testes

**`1`:**

```text
q0 --1--> q1
```

Aceita.

**`01`:**

```text
q0 --0--> q0 --1--> q1
```

Aceita.

**`101`:**

```text
q0 --1--> q1 --0--> q0 --1--> q1
```

Aceita.

**`0`:**

```text
q0 --0--> q0
```

Rejeita.

**`10`:**

```text
q0 --1--> q1 --0--> q0
```

Rejeita.

**`100`:**

```text
q0 --1--> q1 --0--> q0 --0--> q0
```

Rejeita.

### Evidência do JFLAP

![Testes do Exercício 12 no JFLAP](<img width="873" height="703" alt="jflap-exercicio12" src="https://github.com/user-attachments/assets/e8278605-743e-4c89-9234-d40f1553c86f" />


### Raciocínio

Os resultados do JFLAP ficaram iguais aos resultados esperados. As palavras que terminam em `1` foram aceitas e as que terminam em `0` foram rejeitadas.

---

## Exercício 13

### Problema escolhido: acompanhamento de um pedido de entrega

Foi criado um AFD para representar o caminho de um pedido desde a realização até a entrega ou cancelamento.

### Estados

- `q0` = pedido feito.
- `q1` = pedido sendo preparado.
- `q2` = saiu para entrega.
- `q3` = pedido entregue.
- `q4` = pedido cancelado.

### Entradas

```text
Σ = {aceitar, preparar_pronto, entregar, cancelar}
```

### Estado inicial

```text
q0
```

### Estado final

```text
F = {q3}
```

### Quíntupla

```text
M = ({aceitar, preparar_pronto, entregar, cancelar},
     {q0,q1,q2,q3,q4},
     δ,
     q0,
     {q3})
```

### Tabela de transição

| Estado | aceitar | preparar_pronto | entregar | cancelar |
|---|---|---|---|---|
| q0 | q1 | q0 | q0 | q4 |
| q1 | q1 | q2 | q1 | q4 |
| q2 | q2 | q2 | q3 | q2 |
| q3 | q3 | q3 | q3 | q3 |
| q4 | q4 | q4 | q4 | q4 |

### Transições principais

```text
q0 --aceitar--> q1
q1 --preparar_pronto--> q2
q2 --entregar--> q3
q0 --cancelar--> q4
```

### Testes

| Sequência | Resultado |
|---|---|
| `aceitar → preparar_pronto → entregar` | Aceita |
| `cancelar` | Rejeita |
| `aceitar` | Rejeita |
| `aceitar → preparar_pronto` | Rejeita |
| `aceitar → preparar_pronto → entregar → entregar` | Aceita |

### Raciocínio

O pedido começa em `q0`. Depois de aceitar, vai para preparação. Quando fica pronto, sai para entrega. Quando é entregue, chega ao estado final `q3`.

O autômato é determinístico porque, para cada estado e entrada, existe apenas um próximo estado.

---

## Conclusão

Com os exercícios foi possível entender melhor como funcionam os Autômatos Finitos Determinísticos. A ideia principal é começar em um estado inicial, ler cada símbolo da entrada e seguir as transições. No final, se o autômato estiver em um estado final, a palavra é aceita; caso contrário, é rejeitada.

No Exercício 12, o autômato também foi implementado e testado no JFLAP, confirmando que as palavras que terminam em `1` são aceitas e as demais testadas são rejeitadas.
