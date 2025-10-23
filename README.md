# ESP-NES - A Custom PCB for the ESP32 NES Emulator


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
* **Storage:** MicroSD Card Slot (on the display module)
* **Power:** [e.g., TP4056 charging module, LiPo battery, power switch - *mention your power setup here*]

## 💾 Software & Firmware

This board is designed to be fully compatible with the original Anemoia-ESP32 firmware.

**The code can be found at the official repository:**
### **https://github.com/Shim06/Anemoia-ESP32**

### Flashing Instructions:

1.  **Clone the Repository:**
    ```bash
    git clone [https://github.com/Shim06/Anemoia-ESP32.git](https://github.com/Shim06/Anemoia-ESP32.git)
    ```
2.  **Open in PlatformIO:** Open the cloned folder in VS Code with the PlatformIO extension.
3.  **Configure Pins (If Necessary):** The pin definitions in the firmware should match the connections on this PCB. If you made any changes, update them in the source code.
4.  **Build & Upload:** Connect the ESP32 to your computer via USB and upload the firmware.
5.  **Prepare SD Card:** Format your MicroSD card to FAT32. Create a folder named `roms` in the root directory and copy your NES game files (with a `.nes` extension) into it.

## 🚀 Build Your Own

Interested in building your own Anemoia Handheld?

1.  **Get the PCB:** Download the Gerber files from this [releases](https://github.com/KrishP08/ESp-NES/releases) and get them manufactured by a service like JLCPCB or PCBWay.
2.  **Source the Components:** Refer to the Bill of Materials (BOM) file for a complete list of parts.
3.  **Solder Everything:** Solder all the components onto the PCB. It's recommended to start with the smallest surface-mount components first.
4.  **Flash the Firmware:** Follow the software instructions above to flash the Anemoia emulator.
5.  **3D Print a Case (Optional):** Download and print the case files for a finished look.
6.  **Assemble and Play:** Put everything together, load up your SD card, and enjoy retro gaming!

## 🙏 Credits and Acknowledgements

This project would not be possible without the incredible work done by **Shim06**.

* **Anemoia-ESP32 Software:** Huge thanks to **Shim06** for creating and maintaining the amazing emulator firmware. Please support the original project!

## 📜 License

This hardware project is open-source. Please check the `LICENSE` file for more details.
