+++
author = "Waldemar Ferreira"
title = "Estrutura de Dados"
date = "2022-07-21"
description = "Pilha e Fila"
+++

## Pilha e Fila

Filas e pilhas são estruturas usualmente implementadas através de listas (que podem ser tanto a implementação com **Listas de Array** ou com **Listas Ligadas**), retringindo a política de manipulação dos elementos da lista.

### Fila

Uma fila (queue) tipicamente estabelece uma política FIFO -- first in, first out -- de acesso aos dados. Em outras palavras, a ordem estabelecida na lista é a ordem de inserção. No momento de retirar um nó da lista, o nó mais antigo (o primeiro que entrou) é o primeiro a ser retirado.

Como as políticas de inserção e remoção são pré-definidas, para esse tipo de estrutura as operações são descritas de forma genérica, INSERT e REMOVE. Há duas possibilidades para implementar as operações de uma fila usando os procedimentos descritos para listas:
* Restringir a inserção ao procedimento INSERT e a remoção ao procedimento REMOVELAST
* Restringir a inserção ao procedimento APPEND (inclui no final) e a remoção ao procedimento REMOVEFIRST.

#### Fila Fnterface

### Pilha

Uma estrutura de pilha (stack), por outro lado, estabelece uma política LIFO -- last in, first out. Uma estrutura de pilha também oferece basicamente duas operações de manipulação, PUSH, para inserção no topo da pilha, e POP, para retirada do topo da pilha.

Embora também fosse possível implementar uma pilha através de lista usando os procedimentos que acrescentam e removem os nós no final da lista, por razões óbvias de desempenho uma pilha é usualmente implementada usando os procedimentos INSERT e REMOVEFIRST, que não requerem a varredura da lista para estabelecer essa política de manipulação de dados.

#### Pilha Interface

```Java
public interface Stack {
    public boolean isEmpty();
    public boolean seach(int value);
    public void push(int value);
    public int pop();
}
```

#### Pilha Com Lista Ligada

```Java
public class StackLinked implements Stack{

    private No head;

    @Override
    public boolean isEmpty() {
        return head == null;
    }

    @Override
    public boolean seach(int value) {
        // TODO Auto-generated method stub
        return false;
    }

    @Override
    public void push(int value) {
        No n = new No(value);
        n.setProximo(head);
        head = n;
    }

    @Override
    public int pop() {
        int valor = head.getValor();
        head = head.getProximo();
        return valor;
    }
    
}
```

#### Pilha Com Array

```Java
public class StackArray implements Stack {

    private Integer[] keys = new Integer [1000];
    private Integer indexEnd;

    public StackArray(){
        indexEnd = 0;
    }

    @Override
    public boolean isEmpty() {
        if (indexEnd == 0){
            return true;
        }
        return false;
    }

    @Override
    public boolean seach(int value) {
        for (int i = 0; i < indexEnd; i++) {
            if (keys[i] == value){
                return true;
            }
        }
        return false;
    }

    @Override
    public void push(int value) {
        keys[indexEnd] = value;
        indexEnd++;
    }

    @Override
    public int pop() {
        int retorno = keys[indexEnd-1];
        indexEnd--;
        return retorno;
    }   
}
```

## Material Extra

Material sobre lista, pilha e filas: [Lista, pilha e Fila](https://www.youtube.com/watch?v=OwiHoj-mAi8)