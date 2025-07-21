---
layout: default
title: Início
---

# ☸️ Introdução ao Kubernetes

## 📌 O que é o Kubernetes?

Kubernetes é um **orquestrador de containers** projetado para automatizar o _deploy_, gerenciamento, escalabilidade e alta disponibilidade de aplicações conteinerizadas.

🔍 **Exemplo prático:**  
Imagine que você tenha um ambiente com Docker. Se precisar de alta disponibilidade, escalabilidade automática e gerenciamento mais avançado dos containers, apenas Docker ou Docker Compose não serão suficientes.  
O Kubernetes entra como **o maestro de uma orquestra**, onde os containers são os músicos. Ele coordena, organiza e garante que tudo funcione de forma harmônica.

---

## 🕰️ História e Evolução

O Kubernetes foi criado pela **Google em 2014**, utilizando a linguagem **Go (Golang)**.  
Ele se inspira em um projeto interno do Google chamado **Borg**, e compartilha alguns princípios fundamentais:

- ✅ **Gerenciamento declarativo:** infraestrutura como código, permitindo versionamento e reprodutibilidade.
- 🔁 **Autocorreção:** o cluster identifica e corrige automaticamente falhas nos recursos.
- 📈 **Escalabilidade horizontal:** quando a demanda por requisições aumenta, o Kubernetes pode replicar instâncias da aplicação para atender a essa carga — **sem adicionar memória**, apenas distribuindo as requisições.
- ⚖️ **Distribuição de carga:** balanceamento automático entre instâncias.

Em 2015, com o lançamento da versão 1.0, o Kubernetes foi doado à **Cloud Native Computing Foundation (CNCF)**, com o objetivo de fomentar a adoção pela comunidade e remover o controle exclusivo da Google.  
Hoje, é um dos projetos open source mais influentes do mundo.

---

## ☁️ Ecossistema CNCF

A **Cloud Native Computing Foundation (CNCF)** é responsável por manter o Kubernetes e um ecossistema vasto de ferramentas **open source**.

Alguns projetos mantidos pela CNCF:

- 📊 [Prometheus](https://prometheus.io/) — Monitoramento e alertas
- ⛵ [Helm](https://helm.sh/) — Gerenciador de pacotes do Kubernetes
- 🔄 [Argo Workflows / Argo CD](https://argo-cd.readthedocs.io/) — CI/CD e automação de pipelines

💡 A CNCF também oferece a certificação **CKA (Certified Kubernetes Administrator)**, que valida conhecimento prático em administração de clusters Kubernetes.

---

## 💼 Casos de Uso

O Kubernetes é ideal para:

- Migrar para uma arquitetura de **microsserviços**
- Implementar **plataformas de CI/CD**
- Gerenciar **ambientes híbridos ou multi-cloud**
- **Escalar aplicações** automaticamente
- Garantir **alta disponibilidade e resiliência**

---

## 🏗️ Arquitetura do Kubernetes

### 🎛️ Control Plane (Master Nodes)

Responsável por **gerenciar o estado do cluster** e tomar decisões de agendamento e controle.

#### 🔹 Kube-API Server
É o **componente central** do cluster. Atua como uma interface entre usuários, componentes internos e ferramentas externas.  
Responsável por receber requisições (via CLI, UI ou API), autenticar, validar e redirecionar para os demais componentes.

#### 🔹 etcd (Database)
Um banco de dados **chave-valor distribuído**, que armazena todo o estado do cluster (pods, deployments, configurações, etc).  
👉 Se o `etcd` falhar e não houver backup, o **estado do cluster é perdido**.

📌 **Importante:** Em provedores de nuvem (como AWS EKS), não temos acesso direto ao Control Plane — ele é abstraído pelo serviço gerenciado.

---

### ⚙️ Node Plane (Worker Nodes)

Os **Worker Nodes** são os nós responsáveis por **executar os containers** (nossas aplicações).

- Recebem tarefas do Control Plane.
- Hospedam os pods e serviços da aplicação.
- Mais nodes = mais capacidade, escalabilidade e resiliência.

👉 Você pode entendê-los como **máquinas virtuais (VMs)** ou **instâncias físicas**.

---

## 🧱 Principais Objetos do Kubernetes

- ### 🧩 **Pod**
  Unidade básica de execução no Kubernetes. Pode conter um ou mais containers.

- ### 📦 **ReplicaSet**
  Garante que um número específico de réplicas de um pod esteja sempre rodando.

- ### 🚀 **Deployment**
  Controla o ciclo de vida de aplicações: criação, atualização e rollback de pods e ReplicaSets.

- ### 🗂️ **Namespace**
  Permite organizar recursos dentro do cluster, separando ambientes como `dev`, `staging` e `prod`.

- ### 🌐 **Service**
  Abstração para expor uma aplicação em execução como um serviço de rede, facilitando o acesso e o balanceamento de carga.

---

Se quiser, posso ajudar a transformar este conteúdo em um site com [GitHub Pages + Jekyll](https://pages.github.com/) ou [MkDocs](https://www.mkdocs.org/), além de criar uma navegação e layout visual melhores.
