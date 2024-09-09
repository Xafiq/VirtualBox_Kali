# virtualbox_Debian_install

How to install Virtualbox on Debian
---

1_Download VirtualBox

[VirtualBox.org](https://www.virtualbox.org/wiki/Linux_Downloads)

Download Debian-based distributions 

---

2_Update Your System

```bash
sudo apt-get update -y && sudo apt-get full-upgrade -y && sudo apt autoremove -y
```

---

3_Install VirtualBox

```bash
sudo apt install virtualbox
```

4_Enable Virtualization in BIOS (If Needed)

If VirtualBox throws "VT-x/AMD-V hardware acceleration is not available," check your BIOS and enable virtualization (Intel VT or AMD-V).

---

5_Launch VirtualBox

Finally, launch VirtualBox:

```bash
virtualbox
```

---

#Xafiq
