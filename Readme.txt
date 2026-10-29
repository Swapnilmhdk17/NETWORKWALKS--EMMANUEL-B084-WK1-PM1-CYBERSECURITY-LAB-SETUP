Table of Contents

[Step 1: Configure the NAT Network in VirtualBox](#step-1-configure-the-nat-network-in-virtualbox)
[Step 2: Create the Kali Linux Virtual Machine](#step-2-create-the-kali-linux-virtual-machine)
[Step 3: Configure Virtual Machine Settings](#step-3-configure-virtual-machine-settings)
[Step 4: Install Kali Linux](#step-4-install-kali-linux)
[Step 5: Post-Installation Checklist](#step-5-post-installation-checklist)

---

## 🛠️ Prerequisites

* *Hypervisor:* [Oracle VM VirtualBox](https://www.virtualBox.org/) (recommended version 7.x or newer).
* *OS Image:* Download the latest *Kali Linux Installer ISO* from the [official Kali Downloads page](https://www.kali.org/get-kali/).
* *Host Hardware Requirements:*
  * *RAM:* At least 4 GB (8 GB+ recommended).
  * *Storage:* At least 30 GB of free disk space.
  * *Processor:* Multi-core CPU with virtualization enabled (Intel VT-x or AMD-V).

---

## 🌐 Step 1: Configure the NAT Network in VirtualBox

Before creating the VM, set up a dedicated NAT Network so your VMs can communicate securely.

1. Open *VirtualBox*.
2. Go to *File* > *Preferences* (or *Tools* > *Network* depending on your version).
3. Select the *NAT Networks* tab and click the *+ (Create)* button.
4. Name your network (e.g., Kali-Lab-Net) and ensure the CIDR is set (default: 10.0.2.0/24).
5. Ensure *Supports DHCP* is checked.
6. Click *Apply* or *OK*.

---

## 💻 Step 2: Create the Kali Linux Virtual Machine

1. Click *New* in VirtualBox to create a new VM.
2. Enter the basic settings:
   * *Name:* Kali-Linux-VM
   * *Folder:* Choose your destination folder.
   * *ISO Image:* Select your downloaded Kali Linux installer ISO.
   * *Type:* Linux
   * *Version:* Debian (64-bit)
3. Click *Next*.

---

## ⚙️ Step 3: Configure Virtual Machine Settings

### Hardware Allocation
* *Base Memory (RAM):* Allocate at least *4096 MB (4 GB)*.
* *Processors (CPUs):* Allocate at least *2 CPU cores*.

### Storage Allocation
* *Hard Disk:* Select Create a virtual hard disk now.
* *Disk Size:* Allocate at least *30 GB* (Dynamic allocation is fine).
* Click *Finish*.

### Network Settings (Crucial Step)
1. Select your new VM and click *Settings*.
2. Navigate to the *Network* tab.
3. On *Adapter 1*:
   * Check *Enable Network Adapter*.
   * Attached to: *NAT Network*.
   * Name: Select the NAT network you created earlier (Kali-Lab-Net).
4. Click *OK*.

---

## 💿 Step 4: Install Kali Linux

1. Power on the VM by clicking *Start*.
2. In the boot menu, select *Graphical install* and press Enter.
3. Follow the on-screen prompts:
   * Choose your preferred language, location, and keyboard layout.
   * Set up your *Hostname* and *Domain name*.
   * Create a standard user account and password.
   * Set up your clock/timezone.
   * *Partition Disks:* Choose Guided - use entire disk and select the virtual disk. Complete the partition layout and write changes to disk.
   * *Software Selection:* Keep the default desktop environment (XFCE) and standard metapackages selected.
   * *GRUB Bootloader:* Install the GRUB bootloader to the primary drive.
4. Once installation completes, click *Continue* to reboot into your new Kali Linux system.