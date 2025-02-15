---
title: "Adafruit Circuit Playground Express"
weight: 3
---

The [Adafruit Circuit Playground Express](https://www.adafruit.com/product/3333) is small ARM development board based on the Atmel [SAMD21](https://www.microchip.com/wwwproducts/en/ATSAMD21G18) family of processors. It has several built-in devices such as WS2812 "NeoPixel" LEDs, buttons, an accelerometer, and some other sensors.

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
| `D0`              | `PB09`       | `A6`, `UART_RX_PIN` |
| `D1`              | `PB08`       | `A7`, `UART_TX_PIN` |
| `D2`              | `PB02`       | `A5`, `SDA_PIN`   |
| `D3`              | `PB03`       | `A4`, `SCL_PIN`   |
| `D4`              | `PA28`       | `BUTTONA`, `BUTTON` |
| `D5`              | `PA14`       | `BUTTONB`, `BUTTON1` |
| `D6`              | `PA05`       | `A1`              |
| `D7`              | `PA15`       | `SLIDER`          |
| `D8`              | `PB23`       | `NEOPIXELS`, `WS2812` |
| `D9`              | `PA06`       | `A2`              |
| `D10`             | `PA07`       | `A3`              |
| `D12`             | `PA02`       | `A0`              |
| `D13`             | `PA17`       | `LED`             |
| `A8`              | `PA11`       | `LIGHTSENSOR`     |
| `A9`              | `PA09`       | `TEMPSENSOR`      |
| `A10`             | `PA04`       | `PROXIMITY`       |
| `USBCDC_DM_PIN`   | `PA24`       |                   |
| `USBCDC_DP_PIN`   | `PA25`       |                   |
| `SDA1_PIN`        | `PA00`       |                   |
| `SCL1_PIN`        | `PA01`       |                   |
| `SPI0_SCK_PIN`    | `PA21`       |                   |
| `SPI0_SDO_PIN`    | `PA20`       |                   |
| `SPI0_SDI_PIN`    | `PA16`       |                   |
| `I2S_SCK_PIN`     | `PA10`       |                   |
| `I2S_SD_PIN`      | `PA08`       |                   |

## Machine Package Docs

[Documentation for the machine package for the Circuit Playground Express](../machine/circuitplay-express)

## Flashing

### UF2

The Circuit Playground Express comes with the [UF2 bootloader](https://github.com/Microsoft/uf2) already installed.

### CLI Flashing

- Plug your Circuit Playground Express into your computer's USB port.
- Flash your TinyGo program to the board using this command:

    ```shell
    tinygo flash -target=circuitplay-express [PATH TO YOUR PROGRAM]
    ```

- The Circuit Playground Express board should restart and then begin running your program.

### Troubleshooting

If you have troubles getting your Circuit Playground Express board to receive code, try this:

- Press the "RESET" button on the board two times to get the Circuit Playground Express board ready to receive code.
- The Circuit Playground Express board will appear to your computer like a USB drive.
- Now try running the command:

    ```shell
    tinygo flash -target=circuitplay-express [PATH TO YOUR PROGRAM]
    ```

Once you have updated your Circuit Playground Express board the first time, after that you should be able to flash it entirely from the command line.

## Notes

You can use the USB port to the Circuit Playground Express as a serial port. `UART0` refers to this connection.

The Neopixel LED on the Circuit Playground Express can be accessed using the [WS2812](https://pkg.go.dev/tinygo.org/x/drivers/ws2812) driver via the `PB23` pin.

For an example that uses the built-in Neopixel LEDs, take a look at the TinyGo drivers repository located at [https://github.com/tinygo-org/drivers/tree/release/examples](https://github.com/tinygo-org/drivers)
