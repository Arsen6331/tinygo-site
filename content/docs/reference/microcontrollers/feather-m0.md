---
title: "Adafruit Feather M0"
weight: 3
---

The [Adafruit Feather M0](https://www.adafruit.com/product/3403) is a tiny ARM development board based on the Atmel [ATSAMD21G18](https://www.microchip.com/wwwproducts/en/ATSAMD21G18) family of SoC.

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
| `D0`              | `PA11`       |                   |
| `D1`              | `PA10`       | `I2S_SCK_PIN`     |
| `D3`              | `PA09`       |                   |
| `D4`              | `PA08`       | `I2S_SD_PIN`      |
| `D5`              | `PA15`       |                   |
| `D6`              | `PA20`       |                   |
| `D8`              | `PA06`       |                   |
| `D9`              | `PA07`       |                   |
| `D10`             | `PA18`       | `UART_TX_PIN`     |
| `D11`             | `PA16`       | `UART_RX_PIN`     |
| `D12`             | `PA19`       |                   |
| `D13`             | `PA17`       | `LED`             |
| `A0`              | `PA02`       |                   |
| `A1`              | `PB08`       |                   |
| `A2`              | `PB09`       |                   |
| `A3`              | `PA04`       |                   |
| `A4`              | `PA05`       |                   |
| `A5`              | `PB02`       |                   |
| `USBCDC_DM_PIN`   | `PA24`       |                   |
| `USBCDC_DP_PIN`   | `PA25`       |                   |
| `SDA_PIN`         | `PA22`       |                   |
| `SCL_PIN`         | `PA23`       |                   |
| `SPI0_SCK_PIN`    | `PB11`       |                   |
| `SPI0_SDO_PIN`    | `PB10`       |                   |
| `SPI0_SDI_PIN`    | `PA12`       |                   |

## Machine Package Docs

[Documentation for the machine package for the Adafruit Feather M0](../machine/feather-m0)

## Flashing

### UF2

The Feather M0 comes with the [UF2 bootloader](https://github.com/Microsoft/uf2) already installed.

### CLI Flashing

- Plug your Feather M0 into your computer's USB port.
- Flash your TinyGo program to the board using this command:

    ```shell
    tinygo flash -target=feather-m0 [PATH TO YOUR PROGRAM]
    ```

- The Feather M0 board should restart and then begin running your program.

### Troubleshooting

If you have troubles getting your Feather M0 board to receive code, try this:

- Press the "RESET" button on the board two times to get the Feather M0 board ready to receive code.
- The Feather M0 board will appear to your computer like a USB drive.
- Now try running the command as above:


```shell
tinygo flash -target=feather-m0 [PATH TO YOUR PROGRAM]
```

Once you have updated your Feather M0 board the first time, after that you should be able to flash it entirely from the command line.

## Notes

You can use the USB port to the Feather M0 as a serial port. `UART0` refers to this connection.
