# How I Install Arch Linux

A step-by-step guide to installing Arch Linux.
P.S. **You will need a free bootable flash drive for 2GB+ space.**

---

## Prerequisites

1. **Download Arch Linux ISO**  
   Visit the [Arch Linux download page](https://archlinux.org/download) and download the latest ISO file.

2. **Create a Bootable USB**
   - Insert a flash drive into your computer.
   - Download [Rufus](https://rufus.ie/en/) and run the `.exe` file.
   - In Rufus:
     - Select your flash drive.
     - Choose the Arch Linux ISO file you downloaded.
     - Keep the default settings and press **START**.
   - Once the process finishes and shows **"Ready!"**, your bootable USB is prepared.

---

## Installation Steps

### 1. Boot from the USB

- Insert the bootable USB into the computer where you want to install Arch Linux.
- Access the boot menu (commonly accessed via `F2`, `F12`, or `Esc` during startup) and select the USB device.
- You'll see a menu similar to this:  
  ![Arch Linux Boot Menu](./resources/arch_menu.jpg)
- Choose the first option and wait for the loading process:  
  ![Arch Linux Loading Screen](./resources/arch_load.jpg)
- After loading, you’ll reach the ready-to-install prompt:  
  ![Arch Linux Ready Prompt](./resources/arch_ready.jpg)

---

### 2. Check Internet Connectivity

- **If using Ethernet:** You can skip this step since Ethernet usually works out of the box.
- **If using Wi-Fi:**
  - Test your connection by typing:
    ```bash
    ping google.com
    ```
  - If no connection, launch the interactive Wi-Fi setup tool:
    ```bash
    iwctl
    ```

---

### Notes

- For detailed troubleshooting and advanced configuration, refer to the [Arch Wiki](https://wiki.archlinux.org/).
