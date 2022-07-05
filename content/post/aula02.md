+++
author = "Waldemar Ferreira"
title = "Orientação a Objetos"
date = "2022-06-30"
description = "Orientação a Objtos"
+++

## Orientação a Objetos

A programação orientada a objetos (POO) é um paradigma de programação baseado no conceito de **objetos**, onde os **objetos** são instâncias de **classes**. Classes contêm **dados** e **comportamentos**: **dados** na forma de campos (geralmente conhecidos como atributos ou propriedades) e **comportamento** na forma de **funções** (muitas vezes conhecido como **métodos**).

Exemplo, um código que calcula a distância entre dois pontos.

![formula](/aed/img/dist.png "Distância entre dois pontos").

Como sabemos, de acordo com fórmula:

$$y = \sqrt[2]{(x_1-x_2)^2+(y_1-y_2)^2}$$

## Orientação a Objetos

Inicialmente temos que implementar a classe que representa um ponto, com um arquivo chamado **Ponto.java**.

```java
public class Ponto{
    float x;
    float y;

    public Ponto (float x, float y){
        this.x = x;
        this.y = y;
    }

    public float getX(){
        return x;
    }

    public float getY(){
        return y;
    }

    public double distanciaCoord(float x2, float y2){
        float dist_x = (this.x - x2) * (this.x - x2);
        float dist_y = (this.y - y2) * (this.y - y2);
        double d = Math.sqrt(dist_x + dist_y);
        return d;
    }

    public double distanciaPonto(Ponto p2){
        float dist_x = (this.x - p2.getX()) * (this.x - p2.getX());
        float dist_y = (this.y - p2.getY()) * (this.y - p2.getY());
        double d = Math.sqrt(dist_x + dist_y);
        return d;
    }
}
``` 

E a classe principal que executa o código principal com arquivo **Main.java**.

```java
public class Main{

    public static void main(String[] args){
        Ponto p1 = new Ponto(1,2);
        Ponto p1 = new Ponto(4,5);

        double d = p.distancia(p2);
        System.out.println(d)
    }
}
```