---
title: "Adafruit Feather RP2040"
weight: 3
---

The [Adafruit Feather RP2040](https://www.adafruit.com/product/4884) is a tiny development board based on the Raspberry Pi [RP2040](https://datasheets.raspberrypi.org/rp2040/rp2040-datasheet.pdf) microcontroller.

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
| `D4`              | `GPIO6`      |                   |
| `D5`              | `GPIO7`      |                   |
| `D6`              | `GPIO8`      | `UART1_TX_PIN`    |
| `D9`              | `GPIO9`      | `UART1_RX_PIN`    |
| `D10`             | `GPIO10`     | `SPI1_SCK_PIN`    |
| `D11`             | `GPIO11`     | `SPI1_SDO_PIN`    |
| `D12`             | `GPIO12`     | `SPI1_SDI_PIN`    |
| `D13`             | `GPIO13`     | `LED`             |
| `D24`             | `GPIO24`     | `I2C0_SDA_PIN`    |
| `D25`             | `GPIO25`     | `I2C0_SCL_PIN`    |
| `A0`              | `GPIO26`     | `ADC0`            |
| `A1`              | `GPIO27`     | `ADC1`            |
| `A2`              | `GPIO28`     | `ADC2`            |
| `A3`              | `GPIO29`     | `ADC3`            |
| `I2C1_SDA_PIN`    | `GPIO2`      | `SDA_PIN`         |
| `I2C1_SCL_PIN`    | `GPIO3`      | `SCL_PIN`         |
| `SPI0_SCK_PIN`    | `GPIO18`     |                   |
| `SPI0_SDO_PIN`    | `GPIO19`     |                   |
| `SPI0_SDI_PIN`    | `GPIO20`     |                   |
| `UART0_TX_PIN`    | `GPIO0`      | `UART_TX_PIN`     |
| `UART0_RX_PIN`    | `GPIO1`      | `UART_RX_PIN`     |

## Machine Package Docs

[Documentation for the machine package for the Adafruit Feather RP2040](../machine/feather-rp2040)

## Flashing

### UF2

The Feather RP2040 comes with the [UF2 bootloader](https://github.com/Microsoft/uf2) already installed.

### CLI Flashing

- Plug your Feather RP2040 into your computer's USB port while holding down the RESET button on the board.
- One plugged in, release the RESET button.
- Flash your TinyGo program to the board using this command:

    ```shell
    tinygo flash -target=feather-rp2040 [PATH TO YOUR PROGRAM]
    ```

- The Feather RP2040 board should restart and then begin running your program.

### Troubleshooting

Any troubleshooting tips go here.

## Notes

You cannot yet use the USB port to the Feather RP2040 as a serial port. Instead `UART0` refers to the TX/RX pins on the board itself.
