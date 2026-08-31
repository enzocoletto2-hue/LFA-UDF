## 📌 Checklist da Aula 1 

> Antes de avançar para a próxima aula, verifique se você consegue explicar:

- [ ] **O que é um alfabeto Σ?**  
  > **R: Um alfabeto é um conjunto finito de símbolos que podem ser utilizados para construir palavras.** 

- [ ] **O que é uma cadeia/palavra?**  
  > **R: Um alfabeto é um conjunto finito de símbolos que podem ser utilizados para construir palavras.** 

- [ ] **O que significa ε?**  
  > **R:> **Significa que a linguagem não possui nenhuma palavra.** 

- [ ] **Por que |ε| = 0?**  
  > **R: Porque essa palavra possui comprimento zero.** 

- [ ] **O que é um prefixo?**  
  > **R: Prefixo fica antes do radical.** 

- [ ] **O que é um sufixo?**  
  > **R:Sufixo fica depois do radical.** 

- [ ] **O que significa Σ*?**  
  > **R: É o conjunto de todas as palavras que podem ser formadas com os símbolos do alfabeto Σ.** 

- [ ] **Se Σ* possui limite de tamanho?**  
  > **R: Não.** 

- [ ] **O que é uma linguagem formal L?**  
  > **R:É um conjunto de palavras escolhidas dentre as palavras possíveis sobre um alfabeto.** 

- [ ] **O que significa L ⊆ Σ*?**  
  > **R: L está contido em Σ*. Significa que toda palavra de L é também uma palavra sobre Σ, ou seja, L só usa símbolos do alfabeto. Toda linguagem sobre Σ é, por definição, um subconjunto de Σ*.** 

- [ ] **O que é uma gramática formal?**  
  > **R:É um mecanismo que gera as palavras de uma linguagem, definido pela quádrupla G = (V, T, P, S) ** 

- [ ] **O que são terminais e não terminais?**  
  > **R: Terminais (T): símbolos do alfabeto que aparecem na palavra final. Ex.: a, b, 0, 1. Não podem ser substituídos.Não terminais (V): símbolos auxiliares (S, A, B) que servem para construir a derivação e devem ser substituídos. Enquanto houver um não terminal, a derivação ainda não terminou** 

- [ ] **O que é uma regra de produção?**  
  > **R: É uma regra do tipo lado esquerdo → lado direito que diz como substituir um não terminal. Em S → aS, o → lê-se "produz" ou "é substituído por". Já o ⇒ indica a aplicação da regra (derivação): S ⇒ aS.** 

- [ ] **Como ler `S → aS | ε`?**  
  > **R: A barra | significa "ou" e agrupa duas produções do mesmo não terminal. Lê-se: "S produz aS, ou S produz ε".

- [ ] **Como gerar palavras usando uma gramática?**  
  > **R: Comece pelo símbolo inicial S.
         Escolha uma produção cujo lado esquerdo seja um não terminal presente e substitua.
         Repita até que não sobre nenhum não terminal.
         O que restou (só terminais) é a palavra gerada; ela pertence a L(G).**
