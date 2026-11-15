# Embedded ECU Development – Sensor I/O and GPIO Programming

An academic embedded systems project developed as part of the Automotive Software Engineering (ASE) studies at **TU Chemnitz**. The project demonstrates analog sensor acquisition, GPIO pin configuration, LED-based value visualization, and timer-driven binary counter functionality using C.

## Project Overview

This project focuses on low-level embedded programming and hardware interaction on an ECU evaluation board.

The application reads analog values from a potentiometer and a light-dependent resistor (LDR), processes the sensor readings, and displays their value ranges using six onboard LEDs.

It also implements a binary counter controlled by push buttons and a periodic timer interrupt.

## Key Features

- **Potentiometer Reading:** Reads analog input values from the potentiometer.
- **Light Sensor Reading:** Acquires analog values from an LDR.
- **LED Visualization:** Maps sensor values into six ranges and displays them using six LEDs.
- **GPIO Configuration:** Configures digital input and output pins through the System Integration Unit (SIU).
- **Binary Counter:** Implements a 3-bit binary counter using LEDs.
- **Push Button Control:** Uses button inputs to control the counter direction.
- **Timer Interrupt:** Uses a Periodic Interrupt Timer (PIT) for counter updates.

## Hardware and Software

### Hardware

- ECU evaluation board used in the TU Chemnitz ASE tutorial
- Potentiometer
- Light-dependent resistor (LDR)
- Six onboard LEDs
- Digital switches
- Push buttons

### Software and Technologies

- C Programming
- Embedded C
- GPIO and SIU
- Analog-to-Digital Converter (ADC)
- Periodic Interrupt Timer (PIT)
- Hardware register-level programming
- Board-specific initialization and support libraries

## Project Tasks

### Task 1 – Potentiometer Reading

The application reads the potentiometer value through the ADC.

The input value is divided into six ranges. Each range activates a corresponding number of LEDs to provide a visual representation of the potentiometer reading.

### Task 2 – Light Sensor Reading

The application reads the analog value from the light sensor (LDR).

The sensor value is mapped to six ranges and displayed using the onboard LEDs.

### Task 3 – Binary Counter

A 3-bit binary counter is implemented using three LEDs.

- Push buttons control the counter direction.
- A periodic timer interrupt updates the counter.
- The three LEDs represent the binary counter states.

## Pin Configuration

The `siu.c` source file contains the SIU pin configuration.

| Function | SIU Pin |
|---|---:|
| Switch 1 | 52 |
| Switch 2 | 53 |
| Switch 3 | 54 |
| Switch 4 | 55 |
| Push Button 1 | 60 |
| Push Button 2 | 62 |
| LED P | 56 |
| LED RX | 57 |
| LED TX | 58 |
| LED U1 | 59 |
| LED U2 | 43 |
| LED U3 | 6 |
| Potentiometer analog pin | 66 |
| LDR analog pin | 32 |

The application reads the potentiometer through `ADC0.CDR[5]` and the LDR through `ADC1.CDR[3]`.

## Project Structure

```text
ECU-Embedded-Systems-Sensor-IO/
│
├── .github/
│   └── workflows/
│
├── main.c
├── siu.c
│
├── Unit1_question.pdf
├── pin_muxing.pdf
│
└── README.md
```

## Documentation

The repository includes the following academic resources:

- **Unit1_question.pdf:** Original tutorial task description.
- **pin_muxing.pdf:** Pin multiplexing and configuration reference.

## Development Environment

The project uses board-specific hardware definitions, initialization functions, and support libraries.

The source code includes platform-specific headers such as:

- `init.h`
- `xpc56el.h`
- `siu.h`

A compatible TU Chemnitz ASE tutorial development environment, board support package, and toolchain are required to build and flash the application.

Exact build and flashing commands depend on the provided development environment.

## Learning Outcomes

Through this project, the following embedded systems concepts were explored:

- Working with hardware registers in C
- Configuring GPIO input and output pins
- Reading analog sensor values using ADC
- Mapping sensor values to LED outputs
- Implementing timer-based functionality
- Handling push button inputs
- Understanding basic ECU peripheral interaction

## Project Context

**University:** TU Chemnitz  
**Study Programme:** M.Sc. Automotive Software Engineering  
**Project Type:** Academic Embedded Systems Tutorial  
**Programming Language:** C

## Disclaimer

This project was developed for academic learning and demonstration purposes. It is not intended for direct use in production automotive systems or safety-critical applications.

---

**Author:** Mohammad Obydur Rahman  
**GitHub:** [github.com/obydur](https://github.com/obydur)


   

   
