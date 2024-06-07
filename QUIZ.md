### How does the DevBoard handle received serial messages? How does this differ from the naïve approach?

The DevBoard manages incoming serial messages using interrupt methods. When a serial message reaches the microcontroller, it triggers an interrupt. This interrupts the current task being executed by the microcontroller, allowing it to initiate a routine specifically designed to handle the incoming data. This method differs from a more simplistic approach where the microcontroller continuously checks for incoming bytes, a process that consumes more energy and CPU resources compared to using interrupts.






### What does `detached_callback` do? What would happen if it wasn't used?

It serves as a mechanism to prevent the user interface from becoming unresponsive in scenarios where certain code operations take an extended period to execute..


### What does `LockedSerial` do? Why is it _necessary_?

In situations where multiple threads attempt to utilize the same serial port concurrently, it can lead to unpredictable outcomes. LockedSerial ensures that these threads can effectively share the same resources simultaneously, mitigating potential conflicts and ensuring smooth operation.