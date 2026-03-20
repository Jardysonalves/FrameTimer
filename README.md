# ⚡ FrameCap Optimizer DLL

<p align="center">
  <img src="https://img.shields.io/badge/Status-Stable-success?style=for-the-badge" alt="Status">
  <img src="https://img.shields.io/badge/Architecture-x86_64-blue?style=for-the-badge" alt="Arch">
  <img src="https://img.shields.io/badge/Optimization-High_Performance-orange?style=for-the-badge" alt="Optimization">
</p>

> **FrameCap** é um otimizador de baixo nível escrito em C++ focado em extrair o máximo de performance em hardwares limitados (como o Intel i3-3240). Ele atua diretamente no Kernel do Windows e no subsistema gráfico para eliminar gargalos de RAM e VRAM.

---

### 🚀 Funcionalidades Principais

* **🧹 RAM Purge (Working Set):** Força o Windows a liberar memória física não utilizada, movendo o "lixo" para o arquivo de paginação.
* **🎮 GPU Driver Reset:** Executa um refresh via hardware (`Win+Ctrl+Shift+B`) para limpar caches de Shaders e Vertex corrompidos na VRAM.
* **⚖️ CPU Priority Hook:** Ajusta automaticamente a prioridade do processo para `HIGH_PRIORITY_CLASS`, reduzindo micro-stutters.
* **💾 Disk Cache Management:** Reduz o overhead do cache de sistema no disco rígido para acelerar o streaming de texturas.

---

### 🛠️ Estrutura do Código

Otimizado para ser compilado via **w64devkit (GCC 15.2.0)**, garantindo um binário extremamente leve (~31KB).

#### 🧬 Core Logic
* [cite_start]`ForcePerformance()`: Gerencia memória física e prioridade de ciclos da CPU. 
* [cite_start]`CleanSystem()`: Realiza o reset do driver gráfico e limpeza de buffers de disco. 
* [cite_start]`DllMain`: Ponto de entrada que executa todas as otimizações no momento da injeção (`DLL_PROCESS_ATTACH`). 

---
