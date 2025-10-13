Part 2 Questions
1. How do external interrupts work and how does the ISR handle button presses?
The NVIC listens into EXTIs and when it senses that the button is pressed (IRQ signals), for instance,
the NVIC notifies the CPU. The NVIC takes care of prioritization when the peripheral that
generates the interrupt request sets the pending flag since the NVIC has to track these
external interrupts. Once prioritization has be determined, the interrupt of highest priority
(if it is not the only one), the CPU will pause the current program and swap into running the
ISR.   

2. When does the ISR get executed?
It gets executed when a hardware or software component gerneates an interrupt signal.

3. What happens if you dont clear the EXTI pending flag in the ISR?
The interrupt will reassert itself as pending even after the ISR resolves so it will get 
triggered again and potentially infinitely if the flag is never cleared.


