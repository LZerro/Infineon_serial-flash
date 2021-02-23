# Serial Flash

### Overview

Provides functions for interacting with an external flash connected through its Single SPI/Dual SPI/Quad SPI/Octal SPI interface. The read operation can be performed in either blocking or non-blocking manner by calling the corresponding function while the write and erase operations are implemented as blocking functions. This library accepts the configuration generated using the QSPI Configurator tool but supports only one memory slot. Note that PSoC 6 supports up to 4 memory slots on the same QSPI block.

### Features

* Supports asynchronous (non-blocking) read operation
* Implements thread-safety for use with multi-threaded RTOS environment using the [abstraction-rtos](https://github.com/cypresssemiconductorco/abstraction-rtos) library
* Accepts the configuration generated by the QSPI Configurator tool
* Supports Execute-in-Place (XIP) mode of operation
* Provides information about the external memory to the programming tool for it to be able to program the memory, for example, when user wants to place the code into the external memory for XIP operation.
* Allows for programming external memory if CY_ENABLE_XIP_PROGRAM is defined when building the application

### Quick Start
1. Add \#include "cy_serial_flash_qspi.h"
2. Add `DEFINES=CY_SERIAL_FLASH_QSPI_THREAD_SAFE` in the Makefile to enable thread-safety when used in a multi-threaded RTOS environment
3. See the [PSoC 6 MCU: QSPI Flash Read and Write](https://github.com/cypresssemiconductorco/mtb-example-psoc6-qspi-readwrite) code example to learn using this library

**NOTE:**
If you delete the contents of the GeneratedSource directory inside the BSP, you must re-generate the memory configuration files *cycfg_qspi_memslot.c/.h*. To do this from inside the ModusToolbox IDE, open the QSPI Configurator tool from the Quick Panel and press **Ctrl+S** or click **File > Save**. If you open the tool outside the IDE, you need to first open the *design.cyqspi* file in the tool. To do this, click **File > Import** and then locate the file inside the BSP under *COMPONENT_BSP_DESIGN_MODUS* directory.

### Dependencies

* [abstraction-rtos](https://github.com/cypresssemiconductorco/abstraction-rtos) library if `DEFINES=CY_SERIAL_FLASH_QSPI_THREAD_SAFE` is added in the Makefile

### More information

* [API Reference Guide](https://cypresssemiconductorco.github.io/serial-flash/html/index.html)
* [Cypress Semiconductor, an Infineon Technologies Company](http://www.cypress.com)
* [Cypress Semiconductor GitHub](https://github.com/cypresssemiconductorco)
* [ModusToolbox](https://www.cypress.com/products/modustoolbox-software-environment)
* [PSoC 6 Code Examples using ModusToolbox IDE](https://github.com/cypresssemiconductorco/Code-Examples-for-ModusToolbox-Software)
* [PSoC 6 Middleware](https://github.com/cypresssemiconductorco/psoc6-middleware)
* [PSoC 6 Resources - KBA223067](https://community.cypress.com/docs/DOC-14644)

---
© Cypress Semiconductor Corporation, 2019-2021.
