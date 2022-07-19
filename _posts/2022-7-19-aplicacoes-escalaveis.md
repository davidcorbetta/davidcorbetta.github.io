---
layout: post
title: Aplicações Escaláveis - resumo/básico
tags: scalability infra
---

Uma aplicação escalável ou escalonável, é uma aplicação que consegue atender um número maior de usuários ou requisição, mantendo um tempo de resposta apropriado.

Uma arquitetura escalonável é focada para resolver problemas de sobrecarga de acesso, ou aumento da carga de trabalho (***workload***), e a partir dai gerenciar melhor os recursos, para evitar um custo gigante com toda essa estrutura que podemos gerenciar.

Então, basicamente:
> Quanto > Aplicação = + Usuários + requisições = > infra = > Custo

### **Dimensionamento**
Ter cargas de trabalho maior sobre a infra.
#### **Vertical**
> Servidor = + CPU + MEM
#### **Horizontal**
Balanceador de carga:
> Requisição -> Instância 1 ou Instância 2 ou Instância 3, etc.

Auto scaling:
> Capacidade > X% = + Instâncias
> Capacidade < X% = - Instâncias
