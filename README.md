# ESP-NES - A Custom PCB for the ESP32 NES Emulator made by Shim06 


A custom-designed, all-in-one PCB that transforms a powerful ESP32 microcontroller into a fully functional Nintendo Entertainment System (NES) emulator.

---

## 📖 About This Project

Rediscover the golden age of 8-bit gaming with Anemoia! This project is a hardware implementation of the incredible Anemoia-ESP32 software, designed to be a clean and portable retro gaming console.

The goal was to create a compact, all-in-one PCB that simplifies the building process and results in a professional-looking handheld. It integrates the ESP32, display, controls, audio, and SD card reader into a single board, perfect for placing in a custom 3D-printed case.

This hardware is specifically designed to run the firmware from the original **[Anemoia-ESP32 GitHub repository](https://github.com/Shim06/Anemoia-ESP32)**.

## ✨ Key Features

* **All-in-One Custom PCB:** No more messy wires! All components are integrated onto a single board.
* **ESP32-Powered:** Leverages the dual-core ESP32-WROOM-32 module for excellent performance.
* **Vibrant Display:** Uses a 2.0-inch ST7789 IPS display for crisp, colorful visuals.
* **Integrated Audio:** Includes a PAM8403 amplifier and a small speaker for authentic game sounds.
* **Built-in Game Storage:** A MicroSD card slot for loading your favorite NES game ROMs.
* **Full Game Controls:** Features a D-pad, A, B, Start, and Select buttons for a complete console experience.
* **Portable Design:** Compact form factor perfect for on-the-go gaming.

## 🛠️ Hardware Components

The custom PCB integrates the following key components:

* **Microcontroller:** ESP32-WROOM-32 Module
* **Display:** 2.0" 320x240 TFT IPS Display (ST7789) with built-in SPI SD card slot
* **Audio:** PAM8403 Audio Amplifier & 0.5W Speaker
* **Input:** 8 x 6x6mm Tactile Push Buttons
* **Storage:** MicroSD Card module

## 💾 Software & Firmware

This board is designed to be fully compatible with the original Anemoia-ESP32 firmware.

**The code can be found at the official repository:**
### **https://github.com/Shim06/Anemoia-ESP32**

### Flashing Instructions:
**Note : for advance build and upload (if you have to try it in Prototype board) go to the Shim06 Anemoia-ESP32 and He is the crater of the Software we are using in this pcb and here are common instruction**

## Getting Started

1. Upload the `Anemoia-ESP32.ino` program into the ESP32
2. Put .nes game roms inside the root of a microSD card
3. Insert the microSD card into the microSD card module
4. Power on the ESP32 and select a game from the file select menu

## How to build and upload

### Step 1

Either use `git clone https://github.com/Shim06/Anemoia-ESP32.git` on the command line to clone the repository or use Code → Download zip button and extract to get the files.

### Step 2
1. Download and install the Arduino IDE. 
2. In <b> File → Preferences → Additional boards manager URLs </b> , add:
```cmd
https://espressif.github.io/arduino-esp32/package_esp32_index.json
```
3. Download the ESP32 board support `v3.2.1` through <b> Tools → Board → Boards Manager </b>. 
> [!IMPORTANT]
> Make sure to download version 3.2.1, as different board versions may have worse performance.
4. Download the `SdFat` and `TFT_eSPI` libraries from <b> Tools → Manage Libraries </b>.

### Step 3 - Configure TFT_eSPI
The emulator uses a custom display configuration for the ST7789 display.
1. Navigate to your Arduino Libraries folder:
(Default location): `Documents/Arduino/libraries/TFT_eSPI`
2. Open `User_Setup_Select.h` in a text editor.
3. Comment out `#include <User_Setup.h>` and any other setup includes and add `<User_Setups/Anemoia-ST7789.h>`:
```C++
// #include <User_Setup.h>
#include <User_Setups/Anemoia-ST7789.h>
```
4. Copy the provided `Anemoia-ST7789.h` file from this repository into
`TFT_eSPI/User_Setups/`. Optionally, edit the `#define` pins as desired.
> [!NOTE]
> If using a screen with the ILI9341 driver, open `Anemoia-ST7789.h` in a text editor and comment out `#define ST7789_DRIVER` and uncomment `#define ILI9341_DRIVER`.
> ```C++
> // #define ST7789_DRIVER
> #define ILI9341_DRIVER
> ```

### Step 4 - Apply custom build flags
1. Locate your ESP32 Arduino platform directory. This is typically at:
```cmd
\Users\{username}\AppData\Local\Arduino15\packages\esp32\hardware\esp32\{version}\
```
2. Copy the `platform.txt` file from this repository and paste into that folder.
This file defines additional compiler flags and optimizations used by Anemoia-ESP32.
> [!WARNING]
> Backup your `platform.txt` file if you have your own custom settings already. 

### Step 5 - Upload
1. Connect your ESP32 via USB.
2. In the Arduino IDE, go to <b> Tools → Board </b> and select your ESP32 board (e.g., ESP32 Dev Module).
3. Click Upload or press `Ctrl+U` to build and flash the emulator. Optionally, edit the `#define` pins as desired.

Step 6 - **Prepare SD Card:** Format your MicroSD card to FAT32. Put .nes game roms inside the root of a microSD card

## Build Your Own PCB OR want to change or Use it any other project
Ypu can get the Gerber files from [releases](https://github.com/KrishP08/ESp-NES/releases) part

## 🙏 Credits and Acknowledgements

This project would not be possible without the incredible work done by **Shim06**.

* **Anemoia-ESP32 Software:** Huge thanks to **Shim06** for creating and maintaining the amazing emulator firmware. Please support the original project!

*Feel free to fork the repository and contribute!* 🚀
