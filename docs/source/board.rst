Information about the Mela-PLC
========================================

.. image:: /img/MELA-PLC_Assembly.jpg

``Mela-PLC`` is an open source controller based on
``microPython`` for industrial use and projects IoT.

``Mela-PLC`` based on a microcontroller ESP32-S3 N32R8 Flash 16 MB
PSRAM 8 MB 240 MHz.

``Mela-PLC`` for controlling external devices has isolated inputs-outputs,
data exchange ports RS-485, RS-232, SPI, I2C, and also a built-in module WiFi.

For visual control and manual adjustment ``Mela-PLC`` has the ability
to connect HMI according to protocols ``modbus RTU`` and ``modbus TCP``.

Using the open source ``Python platform`` to control ``Mela-PLC``
allows you to rely on a large number of application libraries in your developments and
makes the process of writing and debugging programs simple and visual.

The numbering of the contacts of the ``Mela-PLC`` does not correspond
to the numbering of the ESP32 controller. To establish the necessary
contact numbers, a table of pins is provided.

Technical specifications
------------------------

The datasheets and other reference material for ESP32-S3 chip are available
from the vendor site: https://www.espressif.com/en/products/socs/esp32-s3.

They are the primary reference for the chip technical specifications, capabilities,
operating modes, internal functioning, etc.

For your convenience, below are some technical characteristics of ``Mela-PLC``:

**Mela-PLC F1**

- Processor: Espressif ESP32-S3N16R8:
    - Architecture: Xtensa Dual-Core 32-bit LX7
    - RISC-V Ultra Low Power Co-processor
    - CPU frequency: up to 240MHz
    - Internal FlashROM: 16MB
    - External FlashROM: Octal SPI PSRAM 8MB
    - WiFi: 2.4GHz Wifi - 802.11b/g/n, 3D High Gain Antenna
- RTC: DS1307 with a CR2032 coin cell battery
- ADC: 16-bit delta-sigma ADC ADS1115 up to 4 differentials channels 860SPS [0-10V / 0-20mA]
- Digital Input: 8 Digital Isolated Input [0-24V]
- Didital Output: 10; 6 PWM - Digital Isolated Output OC [0-24V 2A]; 4 Relay [250V 5A]
- GPIO: 3 Digital Input-Output TTL [5V]
- USB: USB CH340 + USB OTG
- UART: 3 RX/TX UART
- I2C: I2C Isolated input
- RS-232: UART1
- RS-485: UART2
- Board Indicator: Low power RGB LED PL9823 compatible
- Reset: ON/OFF button, Outer Reset Connector
- Boot: ON/OFF button
- Power: 10-24V 4W Power Pin / 5V 800mA USB

The board can be powered from a USB connectors with a voltage of 5 volts.

For more information see the Mela-PLC datasheet:
https://github.com/gmecc/mela/blob/main/images/board-env.jpg

MicroPython is implemented on top of the ESP-IDF, Espressif’s development framework for the ESP32.
This is a FreeRTOS based system. See the ESP-IDF Programming Guide for details.

PIN table
----------

