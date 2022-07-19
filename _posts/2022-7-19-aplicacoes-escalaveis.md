---
layout: post
title: Aplicações Escaláveis - resumo/básico
tags: scalability infra
---
Uma aplicação escalável ou escalonável, é uma aplicação que consegue atender um número maior de usuários ou requisição, mantendo um tempo de resposta apropriado.

Uma arquitetura escalonável é focada para resolver problemas de sobrecarga de acesso, ou aumento da carga de trabalho (***workload***), e a partir dai gerenciar melhor os recursos, para evitar um custo gigante com toda essa estrutura que podemos gerenciar.

Basicamente:
```
Quanto > Aplicação = + Usuários + requisições = > infra = > Custo
```

### **Dimensionamento**
Ter cargas de trabalho maior sobre a infra.

#### **Vertical**
```
Servidor = + CPU + MEM
```
 
#### **Horizontal**
```
Instância 1 ou Instância 2 ou Instância 3, etc. -> Danco de Dados
```

#### **Balanceador de carga:**

```bash
                                         |->  Instância 1 -> | 
Requisição -> [balanceador de carga] ->  |->  Instância 2 -> | -> Danco de Dados
                                         |->  Instância 3 -> | 
```

#### **Dimensionamento Automatizado:**
```
Capacidade > X% = + Instâncias
Capacidade < X% = - Instâncias
```

### **Camada de Cache:**
Armazena e compartilha sessões, armazenar informações com pouca alterção de forma a
economizar e melhorar desempenho.

<hr>
<sub>Fonte: https://dev.to/lucascavalcante/mas-afinal-o-que-e-significa-escalar-a-aplicacao-4kc7 </sub>
