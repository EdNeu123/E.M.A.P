# 🚨 Estação de Monitoramento de Ambiente e Proximidade

Um sistema embarcado que utiliza um DHT11 (temperatura/umidade) e um HC-SR04 (distância) para monitorar o ambiente. O sistema fornece alertas visuais (LED) para alta temperatura e sonoros (Buzzer) para detecção de proximidade.

**Status do Projeto:** `Concluído`

## ⚙️ Funcionalidades (Features)

* **🌡️ Monitoramento de Temperatura e Umidade:** Lê ambos os dados do sensor DHT11.
* **📏 Medição de Distância:** Utiliza o HC-SR04 para medir a distância de objetos.
* **📈 Saída Serial:** Envia todos os dados lidos para o Serial Monitor (9600 baud).
* **🚨 Lógica de Alerta:**
  1. **Alerta de Temperatura (LED):** Aciona um LED se a temperatura exceder o `TEMPERATURA_ALERTA`.
  2. **Alerta de Proximidade (Buzzer):** Aciona um Buzzer se um objeto for detectado abaixo da `DISTANCIA_ALERTA`.

## 🛠️ Stack de Hardware e Software

### Hardware
* Arduino Uno R3
* Sensor DHT11 (Temp/Umidade)
* Sensor HC-SR04 (Distância)
* LED 5mm
* Buzzer Ativo 5V
* Resistor 220Ω (para o LED)

### Software
* [Arduino Framework (C++)](https://www.arduino.cc/reference/pt/)
* [Biblioteca DHT sensor library](https://github.com/adafruit/DHT-sensor-library) da Adafruit

## 🔌 Pinagem e Montagem (Hardware Setup)

Configuração de pinos utilizada neste projeto:

| Componente | Pino Arduino | Tipo | Observação | 
| :--- | :--- | :--- | :--- | 
| Sensor DHT11 (Data) | `D10` | Digital (Input) | Temp/Umidade | 
| HC-SR04 (Trig) | `D12` | Digital (Output) | Sensor de Distância | 
| HC-SR04 (Echo) | `D11` | Digital (Input) | Sensor de Distância | 
| LED (Atuador) | `D7` | Digital (Output) | Requer resistor de **220Ω** | 
| Buzzer (Atuador) | `D13` | Digital (Output) | *Pino do LED interno (L)* | 

**Nota sobre o Pino 13:** Este pino também controla o LED (L) embutido na placa do Arduino. Ao usar um buzzer nele, o LED da placa piscará junto com o som.

## 🚀 Como Executar (How to Run)

1. **Clone o Repositório.**
2. **Abra a IDE** (Arduino IDE ou VS Code/PlatformIO).
3. **Instale as Bibliotecas:**
   * Vá em `Tools > Manage Libraries...`
   * Procure e instale `DHT sensor library` pela Adafruit.
4. **Monte o Circuito:** Siga o esquema de pinagem.
5. **Upload:** Conecte o Arduino, selecione Placa/Porta e faça o upload.
6. **Monitore:** Abra o Serial Monitor (Baud Rate **9600**).

## 🔧 Configuração e "Magic Numbers"

Limiares de ativação definidos no topo do arquivo `.ino`:
