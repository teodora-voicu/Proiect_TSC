
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
