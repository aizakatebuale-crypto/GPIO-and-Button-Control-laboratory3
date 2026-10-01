# Laboratory Activity 3: GPIO and Button Control

## Overview
This activity is a walkthrough for Laboratory Activity 3 (GPIO and Button Control) using an ESP32. It shows how to read a tactile button press to flip two LEDs between opposite ON/OFF states. The setup relies on the ESP32's built-in INPUT_PULLUP resistor to keep inputs clean and uses simple if/else logic to manage the outputs.

## Project Features

• Internal Pull-Up Mode: Configures Pin 23 with INPUT_PULLUP to keep the input signal steadily HIGH while the button is untouched.

• Dual-State LED Toggle: Sets LED 1 to HIGH (ON) during the released state and LOW (OFF) when pressed, while LED 2 operates in complete opposition.

• Explicit Conditional Logic: Uses structured if/else statements instead of ternary operators to make the control flow easier to follow.

## Observation Table

| Button State | Input Pin Logic | LED 1 (Pin 18) | LED 2 (Pin 19) | 
| :--- | :--- | :--- | :--- | :--- |
| **Released** | HIGH | **ON** | **OFF** | 
| **Pressed** | LOW | **OFF** | **ON** | 

## Source Code

#include <Arduino.h>

const uint8_t BUTTON_PIN = 23;
const uint8_t LED1_PIN = 18;
const uint8_t LED2_PIN = 19; 

void setup() {

  pinMode(BUTTON_PIN, INPUT_PULLUP);
  
  pinMode(LED1_PIN, OUTPUT);
  pinMode(LED2_PIN, OUTPUT);
  
  digitalWrite(LED1_PIN, HIGH);
  digitalWrite(LED2_PIN, LOW);
}

void loop() {
  int buttonState = digitalRead(BUTTON_PIN);
  
  
  if (buttonState == LOW) {
    
    digitalWrite(LED1_PIN, LOW);   
    digitalWrite(LED2_PIN, HIGH);  
  } else {
    
    digitalWrite(LED1_PIN, HIGH);  
    digitalWrite(LED2_PIN, LOW);  
  }
}

## Circuit Documentation

## Photo

<img width="4080" height="3060" alt="image" src="https://github.com/user-attachments/assets/adec5503-b18b-4f2c-95c7-e0d43df43a35" />


## Videos


https://github.com/user-attachments/assets/d050d507-54c7-4415-8f62-029c579925fd


https://github.com/user-attachments/assets/67bb7485-112e-452c-b9e6-f8b70df05fbd

## Conclusion

This activity shows how an ESP32 can read a push button input to control two LEDs in opposite states. By enabling the built-in INPUT_PULLUP resistor, the button provides a steady, reliable signal without random flickering. Using clean if/else logic makes it easy to switch the LEDs back and forth whenever the button is pressed or released. Overall, the circuit works as expected and successfully demonstrates basic digital I/O control.


