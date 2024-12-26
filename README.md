# Project Portfolio: **Building a Pwnagotchi + Using Hashcat**

![pwnagotchi](https://github.com/user-attachments/assets/c091b575-1b63-42ea-8318-dd6a10207b98)

## Overview
This project demonstrates the process of creating a Pwnagotchi (a Raspberry Pi-powered AI that passively collects Wi-Fi handshake data) and utilizing **Hashcat** to crack the captured handshakes. The goal is to combine these two tools for security testing and educational purposes in wireless networks.

---

## 1. Introduction

In this project, we explore how to build and configure a **Pwnagotchi** device to capture Wi-Fi handshake data, and then use **Hashcat** to crack those captured handshakes. We discuss the tools individually and how they work together to test the security of Wi-Fi networks.

---

## 2. Pwnagotchi Setup

### Requirements
- **Raspberry Pi Zero W** (or compatible Raspberry Pi)
- **microSD card** (at least 8GB)
- **Pwnagotchi OS** (a custom Linux-based OS designed for Pwnagotchi)
- **Wi-Fi adapter** (compatible with monitor mode and packet injection)
- **Optional**: Display (e.g., ePaper) for real-time feedback


![image](https://github.com/user-attachments/assets/cee1c8e3-9bb2-4130-aba7-14df4474f87a)


### Installation Steps

1. **Download Pwnagotchi OS** from the [official repository](https://github.com/evilsocket/pwnagotchi).
2. **Flash the image** onto your microSD card using tools like Etcher.
3. **Configure the SD card** by editing the `config.toml` file for network settings and custom configurations.

### Configuration

Here’s how to adjust the configuration for your Pwnagotchi:

- Set up Wi-Fi to allow the device to connect to the internet for updates and AI training.
- Configure the display settings (if applicable).
- Enable logging to capture handshakes and store them for further analysis.

### Usage and Features

Once your Pwnagotchi is configured and booted, it will start passively collecting Wi-Fi handshakes while interacting with nearby networks. The AI inside the Pwnagotchi will improve its handshake collection efficiency over time. For more details, refer to the `pwnagotchi` section of the repository.

<img width="500" height="500" alt="Capture1" src="https://github.com/user-attachments/assets/05b05619-e7c6-4110-a5f0-bc18fca27f3b">

<br><br>
---

## 3. Using Hashcat for Cracking Handshakes

### Requirements
- A computer with **GPU support** (for faster cracking)
- **Hashcat** (a powerful password cracking tool)

### Setup Guide

1. **Install Hashcat** on your system using the instructions on the [official Hashcat website](https://hashcat.net/hashcat/).
2. **Prepare the handshake file** you obtained from your Pwnagotchi device. The file should have a `.hccapx` or `.cap` extension.
3. **Install required dependencies** (e.g., CUDA or OpenCL for GPU acceleration).

### Cracking Process

1. **Choose a wordlist**: For instance, use the `rockyou.txt` wordlist or a custom wordlist such as `networksniper!.txt`.
2. **Run Hashcat** with the following command:

    ```bash
    hashcat -m 2500 -a 0 captured_handshake.hccapx /path/to/wordlist.txt
    ```

   The `-m 2500` option specifies WPA2 cracking, and `-a 0` specifies a dictionary attack.

### Optimization Tips

- Use a **powerful GPU** to speed up the cracking process.
- Adjust the attack mode (e.g., **mask attacks** for more targeted cracking).
- Use **rules** to modify wordlist entries and improve cracking chances.

  
<img width="500" height="500" src="https://github.com/user-attachments/assets/521c2fd5-76d1-4206-952d-9fdc4e535e57">

---

## 4. Conclusion

By combining **Pwnagotchi** and **Hashcat**, this project demonstrates a fully automated approach to wireless security testing. The Pwnagotchi collects Wi-Fi handshakes passively, while Hashcat works to crack these handshakes using powerful algorithms. This project serves as both an educational tool and a demonstration of real-world cybersecurity testing.

---

## 6. Credits and Acknowledgements

- **Pwnagotchi**: [Official Repository](https://github.com/evilsocket/pwnagotchi)
- **Hashcat**: [Official Website](https://hashcat.net/hashcat/)

