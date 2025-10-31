# Bluetooth Jammer Using ESP32 (DevKit / NodeMCU)
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

- [**ESP32 DevKit V1 board**](https://www.amazon.in/dp/B07Q576VWZ)
- [**ESP32-S NodeMCU module**](https://www.amazon.in/dp/B081V735Y5)
- [**NRF24L01 Module**](https://www.amazon.in/dp/B07Q435TGK)
- [**TP4056 Li-Ion Battery Charger**](https://www.amazon.in/dp/B07QK1BY5P)
- [**3.7V LiPo Battery**](https://www.amazon.in/dp/B07DWYXJGP)
- 10uf 63v capacitor

## What is the NRF24L01 Module?

The **NRF24L01** is a low-power 2.4 GHz wireless transceiver module widely used for short-range communication. It supports simple data transmission between microcontrollers and is popular for DIY wireless projects, including remote controls and sensor networks.

## What is ESP32?

**ESP32** is a powerful, low-cost microcontroller featuring WiFi and Bluetooth connectivity, multiple SPI buses, and rich peripherals. It’s used extensively in IoT, robotics, and wireless projects due to its versatility and ease of programming.

## Dual NRF24L01 Setup (ESP32 DevKit / NodeMCU Wiring)

## ESP32 DevKit V1
