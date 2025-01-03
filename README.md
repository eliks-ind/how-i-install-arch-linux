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
- You'll see a menu similar to this:  
  ![Arch Linux Boot Menu](./resources/arch_menu.jpg)  
- Choose the first option and wait for the loading process:  
  ![Arch Linux Loading Screen](./resources/arch_load.jpg)  
- After loading, you’ll see the Arch Linux installation prompt:  
  ![Arch Linux Ready Prompt](./resources/arch_ready.jpg)

---

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
     iwctl
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

---

### 3. Start the Installation

1. Run the installation script:

   ```bash
   archinstall
   ```

2. Follow the steps in the Archinstall guided setup:

#### General Setup

- **Language:** Select your preferred language (English is recommended for simplicity).  
  ![Language Selection](./resources/arch_selected_language.png)
- **Mirror Region:** Choose the mirror region closest to you.  
  ![Mirror Selection](./resources/arch_selected_mirrors.png)  
  ![Mirror List](./resources/arch_mirror.png)
- **Locales:** Leave the default values.  
  ![Locale Selection](./resources/arch_selected_locales.png)

#### Disk Configuration

- **Partitioning Method:** Use "Best Effort Partition" (ext4 is recommended).  
  ![Partitioning Method](./resources/arch_selected_partitioning.png)  
  ![Use Best Effort Partition](./resources/arch_selected_use_best_effort_partition.png)
- **Drives:** Select the drive/drives where you want to install Arch Linux.  
  ![Disk Selection](./resources/arch_select_disk.png)
- **Separate /home Directory:** Optional (choose based on your preference).  
  ![Separate Home Directory](./resources/arch_separate_home_directory.png)
- **Disk Encryption:** Optional (skip if you don't want encryption).  
  ![Disk Encryption](./resources/arch_selected_disk_encryption.png)
- **Bootloader:** Ensure GRUB is selected.  
  ![Bootloader Selection](./resources/arch_selected_bootloader.png)

#### User Accounts

- Set a root password.  
  ![Root Password](./resources/arch_selected_root_password.png)
- Create a user account.  
  ![Add User](./resources/arch_add_user.png)  
  ![Enter Username](./resources/arch_enter_username.png)  
  ![Grant Sudo Privileges](./resources/arch_sudo.png)

#### Profiles and Packages

- **Profile Type:** Select "Minimal" (Desktop Environment can be installed later).  
  ![Profile Type](./resources/arch_selected_profile_type.png)  
  ![Minimal Profile](./resources/arch_selected_profile_type_minimal.png)
- **Audio Server:** Choose Pipewire (recommended for its modern features).  
  ![Audio Server](./resources/arch_audio_server.png)
- **Additional Packages:** Add packages like `neovim vim firefox git neofetch`. These can also be installed post-installation.  
  ![Additional Packages](./resources/arch_additional_packages.png)

#### Timezone and Networking

- **Timezone:** Select your local timezone.  
  ![Timezone Selection](./resources/arch_selected_timezone.png)
- **Network Interface:** Verify your network settings.  
  ![Network Interface](./resources/arch_network_interface.png)

#### Finalize Installation

- Review all settings.  
  ![Settings Review](./resources/arch_selected_install.png)
- Press **Install** (Note: Selected drives will be formatted, and all data will be lost).  
  ![Start Installation](./resources/arch_press_enter.png)  
  ![Countdown](./resources/arch_countdown.png)
- Wait for the installation to complete.

---

After it completes reboot the system by typing `reboot now` or `reboot 0` and boot to the existing OS. You can also remove the flash drive.

### 4. Install a Desktop Environment

-- Install yay

type to your terminal `git clone https://aur.archlinux.org/yay.git`

<!-- Once Arch Linux is installed, you can set up a Desktop Environment (DE). Refer to the [Arch Wiki](https://wiki.archlinux.org/) for detailed steps on installing your preferred DE. -->

---

## Notes

- For troubleshooting and advanced configurations, consult the [Arch Wiki](https://wiki.archlinux.org/).
