# Aplica-o-IOT-
integrantes: Luigi RM563096, Arthur RM564958, Bruno RM562863, Vitor RM562208, Natalia RM563072
# ⚽ Projeto IoT - Detecção de Gols no Futebol Feminino

## 📌 Descrição
Este projeto implementa um sistema **IoT** para detectar automaticamente **gols em partidas de futebol feminino**.  
A detecção é feita através de **sensores simulados** (botões no Wokwi), conectados a um **ESP32**, que envia eventos de gol para um **broker MQTT**.  
Os dados podem ser visualizados em tempo real via **Node-RED Dashboard** ou armazenados para análises posteriores.  

---

## 🎯 Objetivo
- Detectar **eventos de gol** com base na passagem da bola pela linha do gol.  
- Transmitir esses eventos em tempo real usando **MQTT**.  
- Fornecer um **dashboard em tempo real** para análise de placar e estatísticas.  

---

## 🛠️ Arquitetura do Sistema


- **Sensores IR simulados** → Botões no Wokwi.  
- **ESP32 DevKit** → Coleta eventos e publica via MQTT.  
- **Broker MQTT** (HiveMQ público ou Mosquitto local).  
- **Node-RED** → Processa eventos e exibe placar em tempo real.  

---

## 🧩 Componentes
- ESP32 DevKit (simulado no [Wokwi](https://wokwi.com))  
- 2 × Push-buttons (substituindo sensores IR de gol)  
- Broker MQTT (HiveMQ público ou Mosquitto local)  
- Node-RED + Node-RED Dashboard  

---

## 💻 Como Executar

### 1. Simulação no Wokwi
1. Abra [https://wokwi.com](https://wokwi.com).  
2. Crie um novo projeto com ESP32.  
3. Substitua o código pelo `sketch.ino` fornecido.  
4. Substitua o `diagram.json` para montar o circuito com 2 botões.  
5. Inicie a simulação e pressione os botões para simular gols.  

---

### 2. Código do ESP32
- Detecta pressões rápidas dos dois botões (sensores).  
- Publica evento JSON via MQTT:  

```json
{
  "event": "goal",
  "ts_ms": 123456
}
