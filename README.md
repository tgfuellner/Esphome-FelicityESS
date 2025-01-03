# Esphome-FelicityESS
Read info from FelicityESS 48100LCG01 with esphome over RS485 (ModBus)

## My setup:

- Two FelicityESS LiFePO4  Units each having 5kWh:

![PXL_20241129_152614761 MP](https://github.com/user-attachments/assets/dcc261d7-df65-42ea-9c78-91f3ef903ff6)

- ESP32 module and an RS485 transceiver module:

![PXL_20241129_152550256](https://github.com/user-attachments/assets/88ba2ca4-953b-4313-94db-17ee36df1227)

![image](https://github.com/user-attachments/assets/7f44592e-2e98-4b2b-81b4-3280ea343dc5)
![PXL_20241129_152533838](https://github.com/user-attachments/assets/53f8560b-05e9-4e03-9edf-caa90e45e9d0)

## Connecting esp32 and rs485 Module

The transceiver connects to the UART of the MCU. For ESP32, pin 16 to TXD and pin 17 to RXD are the default ones but any other pins can be used as well. 3.3V to VCC and naturally GND to GND.

See https://esphome.io/components/modbus_controller.html

## Esphome stuff

Install the great https://esphome.io/

then execute:

`esphome run felicity-speicher.yaml`

This should compile and upload the code to the esp32

## Home Assistant

- Esphome plays well with https://www.home-assistant.io/

<img width="317" alt="image" src="https://github.com/user-attachments/assets/dcd4d62b-c6cd-49c3-bea3-abb310fe0931">


## Config

If You have only one Felicity Unit, delete entry m2 under modbus_controller and all sensors reffering to m2.

If You have more Felicity Units, create a modbus_controller per Unit.
