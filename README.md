# 🚀 Descomplicando o Kubernetes | LinuxTips

Bem-vindo ao meu repositório de estudos do curso **Descomplicando Kubernetes** da [LinuxTips](https://linuxtips.io)! 🚢

Este repositorio é onde deixo meus laboratórios práticos e os estudos realizados durante o curso. Aqui você encontrará todos os manifestos YAML e configurações de infraestrutura que utilizei para consolidar meu aprendizado sobre um dos orquestradores de contêineres mais populares do mundo.

---

## 📑 Índice

- [🎯 Sobre o Projeto](#-sobre-o-projeto)
- [🛠️ Pré-requisitos](#-pré-requisitos)
- [🗺️ Roteiro de Estudos (Estrutura)](#-roteiro-de-estudos-estrutura)
- [🚀 Como Utilizar](#-como-utilizar)
- [🛡️ Segurança e Boas Práticas](#-segurança-e-boas-práticas)
- [📜 Licença](#-licença)
- [👨‍💻 Sobre Mim](#-sobre-mim)

---

## 🎯 Sobre o Projeto

Este repositório reúne **manifestos Kubernetes** (`*.yaml`) construídos e testados ao longo do curso. Ele abrange desde a criação básica de Pods até configurações avançadas de Ingress, Storage e StatefulSets.

**Os principais objetivos deste repositório são:**
- Servir como um guia de referência rápida e didática para consultas futuras.
- Documentar a evolução prática dos conceitos aprendidos.
- Compartilhar um ambiente de laboratório funcional (via Vagrant) para quem desejar replicar os estudos.

---

## 🛠️ Pré-requisitos

Para tirar o máximo proveito deste repositório, recomendo que você tenha as seguintes ferramentas instaladas:

| Ferramenta | Descrição e Uso |
| :--- | :--- |
| ☸️ **[kubectl](https://kubernetes.io/docs/tasks/tools/)** | A ferramenta de linha de comando essencial para interagir e gerenciar os recursos no cluster. |
| 🐳 **Ambiente K8s** | Um cluster rodando (pode ser o Minikube, kind, k3s, cloud gerenciada ou as VMs do laboratório). |
| 📦 **[Vagrant](https://www.vagrantup.com/)** | *(Opcional)* Necessário apenas se desejar subir o laboratório local com máquinas virtuais (disponível na pasta `vagrant-vms/`). |

---

## 🗺️ Roteiro de Estudos (Estrutura)

O projeto está organizado cronologicamente, acompanhando a evolução das aulas do curso:

- **`day-01/`** ➡️ Introdução: Pods e ConfigMaps.
- **`day-02/`** ➡️ Gerenciamento de Recursos: Pods, volumes simples e limites de CPU/Memória.
- **`day-03/`** ➡️ Escalabilidade: Trabalhando com Deployments.
- **`day-04/`** ➡️ Resiliência: ReplicaSets, DaemonSets e configuração de Probes (Liveness/Readiness).
- **`day-05/`** ➡️ Armazenamento (Parte 1): Introdução aos StorageClasses.
- **`day-06/`** ➡️ Armazenamento (Parte 2): Volumes Persistentes (PV), Claims (PVC) e NFS.
- **`day-07/`** ➡️ Exposição e Estado: Services (ClusterIP, NodePort, LoadBalancer, Headless) e StatefulSets.
- **`day-08/`** ➡️ Segurança: Gerenciamento de Secrets, certificados TLS e acesso a Registries Privados.
- **`day-09/`** ➡️ Tráfego Externo: Ingress (incluindo setup no `kind`), integração com Redis e deploy de uma aplicação completa.
- **`vagrant-vms/`** ➡️ Laboratório: Arquivos Vagrant para provisionamento de VMs Rocky Linux.
---

## 🚀 Como Utilizar

Siga estes passos para explorar os manifestos no seu próprio ambiente:

### 1. Clonar o repositório
```bash
git clone [https://github.com/lucasferreira1107/LinuxTips-DK8s.git](https://github.com/lucasferreira1107/DescomplicandoKubernetes-Linuxtips.git)
cd DescomplicandoKubernetes-Linuxtips
```

### 2. Verificar o Contexto do Cluster
Certifique-se de que o seu `kubectl` está apontando para o cluster correto antes de aplicar qualquer arquivo:
```bash
kubectl config current-context
kubectl cluster-info
```

### 3. Aplicar os Manifestos
Navegue até o dia desejado e aplique os recursos. Por exemplo, para lançar um Pod de testes do dia 2:
```bash
kubectl apply -f day-02/pod.yaml
kubectl get pods -w
```

### 4. Subir o Laboratório Vagrant (Opcional)
Se não tiver um cluster e quiser usar o ambiente disponibilizado na pasta `vagrant-vms/`:
```bash
cd vagrant-vms/rocky-linux
vagrant up
```