.. csv-table::
    :header: "Pin", "GPIO", "BOARD", "Type", "Function"
    :widths: 10, 15, 15, 10, 50

    "1", "GND"
    "2", "3V3"
    "3", "EN", "RESET", "T", "Outer RESET"
    "4", "IO4", "SDA0", "IsIO", "I2C0 SDA0"
    "5", "IO5", "SDL0", "IsIO", "I2C0 SDL0"
    "6", "IO6", "LED", "O", "LED RGB"
    "7", "IO7", "RS-485 Tx", "IsIO", "UART2 RS-485 Tx"
    "8", "IO15", "RS-485 Rx", "IsIO", "UART2 RS-485 Rx"
    "9", "IO16", "RS-485 RTC", "IsIO", "UART2 RS-485 RTC"
    "10", "IO17", "RS-232 Tx", "IsIO", "UART1 RS-232 Tx"
    "11", "IO18", "RS-232 Rx", "IsIO", "UART1 RS-232 Rx"
    "12", "IO8", "?"
    "13", "IO19", "USB", "IO", "USB Serial JTAG"
    "14", "IO20", "USB", "IO", "USB Serial JTAG"
    "15", "IO3", "DI0", "IsI", "Digital Input [0-24V]"
    "16", "IO46", "DI1", "IsI", "Digital Input [0-24V]"
    "17", "IO9", "DI2", "IsI", "Digital Input [0-24V]"
    "18", "IO10", "DI3", "IsI", "Digital Input [0-24V]"
    "19", "IO11", "DI4", "IsI", "Digital Input [0-24V]"
    "20", "IO12", "DI5", "IsI", "Digital Input [0-24V]"
    "21", "IO13", "COM0", "R", "Reley [250V 5A]"
    " ", " ", "NO0", "R", "Reley [250V 5A]"
    " ", " ", "NC0", "R", "Reley [250V 5A]"
    "22", "IO14", "COM1", "R", "Reley [250V 5A]"
    " ", " ", "NO1", "R", "Reley [250V 5A]"
    " ", " ", "NC1", "R", "Reley [250V 5A]"
    "23", "IO21", "COM2", "R", "Reley [250V 5A]"
    " ", " ", "NO2", "R", "Reley [250V 5A]"
    " ", " ", "NC2", "R", "Reley [250V 5A]"
    "24", "IO47", "COM3", "R", "Reley [250V 5A]"
    " ", " ", "NO3", "R", "Reley [250V 5A]"
    " ", " ", "NC3", "R", "Reley [250V 5A]"
    "25", "IO48", "PWM10", "OC", "PWM [24V 2A]"
    "26", "IO48", "PWM10", "OC", "PWM [24V 2A]"
    "27", "IO0", "BOOT", "T", "BOOT"
    "28", "IO35", "PWM12", "OC", "PWM [24V 2A]"
    "29", "IO36", "PWM13", "OC", "PWM [24V 2A]"
    "30", "IO37", "PWM14", "OC", "PWM [24V 2A]"
    "31", "IO38", "PWM15", "OC", "PWM [24V 2A]"
    "32", "IO39", "GPIO39", "IO", "Digital Input / JTAG / SPI"
    "33", "IO40", "GPIO40", "IO", "Digital Input / JTAG / SPI"
    "34", "IO41", "GPIO41", "IO", "Digital Input / JTAG / SPI"
    "35", "IO42", "GPIO42", "IO", "Digital Input / JTAG / SPI"
    "36", "RXD0", "RX0", "IsIO", "UART0 RX"
    "37", "TXD0", "TX0", "IsIO", "UART0 TX"
    "38", "IO2", "SDA1", "IsIO", "I2C1 SDA1"
    "39", "IO1", "SDL1", "IsIO", "I2C1 SDL1"
    "40", "GND", "GND", " ", "GND"
    " ", " ", "AI0+", "AI", "Analog Input 16-bit ADC [0-10V / 0-20mA]"
    " ", " ", "AI0-", "AI", "Analog Input 16-bit ADC [0-10V / 0-20mA]"
    " ", " ", "AI1+", "AI", "Analog Input 16-bit ADC [0-10V / 0-20mA]"
    " ", " ", "AI1-", "AI", "Analog Input 16-bit ADC [0-10V / 0-20mA]"
    " ", " ", "AI2+", "AI", "Analog Input 16-bit ADC [0-10V / 0-20mA]"
    " ", " ", "AI2-", "AI", "Analog Input 16-bit ADC [0-10V / 0-20mA]"
    " ", " ", "AI3+", "AI", "Analog Input 16-bit ADC [0-10V / 0-20mA]"
    " ", " ", "AI3-", "AI", "Analog Input 16-bit ADC [0-10V / 0-20mA]"
    " ", " ", "USB", "P", "VCC [5V 500mA]"
    " ", " ", "VCC", "P", "VCC [5-24V 200mW]"


