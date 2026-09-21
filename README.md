                        Sensor de Monitoramento de Temperatura com Alerta Visual e Sonoro

Este projeto consiste em um sistema de monitoramento automatizado que lê a temperatura em tempo real e aciona alertas visuais e sonoros caso os valores ultrapassem um limite crítico de segurança.

## 🚀 Funcionamento do Sistema

O sistema monitora constantemente a temperatura ambiente ou de um maquinário específico. O comportamento é dividido em dois estados:

* **Estado Seguro (Abaixo de 987°C):** O LED verde permanece **aceso**, o LED vermelho fica **apagado** e o buzzer (alarme sonoro) permanece **desativado**.
* **Estado de Alerta (Acima de 987°C):** O LED verde se **apaga**, o LED vermelho **acende** e o buzzer emite um **sinal sonoro contínuo** até que a temperatura volte à faixa segura.

---

## 🛠️ Componentes Utilizados

* **1x** Microcontrolador (Ex: Arduino Uno)
* **1x** Sensor de Temperatura
* **1x** LED Vermelho (Alerta)
* **1x** LED Verde (Normalidade)
* **2x** Resistores de 220Ω (para os LEDs)
* **1x** Buzzer Ativo 5V (Alarme sonoro)
* **1x** Protoboard e Jumpers para conexão

---

## 📌 Pinagem Sugerida (Exemplo Arduino)

| Componente | Pino do Arduino | Descrição |
| :--- | :--- | :--- |
| **LED Verde** | D2 | Indicador de temperatura normal |
| **LED Vermelho** | D3 | Indicador de temperatura crítica |
| **Buzzer** | D4 | Alarme sonoro de segurança |

---

## 💻 Lógica do Código (Pseudo-código)

int buzzer = 7;
int ntc = A0;
int led = 13;

void setup() {
pinMode(buzzer,OUTPUT);
pinMode(ntc,INPUT);
pinMode(led,INPUT);
Serial.begin(9600);
 }
void loop() {
  int temperature = analogRead(ntc);
  int limite = 983;
  Serial.println(temperature);
  

  if(temperature>limite){
    digitalWrite(buzzer, HIGH);
    digitalWrite(led, LOW);
    delay(1000);
  }else{
    digitalWrite(led,HIGH);
    digitalWrite(buzzer, LOW);
    delay(1000);
  }
}

---

## 🔧 Como Executar o Projeto

1. Monte o circuito seguindo o esquema de pinagem.
2. Certifique-se de usar um sensor adequado para a faixa de 987°C, como um **NTC**.
3. Instale as bibliotecas necessárias para o seu sensor na sua IDE de preferência.
4. Carregue o código para o microcontrolador.
5. Abra o Monitor Serial para acompanhar as leituras em tempo real.
