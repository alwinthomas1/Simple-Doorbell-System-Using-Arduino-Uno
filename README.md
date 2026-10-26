# Simple Doorbell System Using Arduino Uno

This project uses an Arduino Uno, a push button, and a buzzer to create a simple doorbell. The buzzer sounds while the button is pressed and stops when the button is released.

## Project Overview

The circuit was built and tested using the Wokwi Arduino simulator. It uses a push button as the input and a buzzer as the output.

## Objective

To make a buzzer turn on when a push button is pressed and turn off when it is released.

## Components Used

| Component | Quantity |
|---|---:|
| Arduino Uno | 1 |
| Push Button | 1 |
| Buzzer | 1 |
| Breadboard | 1 |
| Jumper Wires | As required |

**Software:** Wokwi

## Project Links

- **Documentation:** [Google Docs Report](https://docs.google.com/document/d/1JxE9SHWzdLFCjzUWvFxljEJj8vXOV9hOaLOio5nnHwE/edit?usp=sharing)
- **Circuit Simulation:** [Open Project in Wokwi](https://wokwi.com/projects/478953537421792257)

## Circuit Connections

| Component | Arduino Pin |
|---|---|
| Push button terminal 1 | D2 |
| Push button terminal 2 | GND |
| Buzzer positive (+) | D8 |
| Buzzer negative (-) | GND |

The button uses the Arduino's internal pull-up resistor, enabled through `INPUT_PULLUP`. Therefore, an external resistor is not required for the button.

## Arduino Code

```cpp
const int buttonPin = 2;
const int buzzerPin = 8;

void setup() {
  pinMode(buttonPin, INPUT_PULLUP);
  pinMode(buzzerPin, OUTPUT);
}

void loop() {
  if (digitalRead(buttonPin) == LOW) {
    tone(buzzerPin, 1000);
  } else {
    noTone(buzzerPin);
  }
}
```

## Working

1. When the button is released, pin D2 reads HIGH and the buzzer remains off.
2. When the button is pressed, pin D2 reads LOW and the buzzer produces a 1000 Hz tone.
3. When the button is released, `noTone()` stops the buzzer.

The program continuously checks the button state without using `delay()`.

## How to Run

1. Open the Wokwi project using the link above.
2. Start the simulation.
3. Press and hold the button to activate the buzzer.
4. Release the button and check that the buzzer stops.
5. Repeat to verify that it works as expected.

## Expected Output

| Button State | Buzzer State |
|---|---|
| Released | OFF |
| Pressed | ON |
| Released again | OFF |

## Result

The circuit is designed to operate as a simple doorbell. The buzzer sounds when the button is pressed and stops when the button is released.

---

**Project:** Simple Doorbell System  
**Microcontroller:** Arduino Uno  
**Simulation Platform:** Wokwi
