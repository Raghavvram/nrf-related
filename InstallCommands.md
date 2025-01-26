To flash your .hex file onto the nRF52840 dongle, follow these steps:

1. **Put the dongle in DFU mode**: Press the reset button on the dongle. The RGB light will turn red with a fade pattern, indicating that the dongle is in DFU mode.

2. **Download and set up nrfutil**: If you haven't already, download and set up nrfutil on your machine. You can find it on the Nordic Semiconductor website.

3. **Generate the firmware package**: Open your terminal and navigate to the directory containing your .hex file. Run the following command to generate a firmware package:
   ```
   nrfutil pkg generate --hw-version 52 --sd-req=0x00 --application yourfile.hex --application-version 1 app.zip
   ```
   Replace `yourfile.hex` with the name of your .hex file.

4. **Flash the firmware package**: Use the following command to flash the firmware package onto the dongle:
   ```
   nrfutil device program --firmware app.zip --traits nordicDfu
   ```
