.. zephyr:code-sample:: espressif_rmt
   :name: Espressif RMT
   :relevant-api: espressif_rmt

   Espressif RMT loopback application to demonstrate API usage.

Overview
********

This sample sends a RMT signal on one pin and read it back on another pin using Espressif RMT.
Demonstration is done with and without DMA support.

Requirements
************

To use this sample, the following hardware is required:

* An ESP32-DevKitC evaluation board
* Or an ESP32-S3-DevKitC evaluation board

Wiring
******

Pins 13 (Tx) and 12 (Rx) of the board must be connected together to establish the loopback.

Building and Running
********************

To build the sample on ESP32-DevKitC:

.. zephyr-app-commands::
   :zephyr-app: samples/drivers/misc/espressif_rmt
   :board: esp32_devkitc/esp32/procpu
   :goals: flash
   :compact:

To build the sample on ESP32-S3-DevKitC:

.. zephyr-app-commands::
   :zephyr-app: samples/drivers/misc/espressif_rmt
   :board: esp32s3_devkitc/esp32s3/procpu
   :goals: flash
   :compact:

The following logs will be available:

.. code-block:: console

   I (152) gpio: GPIO[12]| InputEn: 1| OutputEn: 0| OpenDrain: 0| Pullup: 1| Pulldown: 0| Intr:0
   I (154) gpio: GPIO[13]| InputEn: 0| OutputEn: 1| OpenDrain: 0| Pullup: 1| Pulldown: 0| Intr:0
   Enable RMT RX channel
   Enable RMT TX channel
   RMT TX value 0x00000000
   RMT RX value 0x00000000
   RMT TX value 0x00000001
   RMT RX value 0x00000001
   RMT TX value 0x00000002
   RMT RX value 0x00000002
   RMT TX value 0x00000003
   RMT RX value 0x00000003
   RMT TX value 0x00000004
   RMT RX value 0x00000004
   I (2676) gpio: GPIO[13]| InputEn: 0| OutputEn: 0| OpenDrain: 0| Pullup: 1| Pulldown: 0| Intr:0
   I (2676) gpio: GPIO[12]| InputEn: 0| OutputEn: 0| OpenDrain: 0| Pullup: 1| Pulldown: 0| Intr:0

.. _Espressif RMT: https://docs.espressif.com/projects/esp-idf/en/stable/esp32/api-reference/peripherals/rmt.html
