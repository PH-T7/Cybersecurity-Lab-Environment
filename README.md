[Português](#laboratório-de-cibersegurança-e-análise-de-malware-iso-lab-01) | [English](#cybersecurity--malware-analysis-laboratory-iso-lab-01)

---

# Laboratório de Cibersegurança e Análise de Malware (ISO-LAB-01)

> **Objetivo:** Criar um ambiente isolado de alta performance para estudos de Pentest e Engenharia Reversa, utilizando virtualização de baixo nível.

---

## 1. Especificações do Host
O hardware foi configurado para suportar múltiplas instâncias de virtualização com foco em estabilidade e performance.

* **Processador:** AMD Ryzen 5 4600G
* **Memória:** 32GB RAM DDR4
* **Gráficos:** * **AMD Radeon Vega 7** (Dedicada via IOMMU para a VM)
    * **NVIDIA RTX 3070** (Utilizada pelo Host Linux Mint)
* **Sistema Operacional:** Linux Mint (Base Debian/Ubuntu)

### Configuração de Hardware (BIOS/UEFI)
Para viabilizar o **GPU Passthrough**, foram habilitados recursos avançados na placa-mãe:
* **IOMMU:** Ativado para permitir o isolamento de dispositivos PCI.
* **UMA Frame Buffer:** Alocação de 2GB de VRAM para a GPU integrada.

![Configuração IOMMU](img/IOMMU.png)
*Legenda: Habilitação do suporte IOMMU na BIOS Gigabyte.*

![Frame Buffer](img/BufferSizeBios.png)
*Legenda: Alocação de 2GB para o UMA Frame Buffer Size.*

---

## 2. Arquitetura da Máquina Virtual (Kali Linux)
A VM foi configurada via **KVM/QEMU** para garantir o menor overhead possível.

* **Hipervisor:** Virt-Manager (KVM/QEMU).
* **Recursos:** 8GB RAM | 60GB Armazenamento (QCOW2).
* **Aceleração Gráfica:** GPU Passthrough nativo da Vega 7.

![Virt-Manager Management](img/Virt.png)
*Legenda: Gerenciamento da VM KaliLinux em execução via Virt-Manager.*

![Instalação do Sistema](img/BaixandoVm.png)
*Legenda: Processo de deploy e instalação do sistema básico Kali.*

---

## 3. Ambiente de Operação e Networking
O sistema operacional convidado (Guest) utiliza a interface GNOME 47.1 e ferramentas de rede para laboratórios externos.

* **Interface:** GNOME 47.1 com aceleração via hardware (GPU 2: AMD Radeon Vega Series).
* **Rede Mesh:** Implementação do **Tailscale** (IP 100.123.211.8) para acesso remoto seguro.
* **VPN de Laboratório:** Conexão via **OpenVPN** para plataformas como TryHackMe.

![Desktop Kali Linux](img/Kali1.png)
*Legenda: Dashboard do sistema com Fastfetch exibindo a aceleração via Vega 7 e rede Tailscale ativa.*

![OpenVPN Conectado](img/Kali2.png)
*Legenda: Túnel OpenVPN estabelecido com sucesso para laboratórios de Pentest.*

---

## 4. Segurança e Isolamento
Seguindo as melhores práticas de cibersegurança, o ambiente mantém um protocolo rígido de **"No-Personal-Data"**, garantindo que malwares (como Infostealers) não tenham acesso a credenciais sensíveis do Host ou do usuário.

# Cybersecurity & Malware Analysis Laboratory (ISO-LAB-01)

> **Objective:** To create a high-performance, isolated environment for Pentesting and Reverse Engineering studies using low-level virtualization.

---

## 1. Host Specifications
The hardware was specifically configured to support advanced virtualization workloads with focus on stability and performance.

* **CPU:** AMD Ryzen 5 4600G [cite: 2025-10-21]
* **RAM:** 32GB DDR4 [cite: 2025-10-21]
* **Graphics:** * **AMD Radeon Vega 7** (Dedicated via IOMMU for the VM)
    * **NVIDIA RTX 3070** (Primary GPU for Linux Mint Host) [cite: 2025-10-21]
* **Host OS:** Linux Mint (Debian/Ubuntu-based for rock-solid stability) [cite: 2025-10-21]

### Hardware Configuration (BIOS/UEFI)
To enable **GPU Passthrough**, the following advanced features were enabled:
* **IOMMU:** Activated for PCI device isolation.
* **UMA Frame Buffer:** Allocated 2GB VRAM for the integrated GPU.

![IOMMU Configuration](img/IOMMU.png)
*Caption: Enabling IOMMU support on Gigabyte BIOS.*

---

## 2. Virtual Machine Architecture (Kali Linux)
The guest system is managed via **KVM/QEMU** to ensure minimal overhead and near-native performance.

* **Hypervisor:** Virt-Manager (KVM/QEMU)
* **Allocated Resources:** 8GB RAM | 60GB Storage (QCOW2 format) [cite: 2025-10-21]
* **Graphics Optimization:** Native GPU Passthrough (Vega 7) for hardware acceleration on GNOME 49.1.

![Virt-Manager](img/Virt.png)
*Caption: Running Kali Linux instance via Virt-Manager.*

---

## 3. Networking and Security (The Professional Edge)
Advanced networking layers implemented for both mobility and defensive protocols.

* **Mesh Network:** **Tailscale** implementation for secure, encrypted remote access (IP 100.x.x.x).
* **Lab Connectivity:** **OpenVPN** tunnel configuration for practice platforms (TryHackMe / HackTheBox).
* **Data Isolation:** Strict **"No-Personal-Data"** protocol within the VM. This ensures that analysis of suspicious binaries or malware (e.g., Infostealers) does not compromise host credentials or sensitive information [cite: 2025-10-21].

![Desktop Kali Linux](img/Kali1.png)
*Caption: System dashboard showing hardware-accelerated graphics and active Tailscale mesh network.*

---

## 4. Professional Roadmap
This environment is currently being used as a primary training ground for:
* **Huawei ICT Competition 2025-2026** (Network Track).
* **ISC2 Certified in Cybersecurity (CC)** studies [cite: 2025-10-21].
