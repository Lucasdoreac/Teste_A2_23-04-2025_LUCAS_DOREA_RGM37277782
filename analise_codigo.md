# Parte 2: Análise de Código

## 1. Análise de Código em C
```c
#include <stdio.h>
int main() {
    int vetor[5] = {10, 20, 30, 40, 50};
    int *ptr = vetor;
    printf("%d", *(ptr + 2));
    return 0;
}
```

**Código limpo e comentado:**
```c
#include <stdio.h>
int main() {
    /* Inicializa um vetor de 5 elementos inteiros */
    int vetor[5] = {10, 20, 30, 40, 50};
    
    /* Cria um ponteiro que aponta para o início do vetor */
    int *ptr = vetor;
    
    /* Acessa o elemento na posição 2 (terceiro elemento) 
       usando aritmética de ponteiros e imprime o valor */
    printf("%d", *(ptr + 2)); /* Equivalente a vetor[2] */
    
    return 0;
}
```

**Resposta: 30**

## 2. Análise de Código em Java
```java
public class Main {
    public static void main(String[] args) {
        Stack<String> stack = new Stack<>();
        stack.push("A");
        stack.push("B");
        stack.push("C");
        System.out.println(stack.pop());
        System.out.println(stack.peek());
    }
}
```

**Código limpo e comentado:**
```java
import java.util.Stack; // Import necessário

public class Main {
    public static void main(String[] args) {
        // Cria uma pilha de Strings
        Stack<String> stack = new Stack<>();
        
        // Adiciona elementos à pilha (do mais abaixo ao topo)
        stack.push("A"); // Primeiro elemento (fundo da pilha)
        stack.push("B"); // Segundo elemento
        stack.push("C"); // Terceiro elemento (topo da pilha)
        
        // Remove e imprime o elemento do topo (C)
        System.out.println(stack.pop());
        
        // Visualiza, sem remover, o novo elemento do topo (B)
        System.out.println(stack.peek());
    }
}
```

**Resposta:**
```
C
B
```

## 3. Análise de Código em Python
```python
fila = ["A", "B", "C"]
fila.append("D")
print(fila.pop(0))
print(fila[0])
```

**Código limpo e comentado:**
```python
# Inicializa uma lista para simular uma fila
fila = ["A", "B", "C"]

# Adiciona um elemento ao final da fila
fila.append("D")  # Fila agora é ["A", "B", "C", "D"]

# Remove e retorna o primeiro elemento da fila (simulando uma dequeue)
print(fila.pop(0))  # Remove "A", fila agora é ["B", "C", "D"]

# Imprime o novo primeiro elemento da fila, sem removê-lo
print(fila[0])  # Imprime "B"
```

**Resposta:**
```
A
B
```

## 4. Análise de Código em C#
```csharp
public class Program {
    public static void Main(string[] args) {
        LinkedList<int> lista = new LinkedList<int>();
        lista.AddLast(1);
        lista.AddLast(2);
        lista.AddFirst(0);
        Console.WriteLine(lista.First.Value);
        Console.WriteLine(lista.Last.Value);
    }
}
```

**Código limpo e comentado:**
```csharp
using System;
using System.Collections.Generic; // Necessário para LinkedList

public class Program {
    public static void Main(string[] args) {
        // Cria uma lista duplamente encadeada vazia
        LinkedList<int> lista = new LinkedList<int>();
        
        // Adiciona o valor 1 ao final da lista
        lista.AddLast(1);  // Lista: [1]
        
        // Adiciona o valor 2 ao final da lista
        lista.AddLast(2);  // Lista: [1, 2]
        
        // Adiciona o valor 0 ao início da lista
        lista.AddFirst(0); // Lista: [0, 1, 2]
        
        // Imprime o valor do primeiro nó da lista
        Console.WriteLine(lista.First.Value);
        
        // Imprime o valor do último nó da lista
        Console.WriteLine(lista.Last.Value);
    }
}
```

**Resposta:**
```
0
2
```

## 5. Análise de Código em JavaScript
```javascript
let vetor = [1, 2, 3, 4, 5];
vetor.splice(2, 1);
console.log(vetor.length);
console.log(vetor[2]);
```

**Código limpo e comentado:**
```javascript
// Inicializa um array com 5 elementos
let vetor = [1, 2, 3, 4, 5];

// Remove 1 elemento a partir do índice 2
// splice(índice_inicial, qtd_elementos_a_remover)
vetor.splice(2, 1);  // Remove o elemento 3, vetor agora é [1, 2, 4, 5]

// Imprime o tamanho do vetor após a remoção
console.log(vetor.length);  // 4

// Imprime o elemento no índice 2 (que agora é 4, não mais 3)
console.log(vetor[2]);  // 4
```

**Resposta:**
```
4
4
```

## 6. Análise de Código em Python (da primeira lista)
```python
def funcao_misteriosa(lista):
    resultado = []
    for elemento in lista:
        if elemento % 2 == 0:
            resultado.append(elemento * 2)
        else:
            resultado.append(elemento + 1)
    return resultado
lista_exemplo = [1, 2, 3, 4, 5]
print(funcao_misteriosa(lista_exemplo))
```

