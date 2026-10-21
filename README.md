# 🏥 Sistema de Atendimento Hospitalar — Triagem Digital

Projeto desenvolvido para a disciplina de **Programação e Sistemas Computacionais II** do curso de Engenharia de Software da **Faculdade Campo Real**, sob orientação do **Prof. Giovane Galvão**.

---

## 📌 Visão Geral do Sistema

O sistema simula a triagem e o atendimento de pacientes em um ambiente hospitalar utilizando **Estruturas de Dados Lineares (EDL)** construídas puramente em C++, sem o uso da biblioteca padrão (*Standard Template Library - STL*).

O fluxo funciona da seguinte forma:
1. **Fila de Pacientes (FIFO):** Os pacientes chegam e aguardam em uma fila de espera.
2. **Lista de Médicos (Lista Encadeada):** Médicos de plantão são alocados em ordem de disponibilidade. Ao atender um paciente, o médico retorna ao final da lista para o próximo ciclo de atendimentos.
3. **Histórico de Atendimentos (Pilha - LIFO):** Cada atendimento concluído é registrado no topo de uma pilha.
4. **Relatório do Dia:** Imprime o histórico completo dos atendimentos preservando os dados intactos através de uma pilha auxiliar.

---

## 🛠️ Estruturas de Dados Implementadas

- **`FilaPacientes` (Fila / FIFO):** Gerencia a fila de espera utilizando dois ponteiros (`frente` e `tras`).
- **`PilhaHistorico` (Pilha / LIFO):** Armazena os registros de atendimentos realizados.
- **`ListaMedicos` (Lista Simplesmente Encadeada):** Controla os médicos disponíveis com remoção no início e inserção no fim.
- **`imprimirHistorico`:** Função responsável por percorrer e imprimir a pilha do topo à base sem destruir a estrutura original.

---

## ⚙️ Compilação e Execução

### Pré-requisitos
- Compilador **g++** com suporte a **C++17**.

### Comandos de Compilação

Para compilar o código sem *warnings* e gerar o executável `atendimento`:

```bash
g++ -std=c++17 -Wall -o atendimento Aula16_atendimento_template.cpp
```

### Comandos de Execução

- **Linux / macOS / Git Bash:**
  ```bash
  ./atendimento
  ```

- **Windows (CMD / PowerShell):**
  ```cmd
  atendimento.exe
  ```

---

## 🖥️ Exemplo de Saída do Programa

```text
╔═══════════════════════════════════════════════════╗
║  Sistema de Atendimento — Squad                 ║
╚═══════════════════════════════════════════════════╝

Médicos disponíveis: Dra. Ana Lima -> Dr. Bruno Costa -> Dra. Carla Ramos

Pacientes chegando:
Próximo a ser atendido: Eduardo (urgencia=3)
Total na fila: 4

Simulação de atendimentos:
  [1] Dra. Ana Lima atende Eduardo (urgencia=3)
  [2] Dr. Bruno Costa atende Fernanda (urgencia=1)
  [3] Dra. Carla Ramos atende Gabriel (urgencia=2)
  [4] Dra. Ana Lima atende Helena (urgencia=1)

Último atendimento registrado (peek): Dra. Ana Lima → Helena (urgencia=1)

=== Relatório de Atendimentos ===
- Dra. Ana Lima → Helena (urgencia=1)
- Dra. Carla Ramos → Gabriel (urgencia=2)
- Dr. Bruno Costa → Fernanda (urgencia=1)
- Dra. Ana Lima → Eduardo (urgencia=3)

💡 Lembrete de commits:
  git add atendimento_template.cpp README.md
  git commit -m "feat: sistema de atendimento integrado (R1-R4)"
  git push origin main
```

---

## 👥 Integrantes do Squad

- **Carlos Eduardo Gomes da Silva**