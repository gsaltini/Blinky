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
There are multiple registers that can be used to modify the state of the GPIO pin connected to the LED. The GPIO BSSR
(bit set/reset register) allows the program to perform an atomic write to a specific GPIO pin. Otherwise the GPIO 
ODR (output data register) allows the program to directly modify the value of the corresponding GPIO pin. 
### What are the registers that you read in order to find out the state of the button?
The GPIO IDR (input data register) is used to read the state of a GPIO pin or port. This would allow us to determine
the state of the button becasue the button is connected to an input GPIO pin.
### Can you read the register directly and see the button change in a debugger or by printing out the valyes of the memory at the register's address?
Yes, it is possible to view the value of the IDR for the GPIOA port change at runtime by using a debugger. When
debugging the program, you will need to have the SFRs window open on the right side of the SMT32CubeIDE. In this
window you are able to look at all the various hardware registers on the board. By opening the GPIOA port registers
it is possible to see that the IDR0 registers will change from 0 to 1 when the button is pressed.

