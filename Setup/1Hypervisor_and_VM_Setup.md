Hypervisor and Kali VM Setup
---
You can choose any hypervisor, some people like [VirtualBox](https://www.virtualbox.org/wiki/Downloads) better, however, for this tutorial we will be using VMWare, as that is what I personally use. 

1. Register a Broadcom account https://profile.broadcom.com/web/registration
2. Login to your Broadcom account https://access.broadcom.com/default/ui/v1/signin/
3. Browse to https://support.broadcom.com/group/ecx/free-downloads
4. Select VMWare Workstation Pro at the bottom, or browse to https://support.broadcom.com/group/ecx/productdownloads?subfamily=VMware%20Workstation%20Pro&freeDownloads=true
5. Select VMWare Workstation Pro 25H2 for Windows and Release 25H2
6. Note: Before being able to press the download button, you must open the terms of service, and then check the box as shown in the screenshot below
<img width="1636" height="659" alt="OYsYUCIk74" src="https://github.com/user-attachments/assets/c1537acf-46fc-460a-9296-d9d74729d4bf" />

8. It will then have you fill out a Trade Compliance and Download Conditions Form, after that you can finally press the download button for the final time, and you will get the installer.
---

8. Download the Kali ISO or, what I use, just the pre-built virtual machine. If you use the pre-built virtual machine you can skip through these next steps and just extract and open your virtual machine in VMWare (you literally just click File > Open > foldername of what you just extracted) https://www.kali.org/get-kali/#kali-virtual-machines
<img width="1895" height="980" alt="OBZCK7eDMp" src="https://github.com/user-attachments/assets/4fb434ea-2d9b-4f4c-a4bc-f5fe51b60450" />


10. Follow the instructions for the hypervisor you downloaded
    - VMWare:
        1. Open the app, drag in the Kali ISO, click continue, then choose Linux -> Other Linux 6.x, and start the machine
    - VirtualBox:
        1. Open VirtualBox, click New, give it a name (something like "Kali"), select the Kali ISO image from your downloads, and start the machine
11. Configuring the VM:
    - Choose Graphical Install
    - Hostname: "kali"
    - Leave the domain name blank
    - Fullname, username & password: "kali" or obviously setup as you wish
    - Choose central time
    - Choose "use entire desk and set up lvm"
    - Select "all files in one partition"
    - Click yes for all options, and type in max for the size
    - Software selection
        - VMWare:
            1. Select only the first two checkmarks, everything else should be left unchecked.
        - VirtualBox:
            1. Don't change anything on the software selection screen, by default everything except GNOME & KDE should be checked
    - Make sure to add more memory and CPU cores so it runs faster, the default is very slow! (This can be done after the machine is fully set up)
    - If you encounter a boot error after everything has installed, powering off the VM and restarting it seems to resolve the issue

If you do the pre-built virtual machine you most likely won't have as many installation steps or problems as compared to using the ISO, but the instructions are still provided above for the ISO.
