# Atividade sobre agentes inteligentes

Aula 20/10/2026 | Professora Kadidja Valéria | Inteligência Artificial

**Disciplina:** Linguagens Formais e Autômatos | Ciência da Computação  
**Estudante:** [Enzo Coletto Costa] | **Turma:** [N1]

---

## Exercício 2.3

### a. Um agente que detecta apenas informações parciais sobre o estado não pode ser perfeitamente racional.
- **Julgamento:** Falso (F)
- **Justificativa:** A racionalidade depende do que o agente consegue perceber e das ações disponíveis, e não da observabilidade perfeita do mundo. Se ele maximiza seu sucesso com a informação limitada que tem, ele é racional.
- **Exemplo:** Um carro autônomo em uma estrada com neblina densa (ambiente parcialmente observável) ainda toma a decisão mais racional possível (reduzir a velocidade, ligar faróis) com base nos dados limitados dos seus sensores.

### b. Existem ambientes de tarefa nos quais nenhum agente reativo puro pode comportar-se racionalmente.
- **Julgamento:** Verdadeiro (V)
- **Justificativa:** Agentes reativos puros tomam decisões baseadas apenas na percepção atual, sem manter um estado interno do passado. Em ambientes onde a informação passada é crucial para decidir a ação correta, um agente reativo puro falhará.
- **Exemplo:** Um labirinto onde é preciso lembrar por onde já passou para não ficar em ciclos infinitos.

### c. Existe um ambiente de tarefa em que todo agente é racional.
- **Julgamento:** Verdadeiro (V)
- **Justificativa:** Em ambientes extremamente triviais, onde qualquer ação possível atinge o objetivo ou onde o critério de sucesso é nulo, qualquer comportamento (mesmo aleatório ou inativo) atende à medida de desempenho.
- **Exemplo:** Um ambiente onde o objetivo do agente é apenas "existir" em um estado estático e todas as ações mantêm esse estado.

### d. A entrada para o programa de agente é a mesma que a entrada para a função de agente.
- **Julgamento:** Falso (F)
- **Justificativa:** A função de agente é uma descrição matemática abstrata que mapeia o histórico completo de percepções para uma ação. O programa de agente roda dentro da arquitetura física e, a cada ciclo, recebe apenas a percepção atual.

### e. Toda função de agente é implementável por uma combinação de programa/máquina.
- **Julgamento:** Falso (F)
- **Justificativa:** Algumas funções de agente exigem um histórico infinito ou um poder de computação infinito que excede a capacidade física de qualquer computador real (máquina de Turing finita).

### f. Suponha que um agente selecione sua ação uniformemente ao acaso do conjunto de ações possíveis. Existe um ambiente de tarefa determinista em que esse agente é racional.
- **Julgamento:** Verdadeiro (V)
- **Justificativa:** Se o ambiente determinista for tão simples que qualquer ação escolhida resulte no sucesso ou cumpra a meta, o agente aleatório será racional.
- **Exemplo:** Um aspirador de pó em uma sala onde todas as posições já estão limpas e qualquer movimento não altera o sucesso.

### g. É possível para um dado agente ser perfeitamente racional em dois ambientes de tarefa distintos.
- **Julgamento:** Verdadeiro (V)
- **Justificativa:** Se os dois ambientes possuírem dinâmicas estruturalmente equivalentes que exijam exatamente a mesma estratégia de maximização de desempenho, o mesmo programa de agente pode ser racional em ambos.

### h. Todo agente é racional em um ambiente não observável.
- **Julgamento:** Falso (F)
- **Justificativa:** Em um ambiente não observável, o agente não tem informações diretas, mas ainda precisa fazer inferências e agir de forma inteligente. Se ele tomar ações autodestrutivas ou ignorar raciocínios probabilísticos básicos, ele será irracional.

