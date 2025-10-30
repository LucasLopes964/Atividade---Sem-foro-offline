###  Resumo

A imagem abaixo mostra que durante a montagem do circuito, usei o Arduino Uno conectado a três LEDs (vermelho, amarelo e verde), cada um com seu resistor, seguindo a proposta. Durante o processo, precisei trocar alguns componentes que estavam com defeito, como resistores e jumpers, para garantir o bom funcionamento do circuito. Após os ajustes, o sistema funcionou corretamente, com os LEDs acendendo conforme o código.

![Montagem física](assets/IMAGEM1.jpeg)

---

###  Componentes Utilizados no Circuito

| Componente        | Quantidade | Especificações / Valores | Função no Circuito |
|-------------------|-------------|---------------------------|--------------------|
| **Arduino UNO**   | 1           | Microcontrolador ATmega328P, 5V | Controlar o acionamento dos LEDs. |
| **LED Vermelho**  | 1           | Tensão: ~2V / Corrente: 20mA | Indicar o estado “pare” (sinal vermelho). |
| **LED Amarelo**   | 1           | Tensão: ~2V / Corrente: 20mA | Indicar o estado de “atenção” (sinal amarelo). |
| **LED Verde**     | 1           | Tensão: ~2V / Corrente: 20mA | Indicar o estado “siga” (sinal verde). |
| **Resistor**      | 3           | 220 Ω (faixas: vermelho, vermelho, marrom, ouro) | Limitar a corrente que passa pelos LEDs, evitando que queimem. |
| **Jumpers (Fios de Conexão)** | 7 | Macho-macho | Fazer as ligações entre o Arduino e a protoboard. |
| **Protoboard**    | 1           | 830 pontos (aprox.) | Facilitar a montagem do circuito sem solda. |
| **Cabo USB**      | 1           | Tipo A-B | Alimentar e programar o Arduino pelo computador. |

---

### Tabela de Avaliação entre Pares
#### Avaliador: Guilherme Schmidt
|Critério|  Contempla (Pontos)| Contempla Parcialmente (Pontos) |Não Contempla (Pontos) |Observações do Avaliador|
|-|-|-|-|-|
|Montagem física com cores corretas, boa disposição dos fios e uso adequado de resistores   |3  |   || |
|Temporização adequada conforme tempos medidos com auxílio de algum instrumento externo |3  |   | | |
|Código implementa corretamente as fases do semáforo e estrutura do código (variáveis representativas e comentários) |  3|   |   | |
|Ir além: Implementou um componente de extra, fez com millis() ao invés do delay() e/ou usou ponteiros no código |   |  0,5 |   | |
| | | | |Pontuação Total: 9,5|


### Tabela de Avaliação entre Pares
#### Avaliador: João de caprio
|Critério|  Contempla (Pontos)| Contempla Parcialmente (Pontos) |Não Contempla (Pontos) |Observações do Avaliador|
|-|-|-|-|-|
|Montagem física com cores corretas, boa disposição dos fios e uso adequado de resistores   |3  |   || |
|Temporização adequada conforme tempos medidos com auxílio de algum instrumento externo |3  |   | | |
|Código implementa corretamente as fases do semáforo e estrutura do código (variáveis representativas e comentários) |  3|   |   | |
|Ir além: Implementou um componente de extra, fez com millis() ao invés do delay() e/ou usou ponteiros no código |   |  0,5 |   | |
| | | | |Pontuação Total: 9,5|

###  Código 

```cpp
// Definição dos pinos dos LEDs
int ledVermelho = 8;
int ledAmarelo  = 9;
int ledVerde    = 10;

void setup() {
  // Configura os pinos como saída
  pinMode(ledVermelho, OUTPUT);
  pinMode(ledAmarelo, OUTPUT);
  pinMode(ledVerde, OUTPUT);
}

void loop() {
  // Fase Vermelha - 6 segundos
  digitalWrite(ledVermelho, HIGH);
  digitalWrite(ledAmarelo, LOW);
  digitalWrite(ledVerde, LOW);
  delay(6000);

  // Fase Verde - 4 segundos
  digitalWrite(ledVermelho, LOW);
  digitalWrite(ledAmarelo, LOW);
  digitalWrite(ledVerde, HIGH);
  delay(4000);

  // Fase Amarela - 2 segundos
  digitalWrite(ledVermelho, LOW);
  digitalWrite(ledAmarelo, HIGH);
  digitalWrite(ledVerde, LOW);
  delay(2000);
}

