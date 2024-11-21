# UI + Desktop

### X11
```
  X11 - X Window System is a software stack used to display text and graphics on a screen

  hostname:displaynumber.screennumber

  /etc/X11/xorg.conf or /etc/X11/xorg.conf.d/
    InputDevice
    InputClass          use to configure class of hardware devices
    Monitor             describes physical monitor used and connected
    Device              describes physical video card used
    Screen              ties Monitor and Device sections together
    ServerLayout        groups all sections into 1 X Window system interface
  
xdpyinfo #display info about running X server instance

sudo Xorg -configure    #generate X config file
```

### Graphical Desktops
```
  Gnome, KDE, Xfce

  Virtual Network Computing (VNC)
    # Remote Frame Buffer protocol (RFB)
    # ~/ . vnc/xstartup
    # TCP port 5900, + for each new sessions
```
