# Bluetooth Jammer Using ESP32 (DevKit / NodeMCU)

<p align="center">
<a href="#"><img title="device" src="device.jpg"></a>
</p>
<p align="center">
<a href="https://github.com/vxnuprasad"><img title="Author" src="https://img.shields.io/badge/Author-Vishnu-yellow.svg?style=for-the-badge&logo=github"></a>
<a href="[https://interncrafters.netlify.app/](https://vxnuprasad.github.io/)"><img title="Website" src="https://img.shields.io/badge/Website-vxnuprasad-green.svg?style=for-the-badge&logo=sites"></a>
</p>

## Disclaimer
This project is **strictly for educational and authorized penetration testing purposes only**. Wireless jamming devices are illegal in many countries when used without permission and can disrupt critical communications. I assume no responsibility for misuse or damage caused by this device. Use responsibly and legally, in controlled test environments only.

## **How the Jammer Works**

Bluetooth devices don’t just talk on one fixed frequency. Instead, they use a smart technique called **Frequency-Hopping Spread Spectrum (FHSS)**. This means they quickly jump between many different frequencies—sometimes hundreds or thousands of times every second—across the 2.4 GHz band.

### **Why do they do this?**

 *Imagine trying to have a conversation at a noisy party. To avoid interference and be heard clearly, you keep moving to different quieter spots in the room. Bluetooth does the same thing by hopping to different “channels” to find a clear path for communication.*

 ## What Is This “Noise” That the Jammer Sends?

In the context of Bluetooth jamming, **“noise” means random radio signals that carry no useful information** — just static, nonsense, or “junk data” flooded across Bluetooth’s frequencies.

*Think of it like trying to have a conversation on a walkie-talkie while someone else nearby is shouting random gibberish loudly across all channels. That shouting is “noise” drowning out the normal conversation.*

## Product Links

