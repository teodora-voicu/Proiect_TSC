> # Voicu Teodora TSC - OpenBook Reader
>
> ## Implementation steps
>
> * Schematic Creation  
> * Push to 2D PCB  
> * Routing  
>   * GND plane  
>   * Net Class for Power Trails  
>   * Custom rules & constraints upload  
>   * Routing  
> * 3D Models design from datasheets  
>   * Battery  
>   * Screen  
>
> ## 🔧 Hardware Modules and Components
>
> **ESP32-C6-WROOM-1-N8 – Main Microcontroller:**  
> * WiFi 6, Bluetooth 5 LE, RISC-V core.  
> * Power Supply: 3.3V.  
> * Communications: SPI, I2C, UART, GPIO.  
>
> **SD Card Module**  
> * Interface: SPI  
> * Pins Used:  
>     * `SS_SD` → `IO4`  
>     * `MOSI` → `IO7`  
>     * `MISO` → `IO26`  
>     * `SCK` → `IO6`  
>
> **E-Paper Display**  
> * Interface: SPI  
> * Pins Used:  
>     * `EPD_CS` → `IO11`  
>     * `EPD_DC` → `IO5`  
>     * `EPD_RST` → `IO21`  
>     * `EPD_BUSY` → `IO26` (shared with `MISO`)  
>     * `MOSI`, `SCK` (shared with SD)  
>
> **RTC Module - DS3231SN**  
> * Interface: I2C  
> * Pins Used:  
>     * `SCL` → `IO20`  
>     * `SDA` → `IO19`  
>     * `INT_RTC` → `IO8`  
>     * `32KHZ` → `IO9`  
>     * `RTC_RST` → `IO16`  
>
> **Environmental Sensor - BME688**  
> * Interface: I2C (shared with RTC)  
> * Power Supply: 3.3V  
> * Pins Used: `IO19` (`SDA`), `IO20` (`SCL`)  
>
> **External Flash - NORFlash64MB**  
> * Interface: SPI  
> * Pins Used:  
>     * `FLASH_CS` → `IO12`  
>     * Rest (`MOSI`, `MISO`, `SCK`) shared  
>
> **SD/USB interface**  
> * `USB_D+` → `IO14`  
> * `USB_D-` → `IO13`  
>
> **Reset and Boot Buttons**  
> * `IO/BOOT` → `IO15`  
> * `RESET` → `IO3`  
>
> **Li-Po Battery Charging Controller**  
> * TP4056 or similar  
> * Built-in charging control.  
> * Battery level monitoring with:  
>     * Battery ChargeLevel IC → I2C (`IO19`, `IO20`)  
>
> **Qwiic / Stemma QT Connector**  
> * Communicates entirely via I2C (`SCL`/`SDA` shared with RTC/BME688)  
> * Environmental Sensor - BME688  
>     * Protocol: I2C (shared)  
>     * `IO19`/`IO20`  
>
> **SPI ESD Protection Lines**  
> * Protects the SPI lines for the SD card, e-paper, external flash.  
>
> **LDO Voltage Regulator**  
> * Steps down the voltage from 5V to 3.3V to power the ESP32-C6 and other modules.  
>
> **Diodes for reverse polarity protection.**
>
> **USB-C Connector + ESD Protection**  
> * Main power and data input.  
> * Includes TVS diodes for ESD protection.  
>
> # Block Diagram: Schematic Design
