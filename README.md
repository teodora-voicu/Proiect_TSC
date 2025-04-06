
# OpenBook Reader - Teodora-Andreea Voicu

# Hardware Description

**ESP32-C6-WROOM-1-N8 Microcontroller**
- Serves as the central processing unit, managing all communication and control  
- Supports Wi-Fi, Bluetooth, Zigbee, and Thread for wireless communication

**RTC Module (DS3231SN)**
- Maintains accurate timekeeping and provides time/date information via the I2C protocol

**Flash Memory (W25Q512JVEIQ)**
- Provides high-speed storage using the SPI protocol  
- Used for firmware and data storage

**Battery Management IC (MCP73831)**
- Handles charging of the Li-Ion battery with input from the USB Type-C port  
- GPIO pins monitor charging status and control power management

**Fuel Gauge IC (MAX17048G+T10)**
- Tracks the battery's state of charge and communicates with the microcontroller via I2C

**Environmental Sensor (BME680)**
- Monitors temperature, humidity, pressure, and gas levels  
- Connects via the I2C protocol

**ePaper Display**
- Displays information to the user  
- Interfaced using SPI for fast data updates

**SD Card Socket (J4)**
- Provides expandable storage for data logging or firmware updates  
- Communicates using SPI

**USB Type-C Port (J2)**
- Supplies power to the system and enables communication with external devices  
- Includes D+ and D− lines for USB data transfer

# Detailed ESP32-C6 View

**ESP32-C6 Pin Connections**
- **3V3**: Charging 3.3V  
- **EN**: Reset button  
- **IO0**: Communication with the RTC (alert or timing signals)  
- **IO1**: Communication with the RTC for a stable clock reference  
- **IO2**: Used for SPI (Master In Slave Out)  
- **IO3**: Connects to the display, indicating the display’s busy status  
- **IO4**: Communicates with the SD card  
- **IO5**: Connects to the display, distinguishing between data and command signals  
- **IO6**: Used for SPI communication, synchronizes data transfer  
- **IO7**: Used for SPI (Master Out Slave In)  
- **IO8**:  
- **IO9**: Boot button  
- **IO10**: Connects to the display, selects the display for communication  
- **IO11**: Selects the flash memory for communication  
- **IO12**: D+ for USB connection  
- **IO13**: D− for USB connection  
- **IO15**: Change button  
- **TXD0 / GPIO16**: Used for UART debugging  
- **RXD0 / GPIO17**: Used for UART debugging  
- **IO18**: Resets the RTC  
- **IO19**: Power pin for I2C communication  
- **IO20**: Power supply for the display  
- **IO21**: I2C data pin  
- **IO22**: I2C clock pin  
- **IO23**: Resets the display  
- **GND**: Connected to ground



## BOM

