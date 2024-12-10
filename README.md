# How I Install Arch Linux

A step-by-step guide to installing Arch Linux.

**P.S.** _You will need a bootable flash drive with at least 2GB of free space._

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
- From the menu, select the first option and wait for the loading process to complete.
- After loading, you’ll see the Arch Linux installation prompt.

### 2. Check Internet Connectivity

- **If using Ethernet:** Ethernet usually works out of the box, so you can skip this step.
- **If using Wi-Fi:**

  1. Test your connection by typing:

     ```bash
     ping google.com
     ```

     Press `Ctrl+C` to stop the test.

  2. If there’s no connection, set up Wi-Fi using the `iwd` tool:

     ```bash
     iwd
     device list
     station wlan0 get-networks
     station wlan0 connect [name_of_your_network]
     ```

     - Enter the Wi-Fi password when prompted.
     - Exit the `iwd` tool by typing:

       ```bash
       exit
       ```

  3. Verify the connection again:

     ```bash
     ping google.com
     ```

### 3. Start the Installation

1. Run the installation script:

   ```bash
   archinstall
   ```

2. Follow the prompts in the `archinstall` menu to configure and install Arch Linux:
   - Select your preferred language (English is recommended for simplicity).
   - Configure other options, such as disk partitioning, user accounts, and desktop environments.

---

## Notes

- For detailed troubleshooting and advanced configuration, refer to the [Arch Wiki](https://wiki.archlinux.org/).
