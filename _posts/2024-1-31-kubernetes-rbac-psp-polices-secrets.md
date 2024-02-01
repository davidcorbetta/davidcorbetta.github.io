---
layout: post
title: Kuberentes - Security
tags: kubernetes infra security
---
#### **RBAC**
RBAC é um controle de segurança fundamental para garantir que os usuários e as cargas de trabalho do cluster tenham apenas acesso aos recursos necessários para executar suas funções. É importante garantir que, ao projetar permissões para usuários de cluster, o administrador do cluster entenda as áreas onde o escalonamento de privilégios pode ocorrer, para reduzir o risco de acesso excessivo que leve a incidentes de segurança.

A API RBAC impede que os usuários aumentem privilégios editando funções ou vinculações de funções. Como isso é imposto no nível da API, ele se aplica mesmo quando o autorizador RBAC não está em uso.

A API RBAC declara quatro tipos de objetos Kubernetes: `Role` , `ClusterRole` , `RoleBinding` e `ClusterRoleBinding`.

Exemplo de criação de uma role permitindo acesso básicos aos `pods`.
```
apiVersion: rbac.authorization.k8s.io/v1
kind: Role
metadata:
  namespace: default
  name: pod-reader
rules:
- apiGroups: [""] 
  resources: ["pods"]
  verbs: ["get", "watch", "list"]
```

Dessa forma podemos dar mais segurança aos componentes do Kubernetes, para mais detalhes e exemplos consulte a [documentação oficial sobre RBAC][1]



#### **Secrets**
Uma secret contém dados confidenciais, assim como senhas, tokens, kubeconfig. E conforme especificando acessos a secrets, somente componentes especificos do cluster terão acessos a esses dados, dessa forma não sendo necessário ter essas informações no código fonte de aplicação, assim tornando mais seguro a execução do código.

Exemplo de definição de uma secret:
```
apiVersion: v1
kind: Secret
metadata:
  name: my-secret
data:
  .secret-file: dmFsdWUtMg0KDQo=
---
apiVersion: v1
kind: Pod
metadata:
  name: secret-my-pod
spec:
  volumes:
    - name: secret-volume
      secret:
        secretName: my-secret
  containers:
    - name: my-test-container
      image: registry.k8s.io/busybox
      command:
        - ls
        - "-l"
        - "/etc/secret-volume"
      volumeMounts:
        - name: secret-volume
          readOnly: true
          mountPath: "/etc/secret-volume"
```
Dessa forma temos mais segurança ao executar nosas aplicações, mais detalhes, consulte a [documentação oficial sobre Secrets][3]





[1]: https://kubernetes.io/docs/reference/access-authn-authz/rbac/
[2]: https://kubernetes.io/docs/concepts/policy/pod-security-policy/
[3]: https://kubernetes.io/docs/concepts/configuration/secret/