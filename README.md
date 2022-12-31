# A3T1 STM32F407VET6 I2C Basic Interfacing

**Assignment Description:** Read MPU-6050 accelerometer data via I2C and print the data in putty terminal via UART

**Group Name:** Smart Dolphins\
**Owners:** Veknes Benjaman; Saw Jun Chao

**Source Code:** [main.c](/A3T2_STM32F407VET6_BasicInterface/Core/Src/main.c)\
**Video Demonstration:** [https://youtu.be/fyPS4Pgsfv4](https://youtu.be/fyPS4Pgsfv4)

## Descriptions on Board and Microcontroller

**STM32 development board model:** STM32F4VE\
**Microcontroller:** STM32F407VET6\
**Core:** ARM Cortex-M4

## GPIO Pins Configuration, Components and Code Functions

[1] Pinout configuration in STM32CubeIDE

- PA9 configured as USART1_TX and Asynchronous mode
- PA10 configured as USART1_RX and Asynchronous mode
- PB8 configured as I2C and I2C1_SCL
- PB9 configured as I2C and I2C1_SDA

[2] Components

- YP-01 USB to TTL module for UART communication
- MPU-6050 6DOF Accelerometer and Gyroscope

<center><img src="/pictures/schematics.png"></center>

[3] Code function

HAL_Delay(Delay) : Creates delay (in ms)\
HAL_UART_Transmit : Transmit data to UART\
HAL_I2C_Mem_Read : Read an amount of data in blocking mode from a specific memory address\
HAL_I2C_Mem_Write : Write an amount of data in blocking mode from a specific memory address

[4] Putty terminal configuration

- Serial line number may change (can be checked through Windows Device Manager)
- The other configuration are set based on configuration set in STM32CubeIDE

<center><img src="/pictures/putty_configuration.png"></center>

[5] MPU6050 Configuration

- Write 0x0 to register 0x6B for Power Management 1 to wake up the sensor
- Write 0x7 to register 0x19 for Sample Rate Divider to set data rate of 1KHz
- Write 0x0 to register 0x1C for Accelerometer Configuration to configure +- 2g accelerometer sensitivity and 16384 LSB/g sensitivity scale factor

## Putty Terminal Output

<center><img src="/pictures/putty_terminal_output.png"></center>

## References

[1] Board Details and Schematics:\
[https://stm32-base.org/boards/STM32F407VET6-STM32-F4VE-V2.0.html](https://stm32-base.org/boards/STM32F407VET6-STM32-F4VE-V2.0.html)\
[2] STM32CubeIDE Tutorial:\
[https://www.st.com/resource/en/user_manual/um2609-stm32cubeide-user-guide-stmicroelectronics.pdf](https://www.st.com/resource/en/user_manual/um2609-stm32cubeide-user-guide-stmicroelectronics.pdf)\
[https://www.youtube.com/playlist?list=PLnMKNibPkDnFCosVVv98U5dCulE6T3Iy8](https://www.youtube.com/playlist?list=PLnMKNibPkDnFCosVVv98U5dCulE6T3Iy8)\
[3] Previous Assignment:\
[https://github.com/SawJunChao/stm32blinky](https://github.com/SawJunChao/stm32blinky)\
[https://github.com/SawJunChao/stm32morse](https://github.com/SawJunChao/stm32morse)\
[https://github.com/veknes/stm32knightrider](https://github.com/veknes/stm32knightrider)\
[https://github.com/veknes/stm32switchread](https://github.com/veknes/stm32switchread)\
[https://github.com/veknes/stm32helloworld](https://github.com/veknes/stm32helloworld)\
[4] UART STM32 Configuration:\
[https://wiki.st.com/stm32mcu/wiki/STM32StepByStep:Step3_Introduction_to_the_UART](https://wiki.st.com/stm32mcu/wiki/STM32StepByStep:Step3_Introduction_to_the_UART)\
[https://deepbluembedded.com/stm32-usart-uart-tutorial/](https://deepbluembedded.com/stm32-usart-uart-tutorial/)\
[https://controllerstech.com/uart-transmit-in-stm32/](https://controllerstech.com/uart-transmit-in-stm32/)\
[5] MPU6050 Configuration:\
[https://controllerstech.com/how-to-interface-mpu6050-gy-521-with-stm32/](https://controllerstech.com/how-to-interface-mpu6050-gy-521-with-stm32/)\
[6] MPU6050 Datasheet\
[https://invensense.tdk.com/wp-content/uploads/2015/02/MPU-6000-Datasheet1.pdf](https://invensense.tdk.com/wp-content/uploads/2015/02/MPU-6000-Datasheet1.pdf)\
[https://invensense.tdk.com/wp-content/uploads/2015/02/MPU-6000-Register-Map1.pdf](https://invensense.tdk.com/wp-content/uploads/2015/02/MPU-6000-Register-Map1.pdf)