### i. Um agente jogador de pôquer perfeitamente racional nunca perde.
- **Julgamento:** Falso (F)
- **Justificativa:** O pôquer é um jogo estocástico com informação incompleta (envolve cartas aleatórias e blefes). Um agente racional maximiza sua expectativa matemática de ganho a longo prazo, mas a sorte ainda pode fazê-lo perder uma partida isolada.

---

## Exercício 2.4

### Caso 1 — Jogar futebol
- **Agente analisado:** O jogador robô.
- **Objetivo e hipóteses:** Marcar mais gols que o adversário seguindo as regras.
- **P — Medida de desempenho:** Gols marcados, faltas evitadas, posse de bola, vitória.
- **E — Ambiente:** Campo de futebol, bola, companheiros, adversários, juiz.
- **A — Atuadores:** Pernas/pés robóticos (chutar, correr), tronco.
- **S — Sensores:** Câmeras (visão computacional), sensores de toque, giroscópio.

| Propriedade | Classificação | Justificativa |
|---|---|---|
| Observabilidade | Parcialmente observável | Há oclusão visual de jogadores e a bola pode estar fora do campo de visão imediata. |
| Número de agentes | Multiagente | Envolve múltiplos agentes em cooperação (time) e competição (adversários). |
| Previsibilidade | Estocástico | As ações dos rivais e os ressaltos da bola são imprevisíveis. |
| Dependência entre decisões | Sequencial | As jogadas atuais afetam diretamente todo o curso e o resultado da partida. |
| Mudança durante a decisão | Dinâmico | O jogo e o tempo continuam correndo enquanto o agente calcula suas ações. |
| Natureza dos elementos | Contínuo | O espaço físico, o tempo e as posições variam de forma contínua. |
| Conhecimento do funcionamento | Conhecido | As regras do jogo e a física básica do ambiente são conhecidas. |

---

### Caso 2 — Explorar os oceanos subterrâneos de Titã
- **Agente analisado:** Sonda submarina autônoma.
- **Objetivo e hipóteses:** Coletar dados científicos e amostras sem danificar o equipamento.
- **P — Medida de desempenho:** Quantidade de dados úteis coletados, integridade da sonda, eficiência energética.
- **E — Ambiente:** Oceano subterrâneo de metano/etano líquido em Titã, correntes, relevo submarino.
- **A — Atuadores:** Propulsores, braço mecânico coletor, instrumentos de medição.
- **S — Sensores:** Sonar, câmeras de alta pressão, sensores térmicos e químicos.

| Propriedade | Classificação | Justificativa |
|---|---|---|
| Observabilidade | Parcialmente observável | A visibilidade sob o líquido extraterrestre é limitada por partículas e distância. |
| Número de agentes | Agente único | Apenas a sonda atua no ambiente (ignorando variações naturais passivas). |
| Previsibilidade | Estocástico | Correntes e fenômenos geológicos subterrâneos são incertos. |
| Dependência entre decisões | Sequencial | Decisões de navegação afetam a sobrevivência e o sucesso futuro da missão. |
| Mudança durante a decisão | Dinâmico | O ambiente muda enquanto a sonda processa as informações. |
| Natureza dos elementos | Contínuo | Variáveis físicas como pressão, temperatura e coordenadas espaciais são contínuas. |
| Conhecimento do funcionamento | Desconhecido | O ambiente real de Titã possui leis e características exatas ainda não totalmente mapeadas. |

---

### Caso 3 — Comprar livros usados de IA na Internet
- **Agente analisado:** Bot de e-commerce / comprador automatizado.
- **Objetivo e hipóteses:** Adquirir o livro desejado pelo menor preço e melhor estado de conservação.
- **P — Medida de desempenho:** Economia financeira obtida, tempo de busca, estado real do livro adquirido.
- **E — Ambiente:** Sites de e-commerce, sebos online, catálogos de livros.
- **A — Atuadores:** Requisições HTTP, cliques de compra, envio de pagamento digital.
- **S — Sensores:** Web scraping de páginas web, APIs de busca de preços.