| **Piece Name**                          | **Piece Type (Optional)**            | **Link** |
|----------------------------------------|--------------------------------------|----------|
| ESP32-CAP C0402                        | C                                    | https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO |
| ADAFRUIT_CHIP-LED0603                  | LED                                  | https://www.snapeda.com/parts/KP-1608SURCK/Kingbright/view-part/?ref=search&t=LED%200603 |
| 112ATAARR03                            | microSD                              | https://www.snapeda.com/parts/112A-TAAR-R03/Attend/view-part/ |
| 744043680                              | L                                    | https://eu.mouser.com/ProductDetail/Wurth-Elektronik/744043680?qs=PGXP4M47uW6VkZq%252BkzjrHA%3D%3D |
| BD5229G-TR                             | Voltage Detector                     | https://www.snapeda.com/parts/BD5229G-TR/Rohm/view-part/?ref=search&t=BD5229G-TR |
| BUTTON_CUSYOMV1                        | Button                               | https://www.snapeda.com/search/?q=EVQP7L01P&search-type=parts |
| CPH3225A                               | C                                    | https://www.snapeda.com/parts/CPH3225A/Seiko/view-part/ |
| DS3231SN#                              | I²C-Integrated RTC/TCXO/Crystal      | https://www.snapeda.com/parts/DS3231SN%23/Analog%20Devices/view-part/?ref=search&t=DS3231SN%23 |
| ESP32-C6-WROOM-1-N8                    | ESP32                              | https://www.snapeda.com/parts/ESP32-C6-WROOM-1-N8/Espressif%20Systems/view-part/?ref=search&t=ESP32-C6-WROOM-1-N8 |
| ESP VARSISTOR                          | Varsistor (B72520T0350K062)                      | https://ro.mouser.com/ProductDetail/EPCOS-TDK/B72520T0350K062?qs=dEfas%2FXlABIszF52uu7vrg%3D%3D |
| ESP32_WROVER_AVX---SD0805S020S1R0      |  DIODE SCHOTTKY                       | https://componentsearchengine.com/part-view/SD0805S020S1R0/Kyocera%20AVX |
| ESP32_WROVER_BME680_BME680             | Env Senzor                            | https://www.snapeda.com/parts/BME680/Bosch%20Sensortec/view-part/?ref=search&t=bme680 |
| ESP32_WROVER_EAGLE-LTSPICE_R           | R                                    | https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20(RC0402FR-07100KL)/YAGEO |
| ESP32_WROVER_SPARKFUN-DISCRETESEMI_MOSFET_PCH | T DMG2305UX-7                 | https://componentsearchengine.com/part-view/DMG2305UX-7/Diodes%20Incorporated |
| ESP32_WROVER_SPARKFUN-IC-POWER_MCP73831 | TINY INTEGRATED LI-ION/LI-POLY CHARGE MGNT CONTROLLER | https://componentsearchengine.com/part-view/MCP73831T-2ACI%2FOT/Microchip |
| FH34SRJ-24S-0.5SH_99_                   | FH34SRJ-24S-0.5SH(99)               | https://componentsearchengine.com/part-view/FH34SRJ-24S-0.5SH(99)/Hirose |
| MAX17048G+T10                          |  Cell Fuel Gauge with ModelGauge     | https://www.snapeda.com/parts/MAX17048G+T10/Analog%20Devices/view-part/ |
| MBR0530                                |  Diode Schottky                      | https://www.snapeda.com/parts/MBR0530/Onsemi/view-part/ |
| PGB1010603MR                           |  Ipp Tvs Diode Surface Mount 0603    | https://www.snapeda.com/parts/PGB1010603MR/Littelfuse/view-part/ |
| QWIIC_CONNECTOR                        | PRT-14417 QWIIC_CONNECTOR                 | https://www.snapeda.com/parts/PRT-14417/SparkFun/view-part/ |
| RCL_CPOL-EU                            | C pol                                | https://grabcad.com/library/tantalum-smd-capacitor-type-b-3528-1 |
| SAMACSYS_PARTS_USB4110-GF-A            | USB4110-GF-A                         | https://www.snapeda.com/parts/USB4110-GF-A./Global%20Connector%20Technology/view-part/ |
| SJ                                     | Jumper-SolderPasteJumper3way         | https://grabcad.com/library/solder-jumpers-1 |
| TP                                     | Test-Pad                             | - |
| SI1308EDL-T1-GE3                       |  MOSFET Transistor                 | https://www.snapeda.com/parts/SI1308EDL-T1-GE3/Vishay/view-part/ |
| USBLC6-2SC6Y                           |  Ipp Tvs Diode Surface Mount                                    | https://www.snapeda.com/parts/USBLC6-2SC6Y/STMicroelectronics/view-part/?ref=dk&t=USBLC6-2SC6Y&con_ref=None |
| W25Q512JVEIQ                           | FLASH - NOR Memory                                 | https://www.snapeda.com/parts/W25Q512JVEIQ/Winbond%20Electronics/view-part/?ref=search&t=W25Q512JVEIQ |
| XC6220A331MR-G                         | Voltage Regulator              | https://ro.mouser.com/ProductDetail/Torex-Semiconductor/XC6220A331MR-G?qs=AsjdqWjXhJ8ZSWznL1J0gg%3D%3D&utm_source=octopart&utm_medium=aggregator&utm_campaign=865-XC6220A331MR-G&utm_content=Torex%20Semiconductor |


# Block Diagram
