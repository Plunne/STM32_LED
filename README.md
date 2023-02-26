# STM32 LED METHODS

Little project with different methods to set digital outputs.

This projet blink 3 LED with 3 different methods

1. Hardware Abstraction
2. Low Level ODR Register Masking
3. Low Level Atomic BSRR Register

> *Project made with STM32CubeIDE*

# HARDWARE ABSTRACTION LIBRARY

```c
HAL_GPIO_WritePin(GPIOB, LD1_Pin, 1); // Set LED1 on
HAL_GPIO_WritePin(GPIOB, LD1_Pin, 0); // Clear LED1 off
```

# LOW LEVEL MASKING

```c
GPIOB->ODR |= LD2_Pin;  // Set LED2 on
GPIOB->ODR &= ~LD2_Pin;	// Clear LED2 off
```

# LOW LEVEL ATOMIC

```c
GPIOB->BSRR = LD3_Pin;          // Set LED3 on
GPIOB->BSRR = LD3_Pin << 16;    // Clear LED3 off
```
