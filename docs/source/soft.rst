MELA
====

Application library ``mela``
------------------------------

The ``mela`` application library is designed to adapt known
``micropython`` classes to the ``Mela-PLC`` configuration. When creating real projects,
it is recommended to use the ``mela`` application
library to avoid possible errors. However, the typical ``micropython`` libraries can also
be used with careful parameter settings.

The ``mela`` module contains specific functions related to the hardware on a particular board.
To write portable code use functions and classes from the ``mela`` module.
To access platform-specific hardware use the appropriate library.

The original ``Mela-PLC`` comes with the ``mela`` library installed.


Installation
------------


Install with ``mip``
^^^^^^^^^^^^^^^^^^^^

Install the ``mela`` library from the ``mip`` repository:

.. code-block:: python

    mip.install('github:gmecc/mela')



Installation from GitHub
^^^^^^^^^^^^^^^^^^^^^^^^

Download the ``mela`` library from the repository. Run this command to install

.. code-block:: python

    mpremote mip install github:Linnaar/mela_example


Installing firmware with the ``mela`` library
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Download new firmware for ``Mela-PLC``:
https://github.com/gmecc/mela/blob/main/firmware/ESP32_GENERIC.bin

Clear controller memory:

.. code-block:: python

    python -m esptool --chip esp32-s3 erase_flash


Install new firmware:

.. code-block:: python

    python -m esptool --chip esp32s3 -p <port> write_flash -z 0 <name_firmware>.bin


Classes
-------

* ``Pin`` - control of inputs and outputs
* ``Button`` - eliminating contact bounce
* ``Led`` - control of built-in indicator Led GRB
* ``HMI`` - connection to HMI
* ``ADC`` - analog-to-digital converter
* ``RTC`` - real time clock
* ``Shedule`` - calendar
* ``Timer`` - timer
* ``PWM`` - pulse generator
* ``Counter`` - pulse counter
* ``Encoder`` - reading data from encoder
* ``Impulse`` - pulse generator
* ``Speed`` - speed detection
* ``Remote`` - control command pulse generator
* ``Inv`` - communication with frequency converters
* ``Measure`` - обмен данными с датчиками по протоколу modbusRTU
* ``Pid`` - PID controller
* ``Position`` - positioning
* ``Keyboard`` - decimal keyboard
* ``Indicator`` - 7 segment indicator
* ``Potentiometer`` - working with an external potentiometer
* ``Data`` - working with data
* ``Logging`` - having the logging
* ``Modbus`` - dummy exchange via `modbus RTU/TCP` protocol
* ``CAN`` - dummy exchange via `CAN` protocol
* ``Ethernet`` - dummy exchange via `Ethernet/IP-CIP` protocol 
* ``ML`` - machine learning
* ``I2C`` - dummy exchange via I2C protocol
* ``SPI`` - dummy exchange via SPI protocol
* ``RS-232`` - dummy data exchange via RS-232 port
* ``RS-485`` - dummy data exchange via RS-485 port
* ``Memory`` - memory information
* ``Set`` - setting up controller operating parameters


Usage
-----

.. code-block:: python

    from mela import Mela
    plc=Mela()
    print(plc.info.free)


