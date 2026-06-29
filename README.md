# [qemuTermux](https://github.com/blanckth/qemuTermux/)
Use QEMU in Termux as a full virtual machine and Deploy Any architecture OS and img and run without ROOT.
> ### Author : **`Salar Muhammadi`**.
###### Download and install [Termux](https://f-droid.org/en/packages/com.termux/), Copy and run the following command:
```bash
apt-get update -y && \
apt-get dist-upgrade -y && \
apt-get install qemu* -y && \
mkdir image && \
cd image;
```
> ###### Be Patient...
#### For Creating Virtual HDD Image do:
```bash
qemu-img create -f qcow2 hdd.img 10G
```
#### Running the installation iso with the newly made drive:
> [!NOTE]
> Replace `image.iso` with the iso that you want to install into the virtual hard drive.
```bash
qemu-system-x86_64 -smp 2 -net nic -net user -device AC97 -m 2048 -vnc 127.0.0.1:8 -cdrom image.iso -hda hdd.img
```
##### Now you can reach the Desktop with a VNC app like [AVNC](https://f-droid.org/en/packages/com.gaurav.avnc/) at localhost:5908
> #### For more Detail Options do :
```bash
qemu-system-x86_64 -h
```
#### Enjoy!
