+++
author = "Waldemar Ferreira"
title = "Estrutura de Dados"
date = "2022-07-21"
description = "Estrutura de Dados"
+++

## Estrutura de Dados

Na ciência da computação, uma estrutura de dados é uma forma de organização, gerenciamento e armazenamento de dados de forma a dar um acesso eficiente a dados Mais precisamente, uma estrutura de dados é uma coleção de valores de dados, os relacionamentos entre eles e as funções (ou operações) que podem ser aplicadas esses dados.

As Estruturas de dados mais elementares possuem dois tipos de operações: Consultivas e Modificadoras. As operações mais importantes estão em negrito.

As Operações Consultivas são:
* **Search** (ou procurar)
* Minimum (ou valor mínimo)
* Maximum (ou valor máximo)
* Sucessor (ou valor sucessor)
* Predessor (ou valor antecessor)

Operações Modificadoras:
* **Insert** (ou inserir)
* **Delete** (ou excluir)

Interface em Java comum a todos

```java
public interface EstruturaDeDados {
    public void insert(int chave);
    public void delete(int chave);
    public boolean search(int chave);
    public int minimum();
    public int maximum();
    public int sucessor(int chave);
    public int prodessor(int chave);
}
```

### Implementação com Array

```Java
public class EstruturaBasicaArray implements EstruturaDeDados {

    //Este limite pode ser alterado
    private int[] valores = new int[1000];
    private int index;

    public NetoEstrutura(){
        index = 0;
    }

    @Override
    public void insert(int chave) {
        valores[index] = chave;
        index++;
    }

    @Override
    public void delete(int chave) {
        int indexDelete = searchIndex(chave);
        if (indexDelete != -1){
            for (int i = indexDelete; i < index; i++) {
                valores[i] = valores[i+1];
            }
            index--;
        }
    }

    @Override
    public boolean search(int chave) {
        int indexDelete = searchIndex(chave);
        if (indexDelete != -1) {
            return true;
        }
        return false;
    }

    public int searchIndex(int chave) {
        int indexDelete = -1;
        for (int j = 0; j < index; j++) {
            if (valores[j] == chave) {
                indexDelete = j;
            }
        }
        return indexDelete;
    }

    @Override
    public int minimum() {
        int minimo = valores[0];
        for (int j = 0; j < index; j++) {
            if (valores[j] < minimo){
                minimo = valores[j];
            }
        }
        return minimo;
    }

    @Override
    public int maximum() {
        int maximum = valores[0];
        for (int j = 0; j < index; j++) {
            if (maximum < valores[j]){
                maximum = valores[j];
            }
        }
        return maximum;
    }

    @Override
    public int sucessor(int chave) {
        int minimoLocal = Math.abs(valores[0] - chave);
        int indexMinimo = 0
        for (int j = 0; j < index; j++) {
            if (minimoLocal > Math.abs(valores[0] - chave)){
                minimoLocal = Math.abs(valores[0] - chave);
                indexMinimo = j;
            }
        }
        return valores[j];
    }

    @Override
    public int prodessor(int chave) {
        int minimoLocal = Math.abs(valores[0] - chave);
        int indexMinimo = 0
        for (int j = 0; j < index; j++) {
            if (minimoLocal > Math.abs(valores[0] - chave)){
                minimoLocal = Math.abs(valores[0] - chave);
                indexMinimo = j;
            }
        }
        return valores[j];
    } 
}
```

### Implementação com Lista Ligadas (ou Linked List)

Neste caso precisamos de pelo menos duas Classes:
* No (ou Node).
* A classe de referência.

```Java
public class No {
    private int valor;
    private No proximo;

    public No(int chave) {
        valor = chave;
    }

    public No getProximo(){
        return proximo;
    }

    public void setProximo(No novo) {
        proximo = novo;
    }

    public int getValor() {
        return valor;
    }
}
```


```Java
public class ListaLigada implements EstruturaDeDados{

    private No cabeca;

    @Override
    public void insert(int chave) {
        //inserir na cabeça
        if (cabeca == null){
            cabeca = new No(chave);
            return;
        }
        //inserir no corpo
        No n = cabeca;
        while(n.getProximo() != null){
            n = n.getProximo();
        }
        No novo = new No(chave);
        n.setProximo(novo);
    }

    @Override
    public void delete(int chave) {
        //remover a cabeca
        if (chave == cabeca.getValor()){
            cabeca = cabeca.getProximo();
            return;
        }
        //remover no corpo
        No n = cabeca;
        while(n.getProximo() != null){
            No proximo = n.getProximo();
            if (proximo.getValor() == chave){
                n.setProximo(proximo.getProximo());
                return;
            }
            n = n.getProximo();
        }
    }

    @Override
    public boolean search(int chave) {
        if (cabeca.getValor() == chave){
            return true;
        }
        No n = cabeca;
        while(n.getProximo() != null){
            n = n.getProximo();
            if (n.getValor() == chave){
                return true;
            }
        }
        return false;
    }

    @Override
    public int minimum() {
        int minimo = cabeca.getValor();
        No n = cabeca;
        while(n.getProximo() != null){
            n = n.getProximo();
            if (minimo > n.getValor()){
                minimo = n.getValor()
            }
        }
        return minimo;
    }

    @Override
    public int maximum() {
        int maximum = cabeca.getValor();
        No n = cabeca;
        while(n.getProximo() != null){
            n = n.getProximo();
            if (maximum < n.getValor()){
                maximum = n.getValor()
            }
        }
        return maximum;
    }

    @Override
    public int sucessor(int chave) {
        int minimoLocal = Math.abs(cabeca.getValor() - chave);
        No n = cabeca;
        int valorProximo = cabeca.getValor();
        while(n.getProximo() != null){
            n = n.getProximo();
            if (minimoLocal > Math.abs(n.getValor() - chave)){
                minimoLocal = Math.abs(n.getValor() - chave);
                valorProximo = cabeca.getValor();
            }
        }
        return valorProximo;
    }

    @Override
    public int prodessor(int chave) {
        int minimoLocal = Math.abs(cabeca.getValor() - chave);
        No n = cabeca;
        int valorProximo = cabeca.getValor();
        while(n.getProximo() != null){
            n = n.getProximo();
            if (minimoLocal > Math.abs(n.getValor() - chave)){
                minimoLocal = Math.abs(n.getValor() - chave);
                valorProximo = cabeca.getValor();
            }
        }
        return valorProximo;
    }
    
}
```

## Material Extra

Material sobre lista encadeada: [Lista encadeadas](https://www.youtube.com/watch?v=wRXdDK3zGZs)