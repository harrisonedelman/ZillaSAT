# ZillaSAT

This repo is to document the design process, architecture, and development of the ZillaSAT.

# What is ZillaSAT

ZillaSAT is a small model of a satellite's onboard computer. It collects sensor data, tracks what phase of flight it's in, decides what state the spacecraft should be in, and reports that data to the ground station.

# Why I'm building this

I'm building this to learn the fundamentals of embedded systems, with the added challenge of aerospace-constraints: efficient low-memory, low-power microcontrollers, RTOS scheduling, and communication protocols. Beyond the hardware, I want hands-on experience with flight software framework (F') and testing practices that real spacecraft teams use.

# Architecture

ZillaSAT is made up of three parts:

Sensor node - an STM32 microcontroller running FreeRTOS. Reads IMU, magnetometer, and power montitor. Streaming all of the data over UART.

