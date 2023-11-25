# i3wm-touchpad.conf
#This config file is to be used only in i3wm for touchpad taping 

Sure, here is a more user-friendly version of the text:

**i3wm-Touchpad-Gesture**

**Enhance your i3wm experience with touchpad gestures**

This guide provides two simple methods to enable touchpad gestures for your i3wm setup.

**Method 1: Cloning the Repository**

1. Navigate to the `X11` configuration directory:

```bash
cd /etc/X11/xorg.conf.d/
```

2. Clone the repository containing the touchpad gesture configuration file:

```bash
git clone https://github.com/theonlyanson/i3wm-touchpad-gesture.git
```

3. Alternatively, manually copy the contents of the `90-touchpad.conf` file from the repository and paste it into a new file named `90-touchpad.conf` in the `X11` configuration directory.

**Method 2: Manual Configuration**

1. Create the directory to store the configuration file:

```bash
sudo mkdir -p /etc/X11/xorg.conf.d
```

2. Create the configuration file using the `tee` command:

```bash
sudo tee <<'EOF' /etc/X11/xorg.conf.d/90-touchpad.conf 1> /dev/null
```

3. Paste the following content into the file:

```
Section "InputClass"
        Identifier "touchpad"
        MatchDevicePath "/dev/input/event*"
        Driver "libinput"

        Option "Tapping" "true"
        Option "TapButtonMap" "left middle right"

        Option "ThreeFingerSwipeLeft" "edge:left"
        Option "ThreeFingerSwipeRight" "edge:right"
EndSection
```

4. Save and close the file.

**Common Steps**

After completing either method, log out and log back in for the changes to take effect. Now you should be able to use touchpad gestures to control your i3wm desktop.