| Propriedade | Classificação | Justificativa |
|---|---|---|
| Observabilidade | Parcialmente observável | Nem todas as ofertas ocultas, fretes reais ou condições reais dos sebos são visíveis instantaneamente. |
| Número de agentes | Multiagente | Competição com outros compradores e vendedores no marketplace. |
| Previsibilidade | Estocástico | Os preços mudam dinamicamente e livros esgotam sem aviso prévio. |
| Dependência entre decisões | Sequencial | Comprar agora ou esperar uma oferta melhor afeta o resultado final. |
| Mudança durante a decisão | Semicontínuo / Dinâmico | O mercado muda conforme outros usuários compram os itens. |
| Natureza dos elementos | Discreto | Preços, estoque e identificadores de livros são discretos. |
| Conhecimento do funcionamento | Conhecido | As regras das plataformas de internet e APIs são conhecidas. |

---

### Caso 4 — Jogar uma partida de tênis
- **Agente analisado:** Jogador robô de tênis.
- **Objetivo e hipóteses:** Vencer o set/partida marcando pontos dentro das regras.
- **P — Medida de desempenho:** Número de pontos/games/sets vencidos, erros não forçados.
- **E — Ambiente:** Quadra de tênis, rede, raquete, bola, oponente humano ou robô.
- **A — Atuadores:** Braços mecânicos, sistema de locomoção em quadra.
- **S — Sensores:** Câmeras de rastreamento de trajetória da bola, sensores espaciais.

| Propriedade | Classificação | Justificativa |
|---|---|---|
| Observabilidade | Parcialmente observável | O oponente pode ocultar a intenção do golpe até o último instante. |
| Número de agentes | Multiagente | Competitivo direto contra o oponente. |
| Previsibilidade | Estocástico | As reações e estratégias do adversário introduzem imprevisibilidade. |
| Dependência entre decisões | Sequencial | Cada rebatida molda a posição e as opções do ponto seguinte. |
| Mudança durante a decisão | Dinâmico | O jogo flui continuamente sem pausas para reflexão. |
| Natureza dos elementos | Contínuo | Movimento, tempo, velocidade e trajetória da bola são contínuos. |
| Conhecimento do funcionamento | Conhecido | As regras da física e do tênis são plenamente conhecidas. |

---

### Caso 5 — Praticar tênis contra uma parede
- **Agente analisado:** Jogador robô de tênis.
- **Objetivo e hipóteses:** Rebater a bola consecutivamente mantendo o rali ativo.
- **P — Medida de desempenho:** Número de rebatidas consecutivas sem falha.
- **E — Ambiente:** Parede de treino, piso da quadra, bola, raquete.
- **A — Atuadores:** Braços mecânicos, pernas para deslocamento.
- **S — Sensores:** Câmeras e sensores visuais para rastreamento da bola.

| Propriedade | Classificação | Justificativa |
|---|---|---|
| Observabilidade | Completamente observável | A trajetória da bola e a parede são totalmente visíveis ao agente. |
| Número de agentes | Agente único | Não há outro agente ativo influenciando inteligentemente o ambiente. |
| Previsibilidade | Determinístico | A parede reflete a bola de acordo com leis físicas determinísticas. |
| Dependência entre decisões | Sequencial | O acerto atual depende e afeta a recepção da próxima batida. |
| Mudança durante a decisão | Dinâmico | A bola se move continuamente no tempo. |
| Natureza dos elementos | Contínuo | Espaço, tempo e física do impacto são contínuos. |
| Conhecimento do funcionamento | Conhecido | As leis de reflexão e funcionamento do ambiente são conhecidas. |

---

