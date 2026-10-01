# Laboratory Activity 3: GPIO and Button Control

## Overview
This activity is a walkthrough for Laboratory Activity 3 (GPIO and Button Control) using an ESP32. It shows how to read a tactile button press to flip two LEDs between opposite ON/OFF states. The setup relies on the ESP32's built-in INPUT_PULLUP resistor to keep inputs clean and uses simple if/else logic to manage the outputs.

## Project Features

Internal Pull-Up Mode: Configures Pin 23 with INPUT_PULLUP to keep the input signal steadily HIGH while the button is untouched.
Dual-State LED Toggle: Sets LED 1 to HIGH (ON) during the released state and LOW (OFF) when pressed, while LED 2 operates in complete opposition.
Explicit Conditional Logic: Uses structured if/else statements instead of ternary operators to make the control flow easier to follow.

## Observation Summary

| Button State | Input Pin Logic | LED 1 (Pin 18) | LED 2 (Pin 19) | Behavior Notes |
| :--- | :--- | :--- | :--- | :--- |
| **Released** | HIGH | **ON** | **OFF** | Internal pull-up holds GPIO 23 at 3.3V; LED 1 defaults to HIGH. |
| **Pressed** | LOW | **OFF** | **ON** | Button shorts GPIO 23 to GND (0V); LED outputs invert instantly. |
