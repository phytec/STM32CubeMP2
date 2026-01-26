## <b>OpenAMP_TTY_echo Application Description</b>

-  It demonstrates How to use OpenAMP MW + Virtual UART to create an Inter-Processor Communication channel seen as TTY device in Linux OS.
-  This project deals with CPU2 (Cortex-M33) firmware and requires Linux OS running on CPU1 (Cortex-A35).

- Following command should be done in Linux console to run the example :

        stty -onlcr -echo -F /dev/ttyRPMSG0
        cat /dev/ttyRPMSG0 &
        stty -onlcr -echo -F /dev/ttyRPMSG1
        cat /dev/ttyRPMSG1 &
        echo "Hello Virtual UART0" >/dev/ttyRPMSG0
        echo "Hello Virtual UART1" >/dev/ttyRPMSG1

You should get "Hello Virtual UART0" and "Hello Virtual UART1" in Linux console

####  <b>Expected success behavior</b>
- Blink LED1 (green)

#### <b>Error behaviors</b>
- LED1 (green) does not blink

### <b>Keywords</b>

OpenAMP, RPMsg, TFM, IPCC, Inter-Processor Communication

### <b>Hardware and Software environment</b>

  - This example runs on STM32MP25xx devices
  - This example has been tested with PHYTEC phyFLEX-STM32MP257F FPSC Libra board.
    and can be easily tailored to any other supported device and development board.

  - Connect USB debug cable (on X14) to the PC USB port to display trace.

### <b>How to use it ?</b>

In order to make the program work, you must do the following :

 - Open your preferred toolchain
 - Rebuild all files and load your image into target memory
 - Run the application
 - Connect the board to the PC through USB debug (X14) and USB1 (X18) Type-C ports.
