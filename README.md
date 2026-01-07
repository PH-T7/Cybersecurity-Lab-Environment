# Laboratório de Cibersegurança e Análise de Malware

> **Objetivo:** Criar um ambiente isolado e de alta performance para estudos de Pentest e Engenharia Reversa.

---

## 1. Especificações do Host
Este ambiente foi projetado para maximizar a utilização de recursos de hardware através de virtualização de baixo nível.

* **Processador:** AMD Ryzen 5 4600G
* **Memória:** 32GB RAM
* **Gráficos:** * AMD Radeon Vega 7 (Dedicada via IOMMU para a VM)
    * NVIDIA RTX 3070 (Host)
* **Sistema Operacional:** Linux Mint (Base Debian/Ubuntu para estabilidade)

## 2. Arquitetura da Máquina Virtual (Kali Linux)
O setup utiliza tecnologias de virtualização de alto desempenho para garantir uma experiência próxima ao hardware nativo.

* **Hipervisor:** KVM/QEMU via Virt-Manager
* **Recursos Alocados:** 8GB RAM | 60GB de Armazenamento (Formato QCOW2)
* **Otimização:** GPU Passthrough da Vega 7 para aceleração gráfica nativa no GNOME 47.1 (com 2GB de VRAM alocados).

## 3. Networking e Segurança (Diferencial Técnico)
Implementação de camadas de rede para mobilidade e proteção de dados.

* **Rede Mesh:** Implementação do **Tailscale** para acesso remoto seguro através de IP dedicado (100.x.x.x).
* **Acesso a Labs:** Configuração de túnel **OpenVPN** para plataformas de prática (TryHackMe / HackTheBox).
* **Isolamento de Dados:** Protocolo de "No-Personal-Data" dentro da VM para análise segura de binários suspeitos e malwares (Infostealers).