- [**ESP32 DevKit V1 board**]([https://www.amazon.in/dp/B07Q576VWZ](https://robu.in/product/esp32-38pin-development-board-wifibluetooth-ultra-low-power-consumption-dual-core/))
- [**ESP32-S NodeMCU module**]([https://www.amazon.in/dp/B081V735Y5](https://robu.in/product/esp32-38pin-development-board-wifibluetooth-ultra-low-power-consumption-dual-core/))
- [**NRF24L01 Module**]([https://www.amazon.in/dp/B07Q435TGK](https://robu.in/product/2-4ghz-nrf24l01palna-sma-antenna-wireless-transceiver-communication-module-1km/))
- [**TP4056 Li-Ion Battery Charger**]([https://www.amazon.in/dp/B07QK1BY5P](https://robu.in/product/tp4056-1a-li-ion-lithium-battery-charging-module-mini-usb/))
- [**3.7V LiPo Battery**]([https://www.amazon.in/dp/B07DWYXJGP](https://robu.in/product/450mah-pcm-protected-micro-li-po-battery/))
- [**10uf 63v capacitor**]([https://robu.in/product/10uf-63v-electrolytic-capacitor-pack-of-10/))

## What is the NRF24L01 Module?

The **NRF24L01** is a low-power 2.4 GHz wireless transceiver module widely used for short-range communication. It supports simple data transmission between microcontrollers and is popular for DIY wireless projects, including remote controls and sensor networks.

## What is ESP32?

**ESP32** is a powerful, low-cost microcontroller featuring WiFi and Bluetooth connectivity, multiple SPI buses, and rich peripherals. It’s used extensively in IoT, robotics, and wireless projects due to its versatility and ease of programming.

## Dual NRF24L01 Setup (ESP32 DevKit / NodeMCU Wiring)
<a href="#"><img title="wiring" src="Wiring.jpg"></a>

Both NRF24 modules’ VCC to 3.3V and GND to ground, with capacitors for power stability.

**For a single NRF24L01 module setup: You may use either the VSPI or HSPI bus depending on your preference and the ESP32 variant you have. Simply connect the NRF24L01 module to one SPI bus (default or secondary) using the corresponding SPI pins and assign CE and CSN to any convenient GPIO pins.**

## What is SPI? (Serial Peripheral Interface)

SPI, or Serial Peripheral Interface, is like a conversation between your microcontroller (ESP32) and other electronic devices (like sensors or wireless radios). Imagine SPI as a fast, coordinated walkie-talkie system with four main wires:

- **SCK (Clock):** This is the “beep” telling everyone when to talk.
- **MOSI (Master Out Slave In):** This wire carries data from the microcontroller to the device.
- **MISO (Master In Slave Out):** This wire carries data from the device back to the microcontroller.
- **CSN (Chip Select):** This pin acts like a microphone button, telling a specific device it’s time to listen or talk.

Because SPI is synchronized by the clock signal, the data travels quickly and accurately. It’s one of the fastest ways microcontrollers send and receive data from components.

## What are VSPI and HSPI on the ESP32?

The ESP32 has **two hardware SPI controllers**, meaning it can hold two separate SPI “conversations” at the same time.

- **VSPI (Default SPI):** The first SPI bus, usually connected to default pins like GPIO18 (clock), GPIO19 (MISO), and GPIO23 (MOSI).
- **HSPI (Secondary SPI):** The second SPI bus, usually connected to pins GPIO14 (clock), GPIO12 (MISO), and GPIO13 (MOSI).

Think of it as having two walkie-talkie channels—you can talk to one group on channel 1 (VSPI) and another on channel 2 (HSPI) without mixing up conversations.

This is super helpful when you want to use **two devices that both talk SPI** (like your two NRF24L01 radios), so both can communicate without interference.

## Software Setup & Flashing

1. **Wire your NRF24L01 modules** to the ESP32 according to the wiring diagrams provided earlier.
2. Open the Bluetooth Jammer Web Flasher in a Chrome or Edge browser:
    
    [**https://smoochiee.github.io/Bluetooth-jammer-esp32/flash1**](https://smoochiee.github.io/Bluetooth-jammer-esp32/flash1)
    
3. From the hardware options, select **“Dual Nrf24l01 Vspi and Hspi pins”** if you have two modules connected on both SPI buses.
4. Connect your ESP32 board to your PC via USB, then select the corresponding **COM port** in the flasher interface.
5. Choose the firmware version you want to install — typically the latest BLE1 version.
6. Click **Install** and wait patiently while the firmware uploads. This process may take a few minutes.
7. After successful flashing, press the **reset (EN)** button on your ESP32 development board.
8. Your Bluetooth jammer is now running and will start transmitting interference automatically.

## Step-by-Step Wiring Instructions:

1. **Battery to TP4056:**
    - Connect the **positive (+)** battery lead to the **B+** terminal on the TP4056 board.
    - Connect the **negative (−)** battery lead to the **B−** terminal on the TP4056 board.
2. **TP4056 Power Output:**
    - Use the **OUT+** and **OUT−** terminals on the TP4056 as the battery output to power your system.
    - **DO NOT** draw power directly from B+ or B−; use OUT pins for the load.
3. **Voltage Regulation:**
    - Connect the **OUT+** to the **input (+) pin** of your 3.3V regulator module.
    - Connect **OUT−** to the ground (GND) of your regulator.
    - The **3.3V output pin** of the regulator feeds into the **3.3V power pin** on your ESP32 and both NRF24L01 modules.
4. **Capacitor Placement:**
    - Place the **10µF 63V electrolytic capacitor** **between VCC (3.3V)** and **GND** pins **right next to each NRF24L01 module’s power pins**.
    - This capacitor stabilizes the power supply and helps prevent voltage dips that can cause the radios to malfunction.

 ## Find Me On:
[![LinkedIn](https://img.shields.io/badge/LinkedIn-VishnuPrasad-blue?style=for-the-badge&logo=LinkedIn)](https://www.linkedin.com/in/vxnuprasad)  
[![Instagram](https://img.shields.io/badge/IG-%40__.v.shnu-red?style=for-the-badge&logo=instagram)](https://www.instagram.com/__.v.shnu/)  


