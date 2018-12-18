
# listing vms

## get a list of running VMs

```
VBoxManage list runningvms
```

```
"win10" {2aa5d69d-e8f3-4b6f-a3a3-364b2f00971e}
```

```
VBoxManage list -l runningvms
```

```
Name:            win10
Groups:          /
Guest OS:        Windows 10 (64-bit)
UUID:            2aa5d69d-e8f3-4b6f-a3a3-364b2f00971e
.
.
.
Hardware UUID:   2aa5d69d-e8f3-4b6f-a3a3-364b2f00971e
Memory size:     8048MB
Page Fusion:     off
VRAM size:       256MB
.
.
```

## if its not running, how to start

```
# headless is key, if doing from cmdline
VBoxManage startvm win10 --type headless
```

## if its *ON*, but not working

Requires debugging!

```
# nudge a soft poweroff
VBoxManage controlvm win10 acpipowerbutton
# if it does not work, a hard power off
VBoxManage controlvm win10 poweroff

## then switch if back on
VBoxManage startvm win10 --type headless
```


```
```

Last time the VM became inaccessible

```
# had to copy over this file...
cp win10.vbox-prev win10.vbox
```

# FAQS

## Q after just a few minutes of successfull start, the machine becomes inaccisible

```
We couldn't connect to the remote PC. Make sure the PC is turned on and connected to the network, and that remote access is enabled.

Error code: 0x204
```

**A**: some say, this may be related to a security vulnerability.

https://social.technet.microsoft.com/Forums/Lync/en-US/9017ab7e-b406-4e3a-816e-8a148c394d8c/microsoft-remote-desktop-80-mac-os-x-cant-connect-to-a-windows-10-pc?forum=winRDc


2. this could even be related to lack of space on the device!!!

cp: error writing 'win10.vbox-prev_bak': No space left on device






