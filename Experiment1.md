# Experiment 1

Install WSL, VirtualBox, and create a virtual machine with Linux OS
(Ubuntu, Linux Mint, or Debian)

------------------------------------------------------------------------

## Part 1: Installing and Enabling WSL (Ubuntu) on Windows

Windows Subsystem for Linux (WSL) lets you run a GNU/Linux environment
directly on Windows.

### Step 1: Enable WSL and Virtualization Features

-   Open PowerShell as Administrator (Win + X → PowerShell Admin).
-   Run:

```{=html}
<!-- -->
```
    wsl --install -d ubuntu

This command: - Enables necessary components\
- Downloads Ubuntu\
- Prompts a reboot

Restart the computer when prompted.

### Step 2: Set Up Your Ubuntu Distribution

-   After reboot, Ubuntu window opens automatically.
-   If not, open it from the Start Menu.
-   Create a UNIX username and password.

### Troubleshooting

**If installation fails:** - Manually enable: - Virtual Machine
Platform - Windows Subsystem for Linux\
(In "Turn Windows features on or off", then reboot)

**Error: Required virtualization feature not installed** - Likely
hardware virtualization is disabled.

### Step 3: Enable Virtualization in BIOS/UEFI

-   Check using Task Manager → Performance → Virtualization: Enabled\
-   If disabled:
    -   Reboot and enter BIOS (F2/F10/F12/Del/Esc)
    -   Enable:
        -   Intel VT‑x\
        -   AMD‑V\
        -   SVM Mode\
    -   Save & exit

After enabling, run:

    wsl -l -v

to verify installation.

------------------------------------------------------------------------

## Part 2: Installing VirtualBox

VirtualBox allows running full virtual machines.

### Step 1: Download & Install

-   Download the Windows installer from the official VirtualBox site.
-   Run the `.exe` file.
-   Install with default settings.
-   Approve network and device permissions.

### Step 2 (Optional): Install Visual C++ Redistributable

-   Download VS 2019 Redistributable (`vc_redist.x64.exe`)
-   Install and reboot.

------------------------------------------------------------------------

## Part 3: Creating a Virtual Machine with Linux Mint

### Step 1: Download Linux Mint ISO

-   Visit the Linux Mint Cinnamon download page.
-   Download the 64-bit ISO file.

### Step 2: Create a Virtual Machine

1.  Open VirtualBox → New\
2.  Configure:
    -   **Name:** Linux Mint\
    -   **ISO Image:** Select downloaded ISO\
    -   **Type:** Linux\
    -   **Version:** Ubuntu (64‑bit)
3.  Allocate resources:
    -   RAM: **4GB+**
    -   CPUs: **2+**
4.  Create virtual disk:
    -   Type: VDI\
    -   Storage: Dynamically allocated\
    -   Size: **25GB+**

### Step 3: Install Linux Mint

-   Start the VM.
-   In the live environment, click **Install Linux Mint**.
-   Follow installation:
    -   Language, keyboard
    -   WiFi (optional)
    -   Installation type: *Erase disk and install Linux Mint* (affects
        ONLY virtual disk)
    -   Time zone
    -   User account creation

Restart when finished. Press Enter when asked to remove media.

### Step 4: Install Guest Additions (Recommended)

Improves resolution, clipboard sharing, and performance.

Inside the VM: 1. Devices → Insert Guest Additions CD image\
2. Open the CD\
3. Right‑click → Open in Terminal\
4. Run:

    sudo ./VBoxLinuxAdditions.run

Reboot the VM.

------------------------------------------------------------------------