### Caso 6 — Realizar um salto de altura
- **Agente analisado:** Robô atleta de salto.
- **Objetivo e hipóteses:** Saltar o mais alto possível superando o sarilho sem derrubá-lo.
- **P — Medida de desempenho:** Altura máxima alcançada sem derrubar a barra.
- **E — Ambiente:** Estádio, pista de corrida, sarilho, colchão de queda.
- **A — Atuadores:** Pernas mecânicas de propulsão, ajuste de postura no ar.
- **S — Sensores:** Sensores inerciais, câmeras de distância, giroscópio.

| Propriedade | Classificação | Justificativa |
|---|---|---|
| Observabilidade | Completamente observável | Todos os elementos relevantes (barra, pista, corpo) são visíveis. |
| Número de agentes | Agente único | O atleta atua sozinho na realização da tarefa mecânica. |
| Previsibilidade | Determinístico | A biomecânica e a física do salto seguem leis determinísticas. |
| Dependência entre decisões | Sequencial | A corrida de aproximação afeta o impulso, que afeta a fase aérea. |
| Mudança durante a decisão | Dinâmico | O salto ocorre em tempo real de forma contínua. |
| Natureza dos elementos | Contínuo | Altura, tempo e biomecânica são contínuos. |
| Conhecimento do funcionamento | Conhecido | As leis da gravidade e da biomecânica são conhecidas. |

---

### Caso 7 — Participar de um leilão de um item, realizando lances
- **Agente analisado:** Agente de software de leilão.
- **Objetivo arrematar o item desejado pelo menor preço possível dentro do teto de orçamento.
- **P — Medida de desempenho:** Sucesso na aquisição do item, economia em relação ao valor máximo estipulado.
- **E — Ambiente:** Plataforma de leilão online, outros lances concorrentes.
- **A — Atuadores:** Envio de valor de lance via API/sistema.
- **S — Sensores:** Leitura do histórico de lances da página, tempo restante.

| Propriedade | Classificação | Justificativa |
|---|---|---|
| Observabilidade | Parcialmente observável | Estratégias e lances máximos dos concorrentes são ocultos até serem revelados. |
| Número de agentes | Multiagente | Ambiente altamente competitivo com múltiplos ofertantes. |
| Previsibilidade | Estocástico | Os lances dos outros participantes introduzem incerteza no resultado. |
| Dependência entre decisões | Sequencial | Dar um lance agora afeta a resposta dos concorrentes e o preço final. |
| Mudança durante a decisão | Semidinâmico | O tempo do leilão passa, mas as decisões ocorrem em momentos específicos de lance. |
| Natureza dos elementos | Discreto | Os valores monetários e o tempo em segundos são discretos. |
| Conhecimento do funcionamento | Conhecido | As regras do leilão são conhecidas pelo agente. |

---

### Comparação Final
1. **Tênis contra pessoa vs. parede:** Contra a pessoa, o ambiente é multiagente, competitivo e estocástico (o adversário reage estrategicamente). Contra a parede, é um agente único, determinista e estático em termos de inteligência opositora (a parede apenas reflete a bola passivamente).
2. **Informações incompletas na compra de livros:** O comprador não conhece o estado real de conservação do livro, a honestidade do vendedor ou se há ofertas melhores ocultas na internet.
3. **Influência de outros agentes:** No futebol e em leilões, as ações de um agente alteram diretamente o estado do mundo e a utilidade dos demais, exigindo raciocínio estratégico e antecipação de movimentos alheios.

---

## Exercício 2.5

### Agente
- **Definição:** Entidade autônoma capaz de perceber seu ambiente por meio de sensores e agir sobre ele utilizando atuadores para atingir determinados objetivos.
- **Exemplo:** Um robô aspirador autônomo limpando uma residência.

### Função de agente
- **Definição:** Descrição matemática abstrata que mapeia qualquer histórico de percepções possíveis para uma ação específica a ser executada pelo agente.
- **Exemplo:** A tabela teórica que associa cada histórico de sujeira detectada à respectiva manobra de limpeza.

