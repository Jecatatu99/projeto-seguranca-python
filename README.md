# 🛡️ Laboratório Prático: Simulação de Malware e Análise Defensiva (Python)

[![Python Version](https://img.shields.io/badge/Python-3.x-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Status](https://img.shields.io/badge/Status-Concluído-success.svg)]()

Repositório desenvolvido para fins **estritamente educacionais e de pesquisa**, criado no âmbito de estudos de segurança cibernética defensiva. O projeto demonstra, de forma prática e em ambiente controlado, o comportamento básico de ameaças digitais comuns (**Ransomware** e **Keylogger**), além de documentar estratégias fundamentais de mitigação e defesa.

---

## 📑 Sumário
1. [Sobre o Projeto](#-sobre-o-projeto)
2. [Tecnologias Utilizadas](#-tecnologias-utilizadas)
3. [Estrutura do Repositório](#-estrutura-do-repositório)
4. [Guia de Instalação e Execução](#-guia-de-instalação-e-execução)
   - [1. Ransomware Simulado](#1-ransomware-simulado)
   - [2. Keylogger Simulado](#2-keylogger-simulado)
5. [Análise Comportamental e Mecanismos de Ameaça](#-análise-comportamental-e-mecanismos-de-ameaça)
6. [Estratégias de Defesa e Mitigação](#-estratégias-de-defesa-e-mitigação)
7. [Aviso Legal](#️-aviso-legal)

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
