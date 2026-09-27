# One-Peace 🏴‍☠️
>Our plan for Third Space Hack Club - Week 2!

A locked box that refuses to open until brought to a specific geographic coordinate that can be determined through various puzzles.

ARG GitHub here:
[https://github.com/katfishkatfishing/Eye-of-God](https://github.com/katfishkatfishing/Eye-of-God)

## 💠 Project Overview 💠
An arg inspired puzzle, alien-y sci-fi themed reverse geocache box, meaning the user has to solve a series of puzzles to obtain the coordinates required for the box. Then guy has to bring it there and (hopefully) the box will open.

### Key Features 🗝️
+ GPS Tracking
  - GPS Receiver Module: An internal GPS receiver (NEO-6M) reads satellite NMEA signals to calculate latitude, longitude and altitude.
  - Geofencing & Distance logic: The internal microcontroller runs algorithms to calculate the distance between the box's current coordinates and the pre-programmed target coordinates.
  - Proximity Threshold: The box considers the destination "reached" once it is within a designated radius.

+ Locking Mechanism
  - Electronic Lock: A motorized latch-typically driven by a micro servo motor that secures the lid mechanism.
  - No External Keyholes: The exterior lacks traditional physical keyholes or manual padlocks (duh) to prevent brute-force opening without solving the puzzles.
  - Fail-Safe: In case battery dies or satellite signals drop permanently.
  
+ ARG Puzzle - Clues that lead to more clues that lead to the final destination — the "One Peace"

## PCB Stuff 💻
_WIP_

## Components List
+ Microcontroller & Wireless Modules
  - ESP32-S3-WROOM (Main MCU with Wi-fi & Bluetooth)
  - NEO-6M GPS Receiver Module

+ Power Management & Charging
  - TPS63020DSJR (High-Efficiency Buck-Boost DC-DC Converter)
  - AMS1117-3.3 (3.3V Low Dropout Linear Voltage Regulator - SOT-223)
  - MCP73871-2CC (LiPo / Li-Ion Battery Charge & System Power Path Management IC)

+ Display, Interface & Actuator
  - HS280S010B (2.8' SPI TFT LCD Screen)
  - Motor_Servo (3-Pin Header for Servo Motor / Solenoid control)
  - SW_Push (SMD Push Button Switch - B3U-1000P)
  - LEDs (0603 SMD Status LEDs) x3

+ Connectors
  - USB-C Receptacle (16-Pin USB 2.0 Port for power/flashing)
  - U.FL Antenna Connector (IPEX/U.FL coaxial connector for GPS antenna)
  - Conn_01x02 (2-Pin 2.54mm Header for battery connection)

+ Inductors
  - 1µH Power Inductor (SMD ANR4030)

+ Capacitors
  - 470µF Tantalum Capacitor (EIA-7343 / Case E)
  - 22µF Ceramic Capacitors (0603 SMD) x5
  - 10µF Ceramic Capacitors (0603 SMOD) x3
  - 1µF Ceramic Capacitor (0603 SMD)
  - 0.1µF (100nF) Ceramic Capacitors (0402 SMD) x2
  - 100nF Ceramic Capacitor (0402 SMD)
  - 10pF Ceramic Capacitor (0402 SMD)

+ Resistors
  - 1.6MΩ Resistor (0603 SMD)
  - 1MΩ Resistor (0603 SMD)
  - 180kΩ Resistor (0603 SMD)
  - 39kΩ Resistor (0603 SMD)
  - 10kΩ Resistors (0603 SMD) x2
  - 5.1kΩ Resistors (0603 SMD - USB-C CC Pull-downs) x2
  - 2kΩ Resistor (0603 SMD)
  - 470Ω Resistors (0402 SMD - Current-limiting for LEDs) x3
  - 0Ω Jumper Resistor (0402 SMD)

## BOM 💹
| Reference          | Qty | Value                         | DNP | Exclude from BOM | Exclude from Board | Footprint                                                                                  | Datasheet                                                                                            |
| ------------------ | --- | ----------------------------- | --- | ---------------- | ------------------ | ------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------- |
| C1                 | 1   | 470uF                         |     |                  |                    | Capacitor_Tantalum_SMD:CP_EIA-7343-43_Kemet-X_HandSolder                                   |                                                                                                      |
| C3,C9,C10          | 3   | 10uF                          |     |                  |                    | Capacitor_SMD:C_0603_1608Metric_Pad1.08x0.95mm_HandSolder                                  |                                                                                                      |
| C4,C7              | 2   | 0.1uF                         |     |                  |                    | Capacitor_SMD:C_0402_1005Metric_Pad0.74x0.62mm_HandSolder                                  |                                                                                                      |
| C5,C12,C13,C14,C15 | 5   | 22uF                          |     |                  |                    | Capacitor_SMD:C_0603_1608Metric_Pad1.08x0.95mm_HandSolder                                  |                                                                                                      |
| C6                 | 1   | 1uF                           |     |                  |                    | Capacitor_SMD:C_0603_1608Metric_Pad1.08x0.95mm_HandSolder                                  |                                                                                                      |
| C8                 | 1   | 100nF                         |     |                  |                    | Capacitor_SMD:C_0402_1005Metric_Pad0.74x0.62mm_HandSolder                                  |                                                                                                      |
| C11                | 1   | 10pF                          |     |                  |                    | Capacitor_SMD:C_0402_1005Metric_Pad0.74x0.62mm_HandSolder                                  |                                                                                                      |
| D3,D4,D5           | 3   | LED                           |     |                  |                    | LED_SMD:LED_0603_1608Metric_Pad1.05x0.95mm_HandSolder                                      |                                                                                                      |
| J1                 | 1   | USB_C_Receptacle_USB2.0_16P   |     |                  |                    | Connector_USB:USB_C_Receptacle_GCT_USB4085                                                 | https://www.usb.org/sites/default/files/documents/usb_type-c.zip                                     |
| J2                 | 1   | U.FL                          |     |                  |                    | U.FL_Molex_MCRF_73412-0110_Vertical:U.FL_Molex_MCRF_73412-0110_Vertical                    | https://wmsc.lcsc.com/wmsc/upload/file/pdf/v2/lcsc/2208151830_BAT-WIRELESS-BWU-FL-IPEX1_C5137195.pdf |
| J3                 | 1   | Conn_01x02                    |     |                  |                    | Connector_PinHeader_2.54mm:PinHeader_1x02_P2.54mm_Vertical                                 |                                                                                                      |
| L1                 | 1   | 1uH                           |     |                  |                    | Inductor_SMD:L_APV_ANR4030                                                                 |                                                                                                      |
| LCD1               | 1   | HS280S010B                    |     |                  |                    | lcsc_shared_footprints:C2939938_LCD-TH_HS280S010B                                          | https://wmsc.lcsc.com/wmsc/upload/file/pdf/v2/lcsc/2401291705_HS-HS280S010B_C2939938.pdf             |
| M1                 | 1   | Motor_Servo                   |     |                  |                    | Connector_PinHeader_2.54mm:PinHeader_1x03_P2.54mm_Vertical                                 | http://forums.parallax.com/uploads/attachments/46831/74481.png                                       |
| R6,R7,R8           | 3   | 470R                          |     |                  |                    | Resistor_SMD:R_0402_1005Metric_Pad0.72x0.64mm_HandSolder                                   |                                                                                                      |
| R9,R17             | 2   | 10k                           |     |                  |                    | Resistor_SMD:R_0603_1608Metric_Pad0.98x0.95mm_HandSolder                                   |                                                                                                      |
| R10                | 1   | 2k                            |     |                  |                    | Resistor_SMD:R_0603_1608Metric_Pad0.98x0.95mm_HandSolder                                   |                                                                                                      |
| R13,R14            | 2   | 5.1k                          |     |                  |                    | Resistor_SMD:R_0603_1608Metric_Pad0.98x0.95mm_HandSolder                                   |                                                                                                      |
| R18                | 1   | 0R                            |     |                  |                    | Resistor_SMD:R_0402_1005Metric_Pad0.72x0.64mm_HandSolder                                   |                                                                                                      |
| R19                | 1   | 1.6M                          |     |                  |                    | Resistor_SMD:R_0603_1608Metric_Pad0.98x0.95mm_HandSolder                                   |                                                                                                      |
| R20                | 1   | 39k                           |     |                  |                    | Resistor_SMD:R_0603_1608Metric_Pad0.98x0.95mm_HandSolder                                   |                                                                                                      |
| R21                | 1   | 1M                            |     |                  |                    | Resistor_SMD:R_0603_1608Metric                                                             |                                                                                                      |
| R22                | 1   | 180k                          |     |                  |                    | Resistor_SMD:R_0603_1608Metric_Pad0.98x0.95mm_HandSolder                                   |                                                                                                      |
| SW4                | 1   | SW_Push                       |     |                  |                    | Button_Switch_SMD:SW_SPST_B3U-1000P                                                        |                                                                                                      |
| U1                 | 1   | AMS1117-3.3                   |     |                  |                    | Package_TO_SOT_SMD:SOT-223-3_TabPin2                                                       | http://www.advanced-monolithic.com/pdf/ds1117.pdf                                                    |
| U2                 | 1   | NEO-6M-0-001_C32413118        |     |                  |                    | lcsc_shared_footprints:C32413118_SMD                                                       | None                                                                                                 |
| U3                 | 1   | TPS63020DSJR                  |     |                  |                    | lcsc_shared_footprints:C15483_VSON-14_L4_0-W3_0-P0_50-BL-EP_TI_DSJ                         | https://www.lcsc.com/datasheet/lcsc_datasheet_1809200040_Texas-Instruments-TPS63020DSJR_C15483.pdf   |
| U4                 | 1   | MCP73871-2CC                  |     |                  |                    | Package_DFN_QFN:QFN-20-1EP_4x4mm_P0.5mm_EP2.5x2.5mm                                        | http://www.mouser.com/ds/2/268/22090a-52174.pdf                                                      |
| U5                 | 1   | ESP32-S31-WROOM-3_C9900281993 |     |                  |                    | lcsc_shared_footprints:C9900281993_COMM-SMD_99P-L33_0-W26_0-P0_85_ESP32-S31-MINI-1-H16R16V | None                                                                                                 |