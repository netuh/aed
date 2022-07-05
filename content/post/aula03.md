+++
author = "Waldemar Ferreira"
title = "Análise assintótica"
date = "2022-07-05"
description = "Análise assintótica"
+++

## Análise Assintótica

A análise assintótica de um algoritmo refere-se à definição do **limite/enquadramento** matemático de seu desempenho em tempo de execução. Usando a análise assintótica, podemos definir o melhor caso, o caso médio e o pior cenário de um algoritmo.

Um exemplo que foi analisado é o seguinte:

```java
public class Main{
    public static double encontra(int[] var){
        for (int i = 0; i < 5; i++){
            if (var[i] == 5) {
                return 0;
            }
        }
        return -1;
    }
}
```

Lembrando que a linha primeira linha do método **encontra**:


| Id | Comandos                     | Primitivas |
|----|------------------------------|------------|
|    | for (int i = 0; i < 5; i++){ |            |
| c1 | int i = 0                    | 1          |
| c2 | i < 5                        | 1          |
| c3 | i++                          | 2          |
|    | if (var[i] == 5)             |            |
| c4 | var[i]                       | 1          |
| c5 | var[i] == 5                  | 1          |
| c6 | return 0                     | 1          |
| c7 | return -1                    | 1          |


Fazendo o somatório, seria:

$$ f(n) = c_1 + (c_2+ c_3 + c_4 + c_5) * 5 + c_6 $$

$$ f(n) = 1 + (4) * 5 + 1 $$

$$ f(n) = 22 $$