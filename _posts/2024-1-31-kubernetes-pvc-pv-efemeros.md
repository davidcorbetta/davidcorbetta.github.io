---
layout: post
title: Kubernetes - Storage - PV, PVC e Volumes Efêmeros
tags: infra kubernetes
---


#### **PV (Persistent Volume)**

Um PV é um recurso de armazenamento persistente que pode ser atribuído a pods. Isso significa que o armazenamento pode ser usado por vários pods ao mesmo tempo. Um PV é independente de qualquer pod específico que o use, o que significa que ele pode ser usado por pods diferentes ao longo do tempo.

Um PV pode ser criado por um admin ou por um plugin de armazenamento

Um PV pode ter uma classe, que define o tipo de armazenamento e as políticas de gerenciamento. Isso permite que o admin controlem o tipo de armazenamento que está disponível para os pods.

Mais detalhes sobre PV consulte a  [documentação oficial][1]

#### **PVC (Persistent Volume Claim)**

Um PVC é uma solicitação de armazenamento persistente feita por um usuário. Um PVC é semelhante a um pod. Pods consomem recursos de nó e PVCs consomem recursos de PV.

Um PVC pode solicitar níveis específicos de recursos (CPU e memória). Isso permite que os usuários controlem a quantidade de recursos que são usados pelo armazenamento.

Um PVC pode solicitar tamanho e modos de acesso específicos. Isso permite que os usuários controlem como o armazenamento é usado.

Mais detalhes sobre PVC consulte a [documentação oficial][2]

#### **Volumes Efêmeros**

Um volume efêmero é um volume que é criado e destruído com um pod. Isso significa que o armazenamento não é persistente.

Um volume efêmero é útil para dados que não precisam ser persistidos, como dados de sessão ou arquivos de log.

Mais detalhes sobre Efêmeros consulte a [documentação oficial][3]



[1]: https://kubernetes.io/docs/concepts/storage/persistent-volumes/

[2]: https://kubernetes.io/docs/concepts/storage/persistent-volumes/

[3]: https://kubernetes.io/docs/concepts/storage/ephemeral-volumes/
