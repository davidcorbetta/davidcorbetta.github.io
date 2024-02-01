---
layout: post
title: AWS - Network
tags: aws infra network
---
No contexto da rede na AWS, a comunicação eficiente entre Nodes, Pods e Containers é essencial para o funcionamento e [escalonamento das aplicações](2022-7-19-aplicacoes-escalaveis.md). Esses elementos desempenham papéis específicos na arquitetura de rede, garantindo a conectividade adequada e a troca de informações entre diferentes partes do sistema.

Observando a figura abaixo, temos um Node, e dentro dele temos pods, e dentro dos pods temos containers, segundo essa sequencia, vamos explicar a baixo a comunicação entre eles.

![image](../images/nodes.png)

#### **Nodes**

Cada Nó do Kubernetes executa pelo menos:

* O Kubelet, que é o processo responsável pela [comunicação entre a Camada de Gerenciamento e o Nó](https://kubernetes.io/docs/concepts/architecture/control-plane-node-communication/); gerencia os Pods e os contêineres rodando em uma máquina.
* Um agente de execução de contêiner (por exemplo, Docker) responsável por baixar a imagem do contêiner de um registro de imagens (por exemplo, o Docker Hub), extrair o contêiner e executar a aplicação.

Mais detalhes sobre nodes consulte a  [documentação oficial][1]

#### **Pods**

Cada pod recebe um endereço IP exclusivo para cada família de endereços. Cada contêiner em um pod compartilha o namespace da rede, incluindo o endereço IP e as portas de rede. Dentro de um pod (e somente então), os contêineres que pertencem ao pod podem se comunicar entre si usando localhost. 

Quando os contêineres em um pod se comunicam com entidades fora do pod, eles devem coordenar a forma como usam os recursos de rede compartilhados (como portas). Dentro de um pod, os contêineres compartilham um endereço IP e espaço de porta e podem se encontrar por meio de arquivos localhost.


Mais detalhes sobre Pods consulte a [documentação oficial][3]

#### **Containers**

Dentro de um pod podemos ter varios containers, cada um responsavel por algo, se dois containers estão no mesmo pod, eles podem se comunicar diretamente via localhost.

Os contêineres dentro do pod consideram o nome do host do sistema igual ao configurado name para o pod.

Mais detalhes sobre containers consulte a [documentação oficial][3]



[1]: https://kubernetes.io/docs/concepts/architecture/nodes/

[2]: https://kubernetes.io/docs/concepts/workloads/pods/

[3]: https://kubernetes.io/docs/concepts/containers/
