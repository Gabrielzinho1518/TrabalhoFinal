# TrabalhoFinal
# 🏠 Projeto: Sistema de Alarme Residencial  
**Integrantes:**  Gabriel Saccol e Gilberto Morales  

---

[Sistema-de-Alarme-Residencial-FSM-Conceitos-e-Implementacao-em-VHDL (1).pdf]


## 🎯 Objetivo do Circuito
O objetivo deste projeto é desenvolver, em **VHDL utilizando o Vivado**, um **sistema de alarme residencial digital** capaz de representar três estados principais de operação:  
1. **Desativado** – o sistema está inativo, sem monitoramento;  
2. **Ativado** – o sistema está em vigilância, pronto para detectar invasões;  
3. **Disparado** – o alarme é acionado após a detecção de uma invasão.  

O projeto busca aplicar conceitos de **Máquinas de Estados Finitos (FSM)**, **portas lógicas**, **flip-flops** e **simulação digital**, simulando o comportamento de um sistema de segurança real.

---

## 🧠 Diagrama de Estados (FSM)
A FSM (Finite State Machine) do sistema possui **três estados** principais e **transições controladas por sinais de entrada**:

       +-------------------+
       |                   |
       |   [S1] DESATIVADO |
       |                   |
       +---------+---------+
                 |
         (botão ligar)
                 v
       +-------------------+
       |                   |
       |   [S2] ATIVADO    |
       |                   |
       +---------+---------+
                 |
         (sensor = 1)
                 v
       +-------------------+
       |                   |
       |   [S3] DISPARADO  |
       |                   |
       +---------+---------+
                 |
         (botão reset)
                 v
       +-------------------+
       |   DESATIVADO      |
       +-------------------+


---

## ⚙️ Explicação do Funcionamento Passo a Passo

1. **Estado Desativado (S1)**  
   - O sistema inicia neste estado.  
   - O alarme está inativo.  
   - Ao pressionar o **botão de ativar**, o sistema muda para o estado **Ativado**.  

2. **Estado Ativado (S2)**  
   - O alarme está monitorando o ambiente.  
   - Caso o **sensor** detecte uma presença (sinal = ‘1’), o estado muda para **Disparado**.  
   - Caso contrário, permanece **Ativado**.  

3. **Estado Disparado (S3)**  
   - O alarme é acionado (saída = ‘1’).  
   - Para desligar o alarme, é necessário pressionar o **botão de reset**, retornando ao estado **Desativado**.  

---

## 💻 Estrutura do Repositório

---

## 🧩 Funcionamento Interno (Descrição Técnica)
- **Entradas:**  
  - `clk`: sinal de clock.  
  - `reset`: retorna o sistema ao estado desativado.  
  - `ativar`: ativa o sistema.  
  - `sensor`: sinal de detecção.  

- **Saídas:**  
  - `alarme`: indica se o alarme está disparado (1 = ligado, 0 = desligado).  
  - `estado`: mostra o estado atual (00 = desativado, 01 = ativado, 10 = disparado).  

- **Tecnologia usada:** VHDL (linguagem de descrição de hardware)  
- **Software:** Xilinx Vivado 2015.1  

---

## 🧾 Conclusão

Durante o desenvolvimento deste projeto, foi possível compreender de forma prática:
- A implementação de **máquinas de estados** em VHDL;  
- O uso de **simulações digitais** para validar o comportamento do sistema;  
- A importância da **organização do projeto no Vivado**;  
- A relação entre **entradas, estados e saídas** em sistemas digitais.  

### 🧠 Aprendizados
- Controle de estados em VHDL e uso de processos síncronos.  
- Depuração de sinais usando **waveform simulation**.  
- Estruturação de um projeto digital completo no Vivado.

### ⚠️ Dificuldades
- Ajuste correto do **clock** na simulação.  
- Interpretação das formas de onda.  
- Entendimento inicial da transição de estados com base nas entradas.

---

