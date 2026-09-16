This firmware is created for general RP2040 board, especially black board with RGB LED.
I have tested the function by both Python serial port interface and LabVIEW. 
This firmware is intended to be used to teach students how to control MCU via SCPI command.
I have design this SCPI instrument to have 11 digital inputs, 8 digital outputs, 4 analog inputs, 1 PWM output, chip temperature and RGB LED.
The digital input DI10 (GPIO24) connected to button on the board while 1 PWM output connected to built-in LED at digital output DO9 (GPIO25).
The RGB LED connected to GPIO23. The support commands are as followed:


OUT a b = write output a [0-8] with logic b [0|1].

OUT? a = read status of output a.

IN a = read status of input a.

OUTB a = write outputs in a group of 8-bit (Byte).

INB a = read status inputs in a group of 8-bit (Byte) [0|1] where 0 has the first 8-bit inputs and 1 has the last 3-bit inputs

ADC a = read ADC channel a.

DAC [0|1] = Turn PWM-DAC [off|on] to update PWM value.

PWM a = set PWM value a which should be 0-1023.

[PAT:]RGB [0|1|2|3|4] = experimentally turn [off|on|red|green|blue] the RGB LED.

[PAT:]RGBR [1] =experimentally set red value and update [1].

[PAT:]RGBG [1] =experimentally set green value and update [1].

[PAT:]RGBB [1] =experimentally set blue value and update [1].

TEMP = read RP2040 built-in sensor temperature (chip temperature).

*IDN? = ID of the instrument.
