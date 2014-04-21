Elantech mouse fix
==================

This directory contains a fixed kernel module for the Elanteck trackpads which have
no right click in Linux. To install the fix issue the following commands:

```bash
sudo mv psmouse-elantech-v7right /usr/src/
sudo dkms install -m psmouse -v elantech-v7right
sudo modprobe -r psmouse
sudo modprobe psmouse
```

The right click will now work immediately without a restart.

Unfortunately the fixed module will be lost when installing a new kernel or updating the
existing kernel. Thus, it might be helpful to put the las three lines in a bash script 
(without) sudo, which can be called via sudo after a new kernel has been installed.
