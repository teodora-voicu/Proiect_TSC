# Voicu Teodora-Andreea - OpenBook Reader

## Implementation Steps
1. **Generate the Schematic**  
   Begin by designing the circuit diagram, ensuring all components and connections are clearly laid out.

2. **Transition to 2D PCB**  
   Convert your schematic into a 2D PCB layout, positioning components and preparing for routing.

3. **Routing Process**  
   - **Ground Plane**: Allocate a dedicated layer (or area) for the ground reference to reduce noise.  
   - **Power Net Classes**: Create specific rules for power lines and high-current traces.  
   - **Custom Rules & Constraints**: Import or define custom guidelines for trace width, clearance, and other design parameters.  
   - **Route Traces**: Connect signals, power, and ground in an organized manner, adhering to all design constraints.

4. **3D Models from Datasheets**  
   - **Battery**: Develop or import a 3D model to visualize placement and mechanical fitting.  
   - **Screen**: Include a 3D representation of the display to confirm form factor compatibility.

---

## Hardware Modules and Components

### System Overview
This project brings together several hardware blocks to deliver a feature-rich and efficient system. Its architecture is designed to support diverse functionalities while maintaining reliable performance.

### Components

1. **ESP32-C6-WROOM-1-N8 Microcontroller**  
   Serves as the main processor, orchestrating communication and device control.  
   Offers a range of wireless options, including Wi-Fi, Bluetooth, Zigbee, and Thread.

2. **RTC Module (DS3231SN)**  
   Provides highly accurate timekeeping and date data via the I2C interface.

3. **Flash Memory (W25Q512JVEIQ)**  
   High-speed, SPI-based storage solution for firmware and user data.

4. **Battery Management IC (MCP73831)**  
   Manages Li-Ion battery charging through a USB Type-C input.  
   Monitors charging status and coordinates power usage via GPIO lines.

5. **Fuel Gauge IC (MAX17048G+T10)**  
   Keeps track of battery charge level and relays this information to the microcontroller using I2C.

6. **Environmental Sensor (BME680)**  
   Measures temperature, humidity, pressure, and gas levels.  
   Communicates over I2C.

7. **ePaper Display**  
   Renders information for the user.  
   Uses SPI communication for quick data updates.

8. **SD Card Socket (J4)**  
   Enables additional data storage or firmware upgrade capabilities.  
   Employs SPI for data transfer.

9. **USB Type-C Port (J2)**  
   Supplies power and connects to external devices.  
   Includes D+ and D− lines for USB data communication.

### ESP32-C6 Pin Connections
- **3V3**: Power rail supplied by the charging circuit  
- **EN**: Reset controller for the module  
- **IO0**: Connected to the RTC for alert or timing signals  
- **IO1**: Also interfaced with the RTC for a stable clock reference  
- **IO2**: SPI (MISO) line  
- **IO3**: Linked to ePaper display’s busy signal  
- **IO4**: Communicates with the SD card  
- **IO5**: Chooses between commands and data for the ePaper display  
- **IO6**: SPI clock for data synchronization  
- **IO7**: SPI (MOSI) line  
- **IO8**: (Reserved)  
- **IO9**: Boot button  
- **IO10**: Chip select for the ePaper display  
- **IO11**: Chip select for the flash memory  
- **IO12**: USB D+ line  
- **IO13**: USB D− line  
- **IO15**: Change button  
- **TXD0/GPIO16 & RXD0/GPIO17**: Used for UART debugging  
- **IO18**: Reset signal to the RTC  
- **IO19**: Powers I2C interface  
- **IO20**: Powers the display  
- **IO21**: I2C data line  
- **IO22**: I2C clock line  
- **IO23**: Reset line for the ePaper display  
- **GND**: Ground reference

---

## BOM (Bill of Materials)

**Note**: The TP parts were custom-made.

