---
layout: post
title: Tipos de testes de softwares
tags: teste 
---

Existem diversas maneiras de testar um programa de computador, manualmente, automaticamente, a literatura nos trás modos de fazer isso de maneira estruturada, e cada tipo responsável por um aspecto a ser considerado.

### **Teste de Validação**

 - O software está montado como um pacote e a validação do mesmo é realizada através de uma série de testes caixa preta 
 - finalidade:
  - demonstrar a conformidade aos requisitos funcionais e de desempenho
  - verificar se a documentação está correta
 - duas possibilidades:
  - aceito
  - não está totalmente de acordo com os requisitos: negociar com o usuário
 - engloba o Teste de Aceitação: realizado pelo próprio usuário
 - no caso de software desenvolvido para vários usuários:
  - teste alfa: realizado pelo usuário no ambiente do desenvolvedor
  - teste beta: realizado pelo usuário em seu próprio ambiente

### **Teste de Sistema**

 - considera o software dentro do seu ambiente mais amplo (todos os aspectos de interação com ele, como outro hardware, software, pessoas, etc.)
 - corresponde a uma série de testes que tem por objetivo verificar se todos os elementos do sistema foram integrados adequadamente e realizam corretamente suas funções
  - **teste de segurança:** tem por objetivo verificar se todos os mecanismos de proteção protegem realmente o software de acessos indevidos.
  - **teste de estresse:** tem por objetivo confrontar os programas com situações anormais de freqüência, volume ou recursos em quantidade.
  - **teste de desempenho:** tem por objetivo testar o tempo de resposta do sistema e é aplicado, geralmente, para sistemas de tempo real

### **Teste Unitário**

 - concentra-se no módulo
 - utiliza a técnica de teste estrutural
 - pode ser realizado em paralelo para vários módulos
 - aspectos considerados: geralmente, um programa não é um módulo único, mas formado de diversos módulos que, para efeito do teste de unidade devem ser testados separadamente

### **Teste de Integração**

 - constrói-se, de uma forma sistemática, a estrutura do programa realizando, ao mesmo tempo, testes para detectar erros de interface
 - embora os módulos, depois do teste de unidade, funcionem corretamente de forma isolada, o teste de integração é necessário pois quando colocados juntos, várias situações inesperadas podem acontecer


Como faze-los, vai depender de varias variáveis, como, tipo de tecnologia, ambiente de controle de projeto, equipe de homologação, capacitação técnica,  entre outros fatores.