**Código limpo e comentado:**
```python
def funcao_misteriosa(lista):
    """
    Processa uma lista de números aplicando diferentes operações:
    - Para números pares: multiplica por 2
    - Para números ímpares: adiciona 1
    """
    resultado = []
    for elemento in lista:
        if elemento % 2 == 0:  # Verifica se o elemento é par
            resultado.append(elemento * 2)
        else:  # Caso seja ímpar
            resultado.append(elemento + 1)
    return resultado

lista_exemplo = [1, 2, 3, 4, 5]
print(funcao_misteriosa(lista_exemplo))
```

**Resposta:** [2, 4, 4, 8, 6]

## 7. Análise de Código em C
```c
#include <stdio.h>
#include <stdlib.h>
struct No {
    int valor;
    struct No *proximo;
};
int main() {
    struct No *inicio = malloc(sizeof(struct No));
    inicio->valor = 10;
    inicio->proximo = NULL;
    struct No *segundo = malloc(sizeof(struct No));
    segundo->valor = 20;
    segundo->proximo = inicio;
    printf("%d", segundo->proximo->valor);
    free(inicio);
    free(segundo);
    return 0;
}
```

**Código limpo e comentado:**
```c
#include <stdio.h>
#include <stdlib.h>

/* Define a estrutura de um nó para uma lista encadeada */
struct No {
    int valor;         /* Valor armazenado no nó */
    struct No *proximo; /* Ponteiro para o próximo nó */
};

int main() {
    /* Aloca memória para o primeiro nó */
    struct No *inicio = malloc(sizeof(struct No));
    inicio->valor = 10;       /* Define o valor do primeiro nó */
    inicio->proximo = NULL;   /* Ainda não há próximo nó */
    
    /* Aloca memória para o segundo nó */
    struct No *segundo = malloc(sizeof(struct No));
    segundo->valor = 20;        /* Define o valor do segundo nó */
    segundo->proximo = inicio;  /* Liga o segundo nó ao primeiro */
    
    /* Acessa e imprime o valor do nó apontado pelo campo proximo do segundo nó */
    printf("%d", segundo->proximo->valor); /* Imprime o valor do primeiro nó */
    
    /* Libera a memória alocada */
    free(inicio);
    free(segundo);
    
    return 0;
}
```

**Resposta:** 10

## 8. Análise de Código em Java
```java
import java.util.LinkedList;
public class Main {
    public static void main(String[] args) {
        LinkedList<Integer> fila = new LinkedList<>();
        fila.add(10);
        fila.add(20);
        fila.add(30);
        System.out.println(fila.poll());
        System.out.println(fila.peek());
    }
}
```

**Código limpo e comentado:**
```java
import java.util.LinkedList;

public class Main {
    public static void main(String[] args) {
        // Cria uma LinkedList para usar como fila
        LinkedList<Integer> fila = new LinkedList<>();
        
        // Adiciona elementos à fila
        fila.add(10);  // Primeiro elemento
        fila.add(20);  // Segundo elemento
        fila.add(30);  // Terceiro elemento
        
        // poll() remove e retorna o primeiro elemento da fila
        System.out.println(fila.poll());  // Remove e imprime 10
        
        // peek() retorna o primeiro elemento sem removê-lo
        System.out.println(fila.peek());  // Imprime 20, sem remover
    }
}
```

**Resposta:**
```
10
20
```

## 9. Análise de Código em Python
```python
def recursiva(n):
    if n == 0:
        return 0
    else:
        return n + recursiva(n-1)
print(recursiva(5))
```

**Código limpo e comentado:**
```python
def recursiva(n):
    """
    Função recursiva que calcula a soma de n + (n-1) + (n-2) + ... + 1 + 0
    Também conhecida como somatório de 0 até n
    
    Args:
        n: Número inteiro não negativo
        
    Returns:
        Soma dos números de 0 até n
    """
    # Caso base: quando n é 0, retorna 0
    if n == 0:
        return 0
    # Caso recursivo: n + soma de todos os números menores que n
    else:
        return n + recursiva(n-1)

# Chama a função com n=5 e imprime o resultado
print(recursiva(5))  # 5 + 4 + 3 + 2 + 1 + 0 = 15
```

**Resposta:** 15

## 10. Análise de Código em JavaScript
```javascript
function arvore(n) {
    if (n <= 1) {
        return 1;
    } else {
        return arvore(n - 1) + arvore(n - 2);
    }
}
console.log(arvore(4));
```

**Código limpo e comentado:**
```javascript
/**
 * Calcula o n-ésimo número da sequência de Fibonacci (começando em 1)
 * onde F(0) = 1, F(1) = 1, F(n) = F(n-1) + F(n-2) para n > 1
 * 
 * @param {number} n - Posição na sequência de Fibonacci
 * @return {number} O valor do n-ésimo número de Fibonacci
 */
function arvore(n) {
    // Casos base: F(0) = F(1) = 1
    if (n <= 1) {
        return 1;
    } 
    // Caso recursivo: F(n) = F(n-1) + F(n-2)
    else {
        return arvore(n - 1) + arvore(n - 2);
    }
}

// Calcula e imprime o 4º número de Fibonacci
console.log(arvore(4));  // 1, 1, 2, 3, 5 -> o 4º número é 5
```

**Resposta:** 5