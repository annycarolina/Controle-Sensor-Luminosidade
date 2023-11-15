# objetos-conectados
Controle de Luminária com Sensor de Luminosidade

Objetivo:
O presente projeto teve como propósito desenvolver um sistema de controle de luminária utilizando um sensor de luminosidade (LDR), um Arduino Uno, um LED e um módulo Wi-Fi ESP8266 ESP-12E Node-Mcu. O sistema visa automatizar o acionamento da luminária com base nas condições de luminosidade do ambiente, permitindo também o controle remoto através do protocolo MQTT (Message Queuing Telemetry Transport).

Componentes Utilizados:

Arduino Uno: Placa principal responsável pela execução do código e controle da interação entre os componentes.
Sensor LDR: Detecta a luminosidade do ambiente, variando sua resistência de acordo com a intensidade de luz incidente.
LED: Emite luz quando uma corrente elétrica passa por ele, sendo controlado pelo Arduino com base nas leituras do LDR.
Resistor de 220 ohms: Limita a corrente que passa pelo LED, evitando danos.
ESP8266 ESP-12E Node-Mcu: Módulo Wi-Fi para comunicação sem fio, possibilitando o controle remoto do sistema.

Código:

O código foi desenvolvido utilizando as bibliotecas ESP8266WiFi.h e PubSubClient.h, essenciais para a comunicação Wi-Fi e MQTT com o ESP8266. O código configura a conexão Wi-Fi, o servidor MQTT, os modos dos pinos e realiza a leitura do valor do LDR. Com base na luminosidade detectada, o LED é ligado ou desligado, e uma mensagem é publicada no tópico MQTT "led_control".

Fluxo do Código:

Verifica a conexão MQTT e reconecta-se, se necessário.
Lê o valor do LDR.
Decide se o LED deve ser ligado ou desligado com base na luminosidade.
Publica uma mensagem no tópico MQTT "led_control".
Aguarda 100 milissegundos antes de repetir o processo.
Tenta reconectar ao servidor MQTT a cada 5 segundos até que a conexão seja bem-sucedida.
Assina o tópico MQTT "led_control" após a conexão bem-sucedida.

Funcionamento e Limitações:

Infelizmente, não foi possível demonstrar a funcionalidade completa do projeto devido à dificuldade de conexão com o protocolo MQTT. No entanto, o projeto, em sua concepção ideal, permitiria que o LDR detectasse a luminosidade, o Arduino decidisse sobre o estado do LED, e o ESP8266 possibilitasse a conexão à internet para controle remoto através do MQTT.