```markdown
## BOM (Bill of Materials)

| Nr. | Part Name         | Site Link                                                                                                                                   | Datasheet                                                                                                                                                |
|-----|-------------------|---------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1   | BOOT_BUTON        | [Link](https://www.snapeda.com/parts/EVQP7L01P/Panasonic%20Electronic%20Components/view-part/?welcome=home)                                 | [Datasheet](https://www.snapeda.com/parts/EVQP7L01P/Panasonic/datasheet/)                                                                                |
| 2   | C1                | [Link](https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO)                                                                  | [Datasheet](https://componentsearchengine.com/Datasheets/2/CC0402MRX5R5BB106.pdf)                                                                        |
| 3   | C1_BAT            | [Link](https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO)                                                                  | [Datasheet](https://componentsearchengine.com/Datasheets/2/CC0402MRX5R5BB106.pdf)                                                                        |
| 4   | C1_BAT2           | [Link](https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO)                                                                  | [Datasheet](https://componentsearchengine.com/Datasheets/2/CC0402MRX5R5BB106.pdf)                                                                        |
| 5   | C2                | [Link](https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO)                                                                  | [Datasheet](https://componentsearchengine.com/Datasheets/2/CC0402MRX5R5BB106.pdf)                                                                        |
| 6   | C2_BAT            | [Link](https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO)                                                                  | [Datasheet](https://componentsearchengine.com/Datasheets/2/CC0402MRX5R5BB106.pdf)                                                                        |
| 7   | C3                | [Link](https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO)                                                                  | [Datasheet](https://componentsearchengine.com/Datasheets/2/CC0402MRX5R5BB106.pdf)                                                                        |
| 8   | C4                | [Link](https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO)                                                                  | [Datasheet](https://componentsearchengine.com/Datasheets/2/CC0402MRX5R5BB106.pdf)                                                                        |
| 9   | C4_USB            | [Link](https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO)                                                                  | [Datasheet](https://componentsearchengine.com/Datasheets/2/CC0402MRX5R5BB106.pdf)                                                                        |
| 10  | C5                | [Link](https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO)                                                                  | [Datasheet](https://componentsearchengine.com/Datasheets/2/CC0402MRX5R5BB106.pdf)                                                                        |
| 11  | C5_USB            | [Link](https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO)                                                                  | [Datasheet](https://componentsearchengine.com/Datasheets/2/CC0402MRX5R5BB106.pdf)                                                                        |
| 12  | C6                | [Link](https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO)                                                                  | [Datasheet](https://componentsearchengine.com/Datasheets/2/CC0402MRX5R5BB106.pdf)                                                                        |
| 13  | C7                | [Link](https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO)                                                                  | [Datasheet](https://componentsearchengine.com/Datasheets/2/CC0402MRX5R5BB106.pdf)                                                                        |
| 14  | C8                | [Link](https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO)                                                                  | [Datasheet](https://componentsearchengine.com/Datasheets/2/CC0402MRX5R5BB106.pdf)                                                                        |
| 15  | C9                | [Link](https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO)                                                                  | [Datasheet](https://componentsearchengine.com/Datasheets/2/CC0402MRX5R5BB106.pdf)                                                                        |
| 16  | C10               | [Link](https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO)                                                                  | [Datasheet](https://componentsearchengine.com/Datasheets/2/CC0402MRX5R5BB106.pdf)                                                                        |
| 17  | C10_SUPERCAR      | [Link](https://industry.panasonic.com/global/en/products/control/switch/light-touch/number/evqpuj02k)                                        | [Datasheet](https://industry.panasonic.com/global/en/downloads?tab=catalog&small_g_cd=203&part_no=EVQPUJ02K)                                             |
| 18  | CHANGE_BUTTON     | [Link](https://www.snapeda.com/parts/EVQP7L01P/Panasonic%20Electronic%20Components/view-part/?welcome=home)                                 | [Datasheet](https://www.snapeda.com/parts/EVQP7L01P/Panasonic/datasheet/)                                                                                |
| 19  | C_DELAY           | [Link](https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO)                                                                  | [Datasheet](https://componentsearchengine.com/Datasheets/2/CC0402MRX5R5BB106.pdf)                                                                        |
| 20  | D1                | [Link](https://www.snapeda.com/parts/USBLC6-2SC6Y/STMicroelectronics/view-part/?ref=eda)                                                    | [Datasheet](https://www.snapeda.com/parts/USBLC6-2SC6Y/STMicroelectronics/view-part/?ref=eda)                                                            |
| 21  | D2                | [Link](https://ro.mouser.com/ProductDetail/KYOCERA-AVX/SD0805S020S1R0?qs=jCA%252BPfw4LHbpkAoSnwrdjw%3D%3D)                                    | [Datasheet](https://ro.mouser.com/datasheet/2/40/schottky-3165252.pdf)                                                                                   |
| 22  | D3                | [Link](https://ro.mouser.com/ProductDetail/KYOCERA-AVX/SD0805S020S1R0?qs=jCA%252BPfw4LHbpkAoSnwrdjw%3D%3D)                                    | [Datasheet](https://ro.mouser.com/datasheet/2/40/schottky-3165252.pdf)                                                                                   |
| 23  | D4                | [Link](https://ro.mouser.com/ProductDetail/KYOCERA-AVX/SD0805S020S1R0?qs=jCA%252BPfw4LHbpkAoSnwrdjw%3D%3D)                                    | [Datasheet](https://ro.mouser.com/datasheet/2/40/schottky-3165252.pdf)                                                                                   |
| 24  | D5                | [Link](https://ro.mouser.com/ProductDetail/KYOCERA-AVX/SD0805S020S1R0?qs=jCA%252BPfw4LHbpkAoSnwrdjw%3D%3D)                                    | [Datasheet](https://ro.mouser.com/datasheet/2/40/schottky-3165252.pdf)                                                                                   |
| 25  | D6                | [Link](https://www.snapeda.com/parts/PGB1010603MR/Littelfuse/view-part/?ref=eda)                                                            | [Datasheet](https://www.snapeda.com/parts/PGB1010603MR/Littelfuse%20Inc./datasheet/)                                                                     |
| 26  | D7                | [Link](https://ro.mouser.com/ProductDetail/KYOCERA-AVX/SD0805S020S1R0?qs=jCA%252BPfw4LHbpkAoSnwrdjw%3D%3D)                                    | [Datasheet](https://ro.mouser.com/datasheet/2/40/schottky-3165252.pdf)                                                                                   |
| 27  | D8                | [Link](https://www.snapeda.com/parts/PGB1010603MR/Littelfuse/view-part/?ref=eda)                                                            | [Datasheet](https://www.snapeda.com/parts/PGB1010603MR/Littelfuse%20Inc./datasheet/)                                                                     |
| 28  | D9                | [Link](https://www.snapeda.com/parts/PGB1010603MR/Littelfuse/view-part/?ref=eda)                                                            | [Datasheet](https://www.snapeda.com/parts/PGB1010603MR/Littelfuse%20Inc./datasheet/)                                                                     |
| 29  | D10               | [Link](https://www.snapeda.com/parts/PGB1010603MR/Littelfuse/view-part/?ref=eda)                                                            | [Datasheet](https://www.snapeda.com/parts/PGB1010603MR/Littelfuse%20Inc./datasheet/)                                                                     |
| 30  | D11               | [Link](https://www.snapeda.com/parts/PGB1010603MR/Littelfuse/view-part/?ref=eda)                                                            | [Datasheet](https://www.snapeda.com/parts/PGB1010603MR/Littelfuse%20Inc./datasheet/)                                                                     |
| 31  | D12               | [Link](https://www.snapeda.com/parts/PGB1010603MR/Littelfuse/view-part/?ref=eda)                                                            | [Datasheet](https://www.snapeda.com/parts/PGB1010603MR/Littelfuse%20Inc./datasheet/)                                                                     |
| 32  | EPD_C1            | [Link](https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO)                                                                  | [Datasheet](https://componentsearchengine.com/Datasheets/2/CC0402MRX5R5BB106.pdf)                                                                        |
| 33  | EPD_C2            | [Link](https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO)                                                                  | [Datasheet](https://componentsearchengine.com/Datasheets/2/CC0402MRX5R5BB106.pdf)                                                                        |
| 34  | EPD_C5            | [Link](https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO)                                                                  | [Datasheet](https://componentsearchengine.com/Datasheets/2/CC0402MRX5R5BB106.pdf)                                                                        |
| 35  | EPD_C6            | [Link](https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO)                                                                  | [Datasheet](https://componentsearchengine.com/Datasheets/2/CC0402MRX5R5BB106.pdf)                                                                        |
| 36  | EPD_C7            | [Link](https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO)                                                                  | [Datasheet](https://componentsearchengine.com/Datasheets/2/CC0402MRX5R5BB106.pdf)                                                                        |
| 37  | EPD_C8            | [Link](https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO)                                                                  | [Datasheet](https://componentsearchengine.com/Datasheets/2/CC0402MRX5R5BB106.pdf)                                                                        |
| 38  | EPD_C9            | [Link](https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO)                                                                  | [Datasheet](https://componentsearchengine.com/Datasheets/2/CC0402MRX5R5BB106.pdf)                                                                        |
| 39  | EPD_C10           | [Link](https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO)                                                                  | [Datasheet](https://componentsearchengine.com/Datasheets/2/CC0402MRX5R5BB106.pdf)                                                                        |
| 40  | EPD_C11           | [Link](https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO)                                                                  | [Datasheet](https://componentsearchengine.com/Datasheets/2/CC0402MRX5R5BB106.pdf)                                                                        |
| 41  | EPD_C12           | [Link](https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO)                                                                  | [Datasheet](https://componentsearchengine.com/Datasheets/2/CC0402MRX5R5BB106.pdf)                                                                        |
| 42  | IC1               | [Link](https://componentsearchengine.com/part-view/BD5229G-TR/ROHM%20Semiconductor)                                                          | [Datasheet](https://datasheet.datasheetarchive.com/originals/distributors/Datasheets_SAMA/f2b9741ef86007909f138d561a359946.pdf)                          |
| 43  | IC4               | [Link](https://componentsearchengine.com/part-view/XC6220A331MR-G/Torex)                                                                     | [Datasheet](https://product.torexsemi.com/system/files/series/xc6220.pdf)                                                                                |
| 44  | J1                | [Link](https://componentsearchengine.com/part-view/FH34SRJ-24S-0.5SH%2899%29/Hirose)                                                         | [Datasheet](https://www.hirose.com/en/product/document?clcode=CL0580-1255-6-99&productname=FH34SRJ-24S-0.5SH%2899%29&series=FH34SRJ&documenttype=2DDrawing&lang=en&documentid=0000990903) |
| 45  | J2                | [Link](https://componentsearchengine.com/part-view/USB4110-GF-A/GCT%20(GLOBAL%20CONNECTOR%20TECHNOLOGY))                                     | [Datasheet](https://gct.co/files/drawings/usb4110.pdf)                                                                                                   |
| 46  | J3                | [Link](https://www.snapeda.com/parts/PRT-14417/SparkFun/view-part/)                                                                          | [Datasheet](https://www.snapeda.com/parts/PRT-14417/SparkFun%20Electronics/datasheet/)                                                                    |
| 47  | J4                | [Link](https://www.snapeda.com/parts/112A-TAAR-R03/Attend/view-part/)                                                                        | [Datasheet](https://www.snapeda.com/parts/112A-TAAR-R03/Attend/datasheet/)                                                                               |
| 48  | MCP73831          | [Link](https://ro.mouser.com/ProductDetail/Microchip-Technology/MCP73831T-2ACI-OT?qs=yUQqVecv4qvbBQBGbHx0Mw%3D%3D&utm_id=20109199409&utm_source=google&utm_medium=cpc&utm_marketing_tactic=emeacorp&gad_source=1&gbraid=0AAAAADn_wf0-USzm1eg1ywGvQg_qMgG3H) | [Datasheet](https://ro.mouser.com/datasheet/2/268/MCP73831_Family_Data_Sheet_DS20001984H-3441711.pdf)                                                    |
| 49  | L1                | [Link](https://ro.mouser.com/ProductDetail/Wurth-Elektronik/744043680?qs=PGXP4M47uW6VkZq%252BkzjrHA%3D%3D)                                     | [Datasheet](https://www.we-online.com/components/products/datasheet/744043680.pdf)                                                                       |
| 50  | PFMF.050.1        | [Link](https://ro.mouser.com/ProductDetail/EPCOS-TDK/B72520T0350K062?qs=dEfas%2FXlABIszF52uu7vrg%3D%3D)                                       | [Datasheet](https://www.tdk-electronics.tdk.com/inf/75/db/CTVS_14/Surge_protection_series.pdf)                                                           |
| 51  | Q1                | [Link](https://componentsearchengine.com/part-view/DMG2305UX-7/Diodes%20Incorporated)                                                        | [Datasheet](https://www.diodes.com//assets/Datasheets/DMG2305UX.pdf)                                                                                     |
| 52  | Q2                | [Link](https://componentsearchengine.com/part-view/DMG2305UX-7/Diodes%20Incorporated)                                                        | [Datasheet](https://www.diodes.com//assets/Datasheets/DMG2305UX.pdf)                                                                                     |
| 53  | Q3                | [Link](https://componentsearchengine.com/part-view/SI1308EDL-T1-GE3/Vishay)                                                                   | [Datasheet](https://componentsearchengine.com/part-view/SI1308EDL-T1-GE3/Vishay)                                                                          |
| 54  | R1                | [Link](https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20%28RC0402FR-07100KL%29/YAGEO)                                     | [Datasheet](https://www.yageo.com/upload/media/product/products/datasheet/rchip/PYu-RC_Group_51_RoHS_L_12.pdf)                                           |
| 55  | R1_PINH           | [Link](https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20%28RC0402FR-07100KL%29/YAGEO)                                     | [Datasheet](https://www.yageo.com/upload/media/product/products/datasheet/rchip/PYu-RC_Group_51_RoHS_L_12.pdf)                                           |
| 56  | R1_PINH1          | [Link](https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20%28RC0402FR-07100KL%29/YAGEO)                                     | [Datasheet](https://www.yageo.com/upload/media/product/products/datasheet/rchip/PYu-RC_Group_51_RoHS_L_12.pdf)                                           |
| 57  | R1_BAT            | [Link](https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20%28RC0402FR-07100KL%29/YAGEO)                                     | [Datasheet](https://www.yageo.com/upload/media/product/products/datasheet/rchip/PYu-RC_Group_51_RoHS_L_12.pdf)                                           |
| 58  | R1_PWRUSB         | [Link](https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20%28RC0402FR-07100KL%29/YAGEO)                                     | [Datasheet](https://www.yageo.com/upload/media/product/products/datasheet/rchip/PYu-RC_Group_51_RoHS_L_12.pdf)                                           |
| 59  | R2                | [Link](https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20%28RC0402FR-07100KL%29/YAGEO)                                     | [Datasheet](https://www.yageo.com/upload/media/product/products/datasheet/rchip/PYu-RC_Group_51_RoHS_L_12.pdf)                                           |
| 60  | R2_PINH           | [Link](https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20%28RC0402FR-07100KL%29/YAGEO)                                     | [Datasheet](https://www.yageo.com/upload/media/product/products/datasheet/rchip/PYu-RC_Group_51_RoHS_L_12.pdf)                                           |
| 61  | R2-PINH1          | [Link](https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20%28RC0402FR-07100KL%29/YAGEO)                                     | [Datasheet](https://www.yageo.com/upload/media/product/products/datasheet/rchip/PYu-RC_Group_51_RoHS_L_12.pdf)                                           |
| 62  | R2                | [Link](https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20%28RC0402FR-07100KL%29/YAGEO)                                     | [Datasheet](https://www.yageo.com/upload/media/product/products/datasheet/rchip/PYu-RC_Group_51_RoHS_L_12.pdf)                                           |
| 63  | R2-PINH           | [Link](https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20%28RC0402FR-07100KL%29/YAGEO)                                     | [Datasheet](https://www.yageo.com/upload/media/product/products/datasheet/rchip/PYu-RC_Group_51_RoHS_L_12.pdf)                                           |
| 64  | R2-PINH1          | [Link](https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20%28RC0402FR-07100KL%29/YAGEO)                                     | [Datasheet](https://www.yageo.com/upload/media/product/products/datasheet/rchip/PYu-RC_Group_51_RoHS_L_12.pdf)                                           |
| 65  | R2_USB            | [Link](https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20%28RC0402FR-07100KL%29/YAGEO)                                     | [Datasheet](https://www.yageo.com/upload/media/product/products/datasheet/rchip/PYu-RC_Group_51_RoHS_L_12.pdf)                                           |
| 66  | R2_USB            | [Link](https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20%28RC0402FR-07100KL%29/YAGEO)                                     | [Datasheet](https://www.yageo.com/upload/media/product/products/datasheet/rchip/PYu-RC_Group_51_RoHS_L_12.pdf)                                           |
| 67  | R2_USB1           | [Link](https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20%28RC0402FR-07100KL%29/YAGEO)                                     | [Datasheet](https://www.yageo.com/upload/media/product/products/datasheet/rchip/PYu-RC_Group_51_RoHS_L_12.pdf)                                           |
| 68  | R3                | [Link](https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20%28RC0402FR-07100KL%29/YAGEO)                                     | [Datasheet](https://www.yageo.com/upload/media/product/products/datasheet/rchip/PYu-RC_Group_51_RoHS_L_12.pdf)                                           |
| 69  | R4                | [Link](https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20%28RC0402FR-07100KL%29/YAGEO)                                     | [Datasheet](https://www.yageo.com/upload/media/product/products/datasheet/rchip/PYu-RC_Group_51_RoHS_L_12.pdf)                                           |
| 70  | R5                | [Link](https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20%28RC0402FR-07100KL%29/YAGEO)                                     | [Datasheet](https://www.yageo.com/upload/media/product/products/datasheet/rchip/PYu-RC_Group_51_RoHS_L_12.pdf)                                           |
| 71  | R6                | [Link](https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20%28RC0402FR-07100KL%29/YAGEO)                                     | [Datasheet](https://www.yageo.com/upload/media/product/products/datasheet/rchip/PYu-RC_Group_51_RoHS_L_12.pdf)                                           |
| 72  | R7                | [Link](https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20%28RC0402FR-07100KL%29/YAGEO)                                     | [Datasheet](https://www.yageo.com/upload/media/product/products/datasheet/rchip/PYu-RC_Group_51_RoHS_L_12.pdf)                                           |
| 73  | R8                | [Link](https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20%28RC0402FR-07100KL%29/YAGEO)                                     | [Datasheet](https://www.yageo.com/upload/media/product/products/datasheet/rchip/PYu-RC_Group_51_RoHS_L_12.pdf)                                           |
| 74  | R9                | [Link](https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20%28RC0402FR-07100KL%29/YAGEO)                                     | [Datasheet](https://www.yageo.com/upload/media/product/products/datasheet/rchip/PYu-RC_Group_51_RoHS_L_12.pdf)                                           |
| 75  | R10               | [Link](https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20%28RC0402FR-07100KL%29/YAGEO)                                     | [Datasheet](https://www.yageo.com/upload/media/product/products/datasheet/rchip/PYu-RC_Group_51_RoHS_L_12.pdf)                                           |
| 76  | RESET_BUTTON      | [Link](https://www.snapeda.com/parts/EVQP7L01P/Panasonic%20Electronic%20Components/view-part/?welcome=home)                                 | [Datasheet](https://www.snapeda.com/parts/EVQP7L01P/Panasonic/datasheet/)                                                                                |
| 77  | R_BOOT            | [Link](https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20%28RC0402FR-07100KL%29/YAGEO)                                     | [Datasheet](https://www.yageo.com/upload/media/product/products/datasheet/rchip/PYu-RC_Group_51_RoHS_L_12.pdf)                                           |
| 78  | R_CAPACITOR       | [Link](https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20%28RC0402FR-07100KL%29/YAGEO)                                     | [Datasheet](https://www.yageo.com/upload/media/product/products/datasheet/rchip/PYu-RC_Group_51_RoHS_L_12.pdf)                                           |
| 79  | R_CHANGE          | [Link](https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20%28RC0402FR-07100KL%29/YAGEO)                                     | [Datasheet](https://www.yageo.com/upload/media/product/products/datasheet/rchip/PYu-RC_Group_51_RoHS_L_12.pdf)                                           |
| 80  | R_CL1            | [Link](https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20%28RC0402FR-07100KL%29/YAGEO)                                      | [Datasheet](https://www.yageo.com/upload/media/product/products/datasheet/rchip/PYu-RC_Group_51_RoHS_L_12.pdf)                                           |
| 81  | R_RESET           | [Link](https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20%28RC0402FR-07100KL%29/YAGEO)                                     | [Datasheet](https://www.yageo.com/upload/media/product/products/datasheet/rchip/PYu-RC_Group_51_RoHS_L_12.pdf)                                           |
| 82  | SENSOR2           | [Link](https://www.snapeda.com/parts/BME680/Bosch/view-part/?welcome=home)                                                                  | [Datasheet](https://www.snapeda.com/parts/BME680/Bosch%20Sensortec/datasheet/)                                                                            |
| 83  | SJ1               | [Link](https://grabcad.com/library/solder-jumpers-1)                                                                                         | [Datasheet](https://grabcad.com/library/solder-jumpers-1)                                                                                                |
| 84  | TP1               |                                                                                                                                             |                                                                                                                                                           |
| 85  | TP2               |                                                                                                                                             |                                                                                                                                                           |
| 86  | TP3               |                                                                                                                                             |                                                                                                                                                           |
| 87  | TP4               |                                                                                                                                             |                                                                                                                                                           |
| 88  | TP5               |                                                                                                                                             |                                                                                                                                                           |
| 89  | TP6               |                                                                                                                                             |                                                                                                                                                           |
| 90  | TP7               |                                                                                                                                             |                                                                                                                                                           |
| 91  | TP8               |                                                                                                                                             |                                                                                                                                                           |
| 92  | TP9               |                                                                                                                                             |                                                                                                                                                           |
| 93  | TP10              |                                                                                                                                             |                                                                                                                                                           |
| 94  | TP11              |                                                                                                                                             |                                                                                                                                                           |
| 95  | TP12              |                                                                                                                                             |                                                                                                                                                           |
| 96  | TP13              |                                                                                                                                             |                                                                                                                                                           |
| 97  | TP14              |                                                                                                                                             |                                                                                                                                                           |
| 98  | TP15              |                                                                                                                                             |                                                                                                                                                           |
| 99  | TP16              |                                                                                                                                             |                                                                                                                                                           |
| 100 | TP17              |                                                                                                                                             |                                                                                                                                                           |
| 101 | U1               | [Link](https://www.snapeda.com/parts/W25Q512JVEIQ/Winbond+Electronics/view-part/?ref=eda)                                                    | [Datasheet](https://www.snapeda.com/parts/W25Q512JVEIQ/Winbond+Electronics/view-part/?ref=eda)                                                           |
| 102 | U2               | [Link](https://www.snapeda.com/parts/ESP32-C6-WROOM-1-N8/Espressif+Systems/view-part/?ref=eda)                                               | [Datasheet](https://www.snapeda.com/parts/ESP32-C6-WROOM-1-N8/Espressif%20Systems/datasheet/)                                                            |
| 103 | U3               | [Link](https://www.snapeda.com/parts/DS3231SN%23/Analog+Devices/view-part/?ref=eda)                                                          | [Datasheet](https://www.snapeda.com/parts/DS3231SN%23/Analog%20Devices/datasheet/)                                                                       |
| 104 | U4               | [Link](https://www.snapeda.com/parts/MAX17048G+T10/Analog+Devices/view-part/?ref=eda)                                                        | [Datasheet](https://www.snapeda.com/parts/MAX17048G+T10/Analog%20Devices/datasheet/)                                                                      |
