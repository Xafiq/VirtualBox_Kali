# virtualbox_Debian_install

How to install Virtualbox on Debian
---

Installing VirtualBox on Debian is mostly smooth but expect some twists like missing dependencies or kernel issues. Just follow these steps, and you'll be running VMs in no time.

---

1️⃣ Download VirtualBox

VirtualBox official site:

[VirtualBox Downloads](https://www.virtualbox.org/wiki/Linux_Downloads)

Download the version for Debian-based distributions 

---

2️⃣ Update Your System

Before installing, ensure your system is up to date:

```bash
sudo apt-get update -y && sudo apt-get full-upgrade -y && sudo apt autoremove -y
```

---

3️⃣ Add VirtualBox Repository

To get the latest VirtualBox version, add the VirtualBox repository to your sources list:

```bash
echo "deb [arch=amd64] https://download.virtualbox.org/virtualbox/debian $(lsb_release -cs) contrib" | sudo tee /etc/apt/sources.list.d/virtualbox.list
```

Don't forget to add Oracle's public key to authenticate packages:

```bash
wget -q https://www.virtualbox.org/download/oracle_vbox_2016.asc -O- | sudo apt-key add -
wget -q https://www.virtualbox.org/download/oracle_vbox.asc -O- | sudo apt-key add -
```

---

4️⃣ Install VirtualBox

Now, install VirtualBox with a simple command:

```bash
sudo apt update
sudo apt install virtualbox-7.0
```

🛑 You may encounter dependency issues like:

```
Package 'libvpx5' is not installed.
Package 'libqt5opengl5' is missing.
```

But don’t worry, we’ll fix it!

---

5️⃣ Fix Dependency Problems

Let's install the missing packages manually. Here are a couple of common ones:

```bash
sudo apt install libvpx6
sudo apt install libqt5opengl5
```

If you get errors like "package not found," try downloading them from [pkgs.org](https://pkgs.org/) or download the `.deb` files from the Debian repository.

---

6️⃣ Install Linux Headers

VirtualBox needs your kernel headers to compile modules for your kernel version. Make sure you've got them:

```bash
sudo apt install linux-headers-$(uname -r)
```

If you still hit kernel issues, you might need to:

```bash
sudo dpkg-reconfigure virtualbox-dkms
```

This should help VirtualBox find and compile the right modules.

(for more information check: https://www.debian.org/doc/manuals/debian-kernel-handbook/ch-packaging.html)
---

7️⃣ Enable Virtualization in BIOS (If Needed)

If VirtualBox throws "VT-x/AMD-V hardware acceleration is not available," check your BIOS and enable virtualization (Intel VT or AMD-V).

---

8️⃣ Launch VirtualBox

Finally, launch VirtualBox:

```bash
virtualbox
```

---

Happy virtualizing!