### Programa de agente
- **Definição:** Implementação concreta do agente executada em sua arquitetura física, responsável por calcular a ação com base na percepção atual.
- **Exemplo:** O código fonte em C++ rodando no processador embutido do robô aspirador.

### Racionalidade
- **Definição:** Propriedade de um agente agir sempre de modo a maximizar o seu desempenho esperado, com base nas percepções recebidas e no conhecimento prévio.
- **Exemplo:** Um termostato que aciona o ar-condicionado assim que a temperatura ambiente ultrapassa o limite configurado.

### Autonomia
- **Definição:** Grau em que o comportamento do agente depende de sua própria experiência de aprendizagem e percepção, e não apenas de instruções fixas do programador.
- **Exemplo:** Um carro autônomo que aprende a navegar por novas rotas urbanas sem intervenção humana prévia.

### Agente reativo
- **Definição:** Agente que toma decisões baseando-se unicamente na percepção atual do ambiente, sem manter registros ou estados internos do passado.
- **Exemplo:** Uma torneira automática com sensor infravermelho que abre a água ao detectar movimento imediato.

### Agente baseado em modelo
- **Definição:** Agente que mantém um estado interno para rastrear aspectos do mundo que não são visíveis no momento, compreendendo como o ambiente evolui.
- **Exemplo:** Um robô aspirador que mapeia mentalmente os cômodos da casa por onde já passou.

### Agente baseado em objetivos
- **Definição:** Agente que utiliza informações sobre metas desejadas para avaliar e selecionar quais ações o aproximam do objetivo final estabelecido.
- **Exemplo:** Um aplicativo de GPS calculando a rota mais rápida para um destino específico.

### Agente baseado em utilidade
- **Definição:** Agente que mede o sucesso usando uma função de utilidade, escolhendo ações que maximizam a sua "felicidade" ou grau de preferência entre várias opções.
- **Exemplo:** Um GPS que, além de buscar o menor tempo, calcula qual caminho possui menos pedágios e trânsito.

### Agente com aprendizagem
- **Definição:** Agente cujo programa pode se modificar e melhorar seu comportamento e desempenho ao longo do tempo com base na experiência acumulada.
- **Exemplo:** Um sistema de recomendação de streaming que aprende os gostos do usuário conforme ele assiste a mais filmes.

---

## Síntese com autômatos

- **Cenário escolhido:** Robô aspirador em um ambiente de duas salas (A e B).
- **Três Estados Internos:** 
  1. $S_1$: Localizado na Sala A (limpa).
  2. $S_2$: Localizado na Sala B (suja).
  3. $S_3$: Bateria baixa.
- **Três Percepções:** 
  1. $P_1$: [Limpo, Direita]
  2. $P_2$: [Sujo, Esquerda]
  3. $P_3$: [BateriaFraca]
- **Três Ações:** 
  1. $A_1$: Aspirar
  2. $A_2$: Mover para Direita
  3. $A_3$: Ir para base de carga
- **Regras de Transição:**
  - **Regra 1:** $S_1 + P_2 \rightarrow (S_2, A_1)$ *(Se está na Sala A e percebe que B está suja/está na esquerda, move-se e aspira).*
  - **Regra 2:** $S_2 + P_3 \rightarrow (S_3, A_3)$ *(Se está na Sala B e a bateria fica fraca, vai para a base de carga).*

- **Explicação do Estado Interno:** O estado interno guarda informações do passado que não estão visíveis no sensor imediato, permitindo ao agente lembrar contextos anteriores essenciais para a tomada de decisão.
- **Limitação da Modelagem:** O uso de autômatos finitos simples sofre com a "explosão de estados" em ambientes complexos do mundo real, tornando impossível mapear todas as combinações possíveis de variáveis contínuas.

---

## Referências

- RUSSELL, Stuart; NORVIG, Peter. Agentes inteligentes. In: RUSSELL, Stuart; NORVIG, Peter. *Inteligência artificial*. 3. ed. Rio de Janeiro: Elsevier, 2013. cap. 2.