* *I0*: Input/Output TTL;
* *IsI*: Isolated Input [0-24V] V_True_min = 3V;
* *IsIO*: Isolated Input/Output [0-24V];
* *OC*: Open Collector Output [0-24V 2 A];
* *R*: Relay [250V 5A];
* *T*: High Impedance Isolated Input (PULL APP);
* *P*: Power supply;
* *AI*: Analog Input


Jumper description
-------------------

Jumper location
^^^^^^^^^^^^^^^

See figure below


Analog input jumpers
^^^^^^^^^^^^^^^^^^^^^

The device has four analog inputs located in the upper left corner. Analog inputs are marked as "AIx" (x=0..3).
Each analog input can be configured using four jumpers (J1..J4).


1. Resistance measurement input (voltage measurement with current source).
2. 0..24 mA input.
3. 0..10V input.


Two current source values are available: 0.5 mA and 10 uA.
There are three jumpers on each channel to select the operating mode for the analog inputs (see table below):

+---+-----+-----+----------------------+
| J1|J2   |J3   |Operation mode        |
+===+=====+=====+======================+
| \+|  \- | \-  |Resistance measurement|
+---+-----+-----+----------------------+
| \-|  \+ | \-  |0..24 mA              |
+---+-----+-----+----------------------+
| \-| \-  | \+  |0..10 V               |
+---+-----+-----+----------------------+


The 4th jumper definites current value of current source. If J1 is not installed J4 doesn't influate to analog input operation. R [*]

+-----+--------------+------------+
| J4  | Current value| Max. R [*]_|
+=====+==============+============+
|Set  |0.5 mA        |4 kOhm      |
+-----+--------------+------------+
|Unset|10 uA         |200 kOhm    |
+-----+--------------+------------+

.. [*] FSR=2048mV (see ADS1115 datasheet)


PWM output jumpers
^^^^^^^^^^^^^^^^^^^^^

Jumper defines output state for PWM outputs **when MCU is stopped**. On the PCBA the jumpers are marked "PWM INPUT PULL-UP JUMPER". If the jumper is set, the corresponding output will have a logic "1" state. If the jumper is unset, the corresponding output will have a logic "0" state.
See schematic for details.

+-------------+-----------------------+
| PWMx Jumper | PWMx output state [*]_|
+=============+=======================+
| Set         | 1                     |
+-------------+-----------------------+
| Unset       | 0                     |
+-------------+-----------------------+

.. [*] When the MCU is stopped or the corresponding pin is configured as an input without pull-up or pull-down.


Relay output jumpers
^^^^^^^^^^^^^^^^^^^^^^

Jumper defines relay state (open/close) **when MCU is stopped**. On the PCBA the jumpers are marked "RELAY INPUT PULL-UP JMP". If the jumper is set, the corresponding relay will be ON. If the jumper is unset, the corresponding relay will be OFF.
See schematic for details.

+-------------+-----------------+
| PWMx Jumper | Relay state [*]_|
+=============+=================+
| Set         | ON              |
+-------------+-----------------+
| Unset       | OFF             |
+-------------+-----------------+

.. [*] When the MCU is stopped or the corresponding pin is configured as an input without pull-up or pull-down.

DI jumpers
^^^^^^^^^^^

DI0..DI3 can operate in two modes:

1. 0..24V with Vil=1V and Vih=4.5V.
2. 0..5V with Vil=0.5V and Vih=2.25V.

If the DIx jumper is set, the second mode (0..5V) is selected.

+-----------+------+-----+-----+
| DIx Jumper|Mode  |Vil  |Vih  |
+===========+======+=====+=====+
| Unset     |0..5V |0.5V |2.25V|
+-----------+------+-----+-----+
| Set       |0..24V|1V   |4.5V |
+-----------+------+-----+-----+

|

DIO Jumpers
^^^^^^^^^^^^

