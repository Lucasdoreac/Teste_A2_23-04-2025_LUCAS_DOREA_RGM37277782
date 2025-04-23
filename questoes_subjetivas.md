# Parte 3: Questões Subjetivas

## Questão 1
**Explique como funcionam as estruturas de dados Pilha e Fila, suas principais diferenças e dê exemplos de onde cada uma pode ser aplicada.**

### Pilha (Stack)

Uma pilha é uma estrutura de dados linear que segue o princípio LIFO (Last In, First Out), ou seja, o último elemento a entrar é o primeiro a sair. Podemos compará-la com uma pilha de pratos, onde só podemos adicionar ou remover pratos do topo.

**Operações básicas:**
- **PUSH**: adiciona um elemento no topo da pilha
- **POP**: remove o elemento do topo da pilha
- **TOP/PEEK**: consulta o elemento do topo sem removê-lo
- **EMPTY**: verifica se a pilha está vazia
- **SIZE**: retorna o número de elementos na pilha

**Aplicações comuns de Pilha:**
1. Avaliação de expressões matemáticas e conversão de notações (infixa, pós-fixa)
2. Verificação de parênteses balanceados em expressões
3. Implementação da funcionalidade "Desfazer" (Undo) em editores de texto
4. Gerenciamento de chamadas de funções (stack trace) em linguagens de programação
5. Algoritmos de navegação em profundidade (DFS) em grafos

### Fila (Queue)

Uma fila é uma estrutura de dados linear que segue o princípio FIFO (First In, First Out), ou seja, o primeiro elemento a entrar é o primeiro a sair. É semelhante a uma fila de pessoas esperando em um guichê.

**Operações básicas:**
- **ENQUEUE**: adiciona um elemento no final da fila
- **DEQUEUE**: remove o elemento do início da fila
- **FRONT**: consulta o elemento do início sem removê-lo
- **EMPTY**: verifica se a fila está vazia
- **SIZE**: retorna o número de elementos na fila

**Aplicações comuns de Fila:**
1. Gerenciamento de processos em sistemas operacionais
2. Buffers para dados em operações de entrada/saída
3. Gerenciamento de requisições em servidores web
4. Controle de ordem de impressão em impressoras
5. Algoritmos de busca em largura (BFS) em grafos

### Principais Diferenças

| Característica | Pilha | Fila |
|----------------|-------|------|
| Princípio      | LIFO (Last In, First Out) | FIFO (First In, First Out) |
| Inserção       | Apenas em uma extremidade (topo) | Em uma extremidade (final) |
| Remoção        | Na mesma extremidade da inserção (topo) | Na extremidade oposta à inserção (início) |
| Aplicação      | Quando a ordem de processamento deve ser inversa à ordem de chegada | Quando o processamento deve seguir a ordem de chegada |

## Questão 2
**Descreva as vantagens e desvantagens de utilizar Listas encadeadas e Vetores, comparando as duas estruturas em termos de eficiência de acesso, inserção e remoção de elementos.**

### Vetores (Arrays)

Um vetor é uma estrutura de dados sequencial que armazena elementos em posições contíguas de memória, onde cada elemento pode ser acessado diretamente através de um índice.

**Vantagens:**
1. **Acesso direto**: O acesso a qualquer elemento é de tempo constante O(1), pois conhecendo o índice, podemos calcular diretamente o endereço de memória
2. **Eficiência espacial**: Requer menos espaço de memória por elemento, pois não precisa armazenar ponteiros adicionais
3. **Localidade de referência**: Melhor desempenho de cache devido à disposição contígua na memória
4. **Simplicidade**: Mais simples de implementar e usar

**Desvantagens:**
1. **Tamanho fixo**: Na maioria das implementações, o tamanho precisa ser definido na criação e não pode ser alterado facilmente
2. **Operações de inserção/remoção ineficientes**: Para inserir ou remover elementos no meio da estrutura, é necessário deslocar vários elementos, o que tem custo O(n)
3. **Desperdício de memória**: Quando alocamos mais espaço que o necessário ou quando há muitas remoções

### Listas Encadeadas

Uma lista encadeada é uma estrutura de dados linear em que cada elemento (nó) contém o dado e um ponteiro para o próximo elemento da lista.

**Vantagens:**
1. **Tamanho dinâmico**: Cresce ou diminui conforme necessário durante a execução do programa
2. **Inserção e remoção eficientes**: Quando já temos um ponteiro para o local de inserção/remoção, as operações são de tempo constante O(1)
3. **Melhor uso de memória em cenários de muitas inserções/remoções**: Não há necessidade de realocar a estrutura inteira

**Desvantagens:**
1. **Acesso sequencial**: Para acessar um elemento específico, é necessário percorrer a lista do início até encontrá-lo, resultando em tempo O(n)
2. **Maior consumo de memória por elemento**: Cada nó precisa armazenar o dado e pelo menos um ponteiro
3. **Menor eficiência de cache**: Os elementos não estão necessariamente em posições contíguas de memória
4. **Maior complexidade de implementação**: Requer gerenciamento manual de ponteiros e alocação de memória

### Comparação de Eficiência

| Operação | Vetor | Lista Encadeada |
|----------|-------|-----------------|
| Acesso a um elemento aleatório | O(1) - Constante | O(n) - Linear |
| Inserção/remoção no início | O(n) - Linear | O(1) - Constante |
| Inserção/remoção no meio | O(n) - Linear | O(n) para encontrar + O(1) para inserir |
| Inserção/remoção no final | O(1) - Amortizado* | O(n) para lista simples, O(1) para lista duplamente encadeada com ponteiro para o final |
| Uso de memória | Menor por elemento | Maior por elemento devido aos ponteiros |

*Amortizado para vetores dinâmicos que dobram de tamanho quando necessário

### Escolha da Estrutura Adequada

A escolha entre vetores e listas encadeadas depende das operações predominantes na aplicação:

- **Use vetores quando:**
  - O acesso aleatório por índice é frequente
  - O tamanho da coleção é conhecido antecipadamente
  - As operações de inserção/remoção são predominantemente no final
  - A eficiência de memória é crucial

- **Use listas encadeadas quando:**
  - Inserções e remoções frequentes em posições arbitrárias
  - O tamanho da coleção é desconhecido ou varia significativamente
  - O acesso sequencial é predominante
  - A realocação de memória precisa ser evitada