# Exercício guiado
>**Expressões Regulares   
>Linguagens Formais e Autômatos**
---

## 1. Sobre {0,1}, descreva palavras que terminam em 00 
> **R:^[01]*00$, porque [01] permite os símbolos 0 e 1, enquanto * permite que eles apareçam zero ou mais vezes. O 00 determina que a palavra deve terminar obrigatoriamente com dois zeros. Os símbolos ^ e $ indicam, respectivamente, o início e o fim da entrada, garantindo que a palavra inteira siga a regra.**


## 2. Sobre {a,b}, descreva palavras com exatamente dois a
> **R:^b*ab*ab*$, porque O primeiro b* permite zero ou mais b antes do primeiro a. Depois temos o primeiro a, seguido de outro b*, que permite b entre os dois a. Em seguida aparece o segundo a e, por fim, outro b* permite b depois dele. Dessa forma, existem exatamente dois a na palavra. Os símbolos ^ e $ garantem que toda a entrada seja analisada.**

## 3. Crie um identificador com duas maiúsculas, três algarismos e uma minúscula opcional 
Registre a linguagem, exemplos aceitos, rejeitados e sua Regex
> **R:^[A-Z]{2}[0-9]{3}[a-z]?$, porque [A-Z]{2} representa exatamente duas letras maiúsculas. [0-9]{3} representa exatamente três algarismos. [a-z]? representa uma letra minúscula que pode aparecer zero ou uma vez, pois o ? indica que o elemento é opcional. Os símbolos ^ e $ garantem que o identificador inteiro siga esse formato.**
##
