## Docker e Docker-Compose no Windows: Guia CLI "Zero Desktop"

Este guia ensina como configurar um ambiente de containers no Windows sem o peso do **Docker Desktop**, sem necessidade de gerenciar distros no **WSL** manualmente e utilizando apenas a **linha de comando**.

### 🚀 Benefícios desta Abordagem
* **Performance:** Economia de até 2GB de RAM em comparação ao Docker Desktop.
* **Simplicidade:** Sem interfaces gráficas ou processos pesados em background.
* **CLI nativa:** Use os comandos `docker` e `docker-compose` exatamente como faria no Linux.

---

### 1. Instalação do Motor (Podman)
O Podman é um motor de containers open-source e *daemonless*. Instale-o via **Winget** (nativo do Windows):

```powershell
winget install -e --id RedHat.Podman

```

### 2. Inicialização da Engine

O Podman gerencia sua própria máquina virtual leve. Execute uma única vez para configurar:

```powershell
# Cria a máquina virtual do Podman
podman machine init

# Inicia o serviço
podman machine start

```

### 3. Suporte ao Docker Compose

O suporte ao Compose é adicionado via Python. Certifique-se de ter o Python instalado e execute:

```powershell
# Instalação do módulo podman-compose
pip install podman-compose

```

### 4. Configuração de Aliases (PowerShell)

Para que o seu terminal reconheça os comandos `docker` e `docker-compose`, adicione estas funções ao seu perfil do PowerShell:

1. No terminal, execute: `notepad $PROFILE`
2. Cole o conteúdo abaixo e salve:

```powershell
# Atalho para Docker
function docker { & podman $args }

# Atalho para Docker-Compose (via módulo Python)
function docker-compose { & python -m podman_compose $args }

```

3. Recarregue a sessão no terminal atual: `. $PROFILE`

---

### 🛠️ Cheat Sheet de Uso Diário

| Comando | Função |
| --- | --- |
| `podman machine start` | Liga o motor de containers (necessário após boot) |
| `podman machine stop` | Desliga o motor para economizar recursos |
| `docker ps` | Lista os containers em execução |
| `docker-compose up -d` | Sobe o stack definido no `docker-compose.yml` |
| `docker-compose down` | Derruba o stack e remove redes/containers |
| `docker logs -f [nome]` | Visualiza logs em tempo real |

---

> **Nota:** Se ao rodar `docker-compose` você encontrar avisos de *DeprecationWarning*, não se preocupe. Eles são apenas informativos sobre versões futuras do Python e não afetam o funcionamento dos seus containers.

```

Precisa que eu adicione mais alguma seção específica, como configuração de volumes ou redes?

```
