---
layout: post
title: Como escrever um pseudocódigo?
---
Vamos a algumas definições antes de realmente responder.

Segundo [Wikipedia][1]:

> **Pseudocódigo** é uma forma genérica de escrever um algoritmo, utilizando uma linguagem simples (nativa a quem o escreve, de forma a
> ser entendida por qualquer pessoa) sem necessidade de conhecer a
> sintaxe de nenhuma linguagem de programação.

Um exemplo utilizado em instituições de ensino, é o compilador [Visualg][2], do qual facilita a ilustração de um algoritmo, de forma que todos os programadores possam entendê-los (independentemente da linguagem que utilizem).

Na minha época aprendi em Pascal, que no caso é, como se fosse o portugol da língua inglesa que se assemelham bastante a um pseudocódigo.

**Pascal:**

    program OlaMundo;
    begin
     WriteLn('Olá, Mundo!');
    end.

**Visualg:**

    Algoritmo "OlaMundo"
    inicio
    Escreval("Olá, Mundo!")
    Fimalgoritmo

O exemplo que postou acredito que seja em visualg, e adota o `var`, para declaração de variáveis, pois o visualg precisa de alguma forma interpretar para conseguir compilar, mas se tratando de pseudocódigo, não compilável, o intuito é compreender o que esta tentando ser transmitido, outro exemplo:

    INÍCIO
    VARIÁVEIS
    S,C,I,A,MD:Real;
    S ← 0;
    C ← 0;
    PARA I de 1 ATÉ 10 FAÇA PASSO 1
        Escreva "Digite um número: ";
        LEIA A;
        SE A ≥ 0 ENTÃO
             S ← S + A;
             C ← C + 1;
        FIM SE;
    FIM PARA;
    MD ← S / C;
    ESCREVER ("A média é: ", MD);
    FIM

**Conclusão:**  
Assim, não importa a sintaxe que vai utilizar para escrever, com um minino de padrão, e desde seja possível o receptor entender o que esta querendo ser dito, é válido.


  [1]: https://pt.wikipedia.org/wiki/Pseudoc%C3%B3digo
  [2]: https://pt.wikipedia.org/wiki/Visualg


