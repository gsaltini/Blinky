# Week 3 Assignment
## Description
This programs implements two blinking LEDs using the GPIOB pins 6 (blue LED) and 7 (green LED). Each GPIO output pin
is manipulated using the HAL_GPIO driver library, specifically the HAL_GPIO_TogglePin function. After a delay of 1 
second, implemented using the HAL_Delay function, the programs toggles on and off the green and blue LEDs. This
continues until the board is powered off. Additionally, the User push button, connect to the GPIOA pin 0, was
configured as an external interrupt, using the STM32CubeX interface. Pressing the button triggers an interrupt,
which toggles the green and blue LEDs.

## Further Investigation
### What are the hardware registers that cause the LED to turn on and off? (From the processor manual, don't worry about initialization)

