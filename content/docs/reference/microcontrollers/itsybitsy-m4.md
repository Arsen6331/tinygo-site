---
title: "Adafruit ItsyBitsy M4"
weight: 3
---

The [Adafruit ItsyBitsy M4](https://www.adafruit.com/product/3800) is very compact ARM development board based on the Atmel [SAMD51](https://www.microchip.com/wwwproducts/en/ATSAMD51G19A) family of SoC.

## Interfaces

| Interface | Hardware Supported | TinyGo Support |
| --------- | ------------- | ----- |
| GPIO      | YES | YES |
| UART      | YES | YES |
| SPI       | YES | YES |
| I2C       | YES | YES |
| ADC       | YES | YES |
| PWM       | YES | YES |
| USBDevice | YES | YES |

## Pins

| Pin               | Hardware pin | Alternative names |
| ----------------- | ------------ | ----------------- |
| `D0`              | `PA16`       | `UART_RX_PIN`     |
| `D1`              | `PA17`       | `UART_TX_PIN`     |
| `D2`              | `PA07`       | `UART2_RX_PIN`    |
| `D3`              | `PB22`       |                   |
| `D4`              | `PA14`       |                   |
| `D5`              | `PA15`       |                   |
| `D6`              | `PB02`       |                   |
| `D7`              | `PA18`       |                   |
| `D8`              | `PB03`       |                   |
| `D9`              | `PA19`       |                   |
| `D10`             | `PA20`       |                   |
| `D11`             | `PA21`       |                   |
| `D12`             | `PA23`       |                   |
| `D13`             | `PA22`       | `LED`             |
| `A0`              | `PA02`       |                   |
| `A1`              | `PA05`       |                   |
| `A2`              | `PB08`       |                   |
| `A3`              | `PB09`       |                   |
| `A4`              | `PA04`       | `UART2_TX_PIN`    |
| `A5`              | `PA06`       |                   |
| `USBCDC_DM_PIN`   | `PA24`       |                   |
| `USBCDC_DP_PIN`   | `PA25`       |                   |
| `SDA_PIN`         | `PA12`       |                   |
| `SCL_PIN`         | `PA13`       |                   |
| `SPI0_SCK_PIN`    | `PA01`       |                   |
| `SPI0_SDO_PIN`    | `PA00`       |                   |
| `SPI0_SDI_PIN`    | `PB23`       |                   |
| `QSPI_SCK`        | `PB10`       |                   |
| `QSPI_CS`         | `PB11`       |                   |
| `QSPI_DATA0`      | `PA08`       |                   |
| `QSPI_DATA1`      | `PA09`       |                   |
| `QSPI_DATA2`      | `PA10`       |                   |
| `QSPI_DATA3`      | `PA11`       |                   |

## Machine Package Docs

[Documentation for the machine package for the Adafruit ItsyBitsy M4](../machine/itsybitsy-m4)

## Flashing

### UF2

The ItsyBitsy M4 comes with the [UF2 bootloader](https://github.com/Microsoft/uf2) already installed.

### CLI Flashing

- Plug your ItsyBitsy M4 into your computer's USB port.
- Flash your TinyGo program to the board using this command:

    ```shell
    tinygo flash -target=itsybitsy-m4 [PATH TO YOUR PROGRAM]
    ```

- The ItsyBitsy M4 board should restart and then begin running your program.

### Troubleshooting

If you have troubles getting your ItsyBitsy M4 board to receive code, try this:

- Press the "RESET" button on the board two times to get the ItsyBitsy M4 board ready to receive code.
- The ItsyBitsy M4 board will appear to your computer like a USB drive.
- Now try running the command as above:

    ```shell
    tinygo flash -target=itsybitsy-m4 [PATH TO YOUR PROGRAM]
    ```

Once you have updated your ItsyBitsy M4 board the first time, after that you should be able to flash it entirely from the command line.

## Notes

You can use the USB port to the ItsyBitsy M4 as a serial port. `UART0` refers to this connection.

The DotStar LED on the ItsyBitsy M4 can be accessed using the [APA102](https://pkg.go.dev/tinygo.org/x/drivers/apa102) driver via a software SPI on the `PB02` and `PB03` pins