The device has three open-drain isolated DIOs. The isolated part can be powered from the external power source, which must be connected to the "V+" and "GND" contacts, or from the internal power source. The power source (external/internal) and the value of the internal source voltage are selected by jumpers "3V3" and "5V" as described in the table below:

+-------------+-----------+------------+----------------------+
| Jumper "3V3"|Jumper "5V"|Power source|Power source Voltage  |
+=============+===========+============+======================+
|Unset        |Unset      |External    |Defines by external   |
|             |           |            |power source (3..5.5V)|
+-------------+-----------+------------+----------------------+
|Set          |Unset      |Internal    |3.3V                  |
+-------------+-----------+------------+----------------------+
|Unset        |Set        |Internal    |5V                    |
+-------------+-----------+------------+----------------------+
|Set          |Set        |            |**FORBIDDEN**         |
+-------------+-----------+------------+----------------------+

All the DIOs have a common power source.

It is possible to pull up the DIOs with a 3 kOhm resistor. If pull-up is required, the corresponding jumper marked **"3K PULL UP"** must be set (jumper connects DIOx to "V+" via 3 kOhm resistor).

I2C Jumpers
^^^^^^^^^^^

The device has isolated I2C intefrace. The isolated part can be powered from the external power source, which must be connected to the "V+" and "GND" contacts, or from the internal power source. The power source (external/internal) and the value of the internal source voltage are selected by jumpers "3V3" and "5V" as described in the table below:

+-------------+-----------+------------+----------------------+
| Jumper "3V3"|Jumper "5V"|Power source|Power source Voltage  |
+=============+===========+============+======================+
|Unset        |Unset      |External    |Defines by external   |
|             |           |            |power source (3..5.5V)|
+-------------+-----------+------------+----------------------+
|Set          |Unset      |Internal    |3.3V                  |
+-------------+-----------+------------+----------------------+
|Unset        |Set        |Internal    |5V                    |
+-------------+-----------+------------+----------------------+
|Set          |Set        |            |**FORBIDDEN**         |
+-------------+-----------+------------+----------------------+

It is possible to pull up the lines with a 3 kOhm resistor. If pull-up is required, the corresponding jumper marked **"3K PULL UP"** must be set (jumper connects DIOx to "V+" via 3 kOhm resistor).

RS-485 "120 Ohm" jumper
^^^^^^^^^^^^^^^^^^^^^^^^

This jumper connects a 120 ohm resistor between the A and B lines.


UART0 Pin Header
^^^^^^^^^^^^^^^^^

By default, UART0 of the MCU is connected to the USB-C header via CH340 and the jumpers marked "RX" and "TX" are set. If a variation of UART0 connection is required, the jumpers must be unset and pins '3V3', 'GND', 'RX' and 'TX' can be used for connection to UART0. The 'RX' and 'TX' pins are connected directly to the MCU pins. See datasheet for details.

I2C and additional non-isolated 3.3V CMOS level IOs header
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The device has an internal non-isolated I2C interface which can be used for connection via the I2C pin header marked "GND", "3V3", "SCL", "SDA". If required, an additional I2C device can be connected to the MCU via this header (e.g. LCD display).
Pins "P4", "P5", "P6", "P7" are connected to the IO expander pins and can be used as non-isolated IOs (e.g. for keyboard connection).
The pinout of this header is the same as standard LCD display boards with keyboard for Arduino.

DRDY-DI6 jumper
^^^^^^^^^^^^^^^^

This jumper connects the DRDY pin of the ADS1115 (ADC) to the pin of the MCU corresponding to DI6. It is used when a DRDY signal from the ADC is required . If this jumper is set, the "DI6" contact of the device's input connector must be unconnected.

INT-DI7 jumper
^^^^^^^^^^^^^^^

This jumper connects the INT pin of the IO expander to the pin of the MCU corresponding to DI7. It is used when an INT signal from the IO expander is required . If this jumper is set, the "DI7" contact of the device's input connector must be unconnected.


