# Hypervisor & Kali VM Setup

## Choosing a Hypervisor

You can use either **VMware Workstation Pro** or **VirtualBox** for this setup. VirtualBox is a popular free option, but this guide primarily covers VMware.

---

## Part 1 - Installing VMware Workstation Pro

1. **Create a Broadcom account** at [profile.broadcom.com/web/registration](https://profile.broadcom.com/web/registration)

2. **Sign in** at [access.broadcom.com](https://access.broadcom.com/default/ui/v1/signin/)

3. **Navigate to Free Downloads** at [support.broadcom.com/group/ecx/free-downloads](https://support.broadcom.com/group/ecx/free-downloads)

4. **Select VMware Workstation Pro** from the list, or go directly to the [VMware Workstation Pro downloads page](https://support.broadcom.com/group/ecx/productdownloads?subfamily=VMware%20Workstation%20Pro&freeDownloads=true)

5. Select **VMware Workstation Pro 25H2 for Windows**, Release **25H2**

6. **Accept the Terms of Service** - you must open and check the ToS checkbox before the download button becomes active

<img width="1636" height="659" alt="OYsYUCIk74" src="https://github.com/user-attachments/assets/4a0a0ea4-09c7-4ddd-8da5-b1677d16c481" />


8. Fill out the **Trade Compliance and Download Conditions Form**, then click the final download button to get the installer

---

## Part 2 - Getting Kali Linux

You have two options, the pre-built VM is strongly recommended:

### Option A: Pre-Built Virtual Machine *(Recommended)*

Download the pre-built VM from [kali.org/get-kali/#kali-virtual-machines](https://www.kali.org/get-kali/#kali-virtual-machines).

<img width="1895" height="980" alt="OBZCK7eDMp" src="https://github.com/user-attachments/assets/26878786-20a2-4830-8168-f8f056c8fca6" />

Once downloaded:
1. Extract the archive
2. In VMware, go to **File → Open** and select the extracted folder

That's it, you can skip the manual installation steps below entirely.

### Option B: ISO Installation

Download the Kali ISO from the same page and follow the installation steps in Part 3.

---

## Part 3 — VM Installation (ISO Only)

> Skip this section if you used the pre-built VM.

#### Initial Setup

- **VMware:** Open the app, drag in the Kali ISO, click Continue, select **Linux → Other Linux 6.x**, then start the machine
- **VirtualBox:** Open VirtualBox, click **New**, name it something like "Kali", select the ISO, and start the machine

#### Installation Steps

When the installer boots, follow this sequence:

1. Select **Graphical Install**
2. Set **Hostname** to `kali`
3. Leave the **domain name** blank
4. Set **Full name, username, and password** to `kali` (or customize as you prefer)
5. Select **Central** time zone
6. Choose **"Use entire disk and set up LVM"**
7. Select **"All files in one partition"**
8. Click **Yes** on all confirmation prompts and enter `max` for the disk size

#### Software Selection

- **VMware:** Select only the **first two checkboxes**, leave everything else unchecked
- **VirtualBox:** Leave the defaults as-is (everything except GNOME & KDE should be checked)

---

## Part 4 - Post-Install Tips

- **Allocate more resources** - the defaults are very slow. Increase RAM and CPU cores in your VM settings (can be done after setup is complete)
- **Boot errors after install** - if you hit a boot error on first launch, simply power off the VM and restart it; this usually resolves the issue
