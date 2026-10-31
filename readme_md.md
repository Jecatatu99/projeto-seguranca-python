# 🛡️ Laboratório Prático: Simulação de Malware e Análise Defensiva (Python)

[![Python Version](https://img.shields.io/badge/Python-3.x-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Status](https://img.shields.io/badge/Status-Conclu%C3%ADdo-success.svg)]()

Repositório desenvolvido para fins **estritamente educacionais e de pesquisa**, criado no âmbito de estudos de segurança cibernética defensiva. O projeto demonstra, de forma prática e em ambiente controlado, o comportamento básico de ameaças digitais comuns (**Ransomware** e **Keylogger**), além de documentar estratégias fundamentais de mitigação e defesa.

---

## 🎯 Sobre o Projeto
O objetivo principal deste laboratório é compreender o ciclo de vida e a lógica por trás de ataques cibernéticos simulados para, em contrapartida, desenhar barreiras de proteção mais eficientes. O projeto aborda duas vertentes:
* **Sequestro de Dados (Ransomware):** Demonstração do uso de criptografia simétrica para indisponibilizar dados e a emissão de notificações de resgate.
* **Captura de Informações (Keylogger):** Demonstração de como interceptações de hardware/software podem registrar dados confidenciais digitados pelo usuário.

---

## 🛠️ Tecnologias Utilizadas
* **Python 3.x** — Linguagem principal de programação.
* **Cryptography (Fernet)** — Biblioteca para implementação de criptografia simétrica (AES).
* **pynput** — Biblioteca para monitoramento e controle de eventos de entrada (teclado e mouse).

---

## 📂 Estrutura do Repositório
```text
.
├── README.md                  # Documentação detalhada do laboratório
├── .gitignore                 # Arquivos sensíveis/temporários ignorados pelo Git
├── ransomware_simulador.py    # Script de criptografia, descriptografia e nota de resgate
└── keylogger_simulador.py     # Script de captura e registro local de teclas
```

---

## 🚀 Guia de Instalação e Execução

### Pré-requisitos
Certifique-se de ter o Python instalado na sua máquina. Em seguida, clone o repositório e instale as dependências necessárias:

```bash
# Clone o repositório
git clone https://github.com/SEU-USUARIO/SEU-REPOSITORIO.git
cd SEU-REPOSITORIO

# Instale as bibliotecas necessárias
python -m pip install cryptography pynput
```

### 1. Ransomware Simulado (`ransomware_simulador.py`)
Este script simula o fluxo completo de um ransomware educacional:
1. Cria um arquivo de texto de teste (`arquivo_teste.txt`).
2. Gera uma chave criptográfica segura e embaralha os dados do arquivo.
3. Cria um arquivo de aviso de resgate (`AVISO_RESGATE.txt`).
4. Permite simular a recuperação dos dados através da chave ao pressionar `ENTER`.

**Como executar:**
```bash
python ransomware_simulador.py
```

### 2. Keylogger Simulado (`keylogger_simulador.py`)
Este script demonstra a captura de teclas em segundo plano, salvando os registros em um arquivo de texto local para ilustrar o risco de exfiltração de credenciais.

**Como executar:**
```bash
python keylogger_simulador.py
```
*(Para encerrar a captura e salvar os dados no arquivo `log_teclas.txt`, basta pressionar a tecla **`ESC`**).*

---

## 🔬 Análise Comportamental e Mecanismos de Ameaça

* **Ransomware:** No cenário real, variantes modernas utilizam algoritmos de criptografia para indisponibilizar dados e forçar o pagamento de resgates. A infecção costuma ocorrer via phishing, exploração de vulnerabilidades não corrigidas ou macros maliciosas.
* **Keylogger:** Atua monitorando as interrupções de hardware do teclado (hooks do sistema operacional). A ameaça reside na capacidade de capturar senhas, números de cartões de crédito e mensagens privadas antes mesmo de serem criptografadas pela aplicação de destino.

---

## 🛡️ Reflexão sobre Defesa e Prevenção

A melhor estratégia contra malwares como Ransomwares e Keyloggers é a **defesa em profundidade** (aplicação de múltiplas camadas de proteção). Abaixo estão descritas as principais medidas preventivas e defensivas:

### 1. 🛡️ Antivírus e Soluções EDR (Endpoint Detection and Response)
* **Prevenção contra Ransomware:** Soluções modernas de antivírus e EDR monitoram o comportamento do sistema em tempo real. Elas detectam padrões anômalos, como a criptografia rápida e em massa de múltiplos arquivos, bloqueando o processo malicioso e isolando a máquina antes que o dano se espalhe.
* **Prevenção contra Keylogger:** Identificam assinaturas conhecidas de softwares espiões e bloqueiam chamadas de sistema suspeitas executadas por aplicações não autorizadas.

### 2. 🧱 Firewall (Rede e Host)
* **Bloqueio de Exfiltração:** Um firewall configurado corretamente monitora e filtra o tráfego de entrada e saída. No caso de um **Keylogger**, ele impede que o script envie os dados capturados (logs de teclas) para um servidor externo do atacante ou via e-mail.
* **Controle de Perímetro:** Dificulta a movimentação lateral de um **Ransomware** na rede local, impedindo que o malware infecte outros computadores e servidores conectados.

### 3. 📦 Sandboxing e Isolamento de Ambientes
* **Análise Segura:** O *sandboxing* consiste em executar arquivos, scripts ou anexos suspeitos em um ambiente virtual isolado e seguro antes de permiti-los no sistema principal.
* **Mitigação de Impactos:** Permite aos analistas de segurança observar a execução do código (se ele tenta alterar registros do sistema, criar arquivos ocultos ou criptografar pastas) sem colocar em risco a infraestrutura da organização.

### 4. 👥 Conscientização do Usuário e Treinamento em Cibersegurança
* **Combate ao Phishing:** A grande maioria dos ataques começa com engenharia social — e-mails maliciosos com anexos ou links falsos.
* **Boas Práticas de Navegação:** Treinar usuários para reconhecer sinais de e-mails suspeitos, não baixar executáveis de fontes não confiáveis e reportar incidentes rapidamente é a primeira e mais eficaz linha de defesa.

---

## 🔄 Outras Medidas Complementares
* **Política de Backup 3-2-1:** Manter 3 cópias dos dados, em 2 mídias diferentes, sendo **1 cópia mantida offline (air-gapped)**. É a única garantia de restauração sem depender do pagamento de resgate.
* **Princípio do Menor Privilégio (PoLP):** Garantir que usuários comuns não tenham privilégios de administrador para instalar softwares ou executar scripts de origem desconhecida.

---

## ⚠️ Aviso Legal
> *Este software foi desenvolvido exclusivamente para fins educacionais e de conscientização em segurança da informação. A execução de códigos de simulação de ameaças em ambientes de produção ou em dispositivos de terceiros sem consentimento prévio e explícito é estritamente proibida e constitui atividade ilegal.*