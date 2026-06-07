Coming soon™ please bear with me 🐻 

# FVWMoo
Custom FVWM config running on an Android proot image. Minimalistic and performance oriented, interaction is heavily mouse based.

It's meant to be a lightweight Linux image to be used whenever you can't or don't want to carry a full laptop with you. It requires a mouse and a keyboard to be used, so you'll either have to carry those or scavenge them in your surroundings.

Be sure to read section #3 or you will likely be lost inside the environment (or won't appreciate all it's features).

# 1 Installing Termux
Install the newest version from Termux's GitHub page as the one in the Google Play store is outdated. You can find it [here](https://github.com/termux/termux-app/releases)
<br>
Once downloaded and installed, open it and run the following commands: 
```
pkg update
pkg upgrade
pkg install x11-repo
pkg install termux-x11-nightly
pkg install tur-repo
pkg install pulseaudio
pkg install proot-distro
pkg install wget
pkg install git
pkg install virglrenderer-mesa-zink
termux-setup-storage
```
This will install everything you need to run a proot image, including audio, X11, HW acceleration; some utils that we'll need later and will enable Termux to access your device's storage.

# 2 Importing the image 

# 3 Features and how to use them
The desktop is optimised for mouse interaction and minimal intrusion.

### Menu
Right mouse button (RMB from now on) anywhere on the desktop will bring up the menu.

### Window title bar
Windows will have a vertical title bar on the left instead of top, and will have 5 buttons. Each button reacts to left right and middle mouse clicks differently.  
Starting form the bottom and going up:  
- Button 1:  
  - LMB -> close window  
  - RMB -> iconify window  
  - MMB ->  
- Button 2:  
  - LMB ->  
  - RMB ->  
  - MMB ->  
- Button 3:  
  - LMB ->  
  - RMB ->  
  - MMB ->  
- Button 4:  
  - LMB ->  
  - RMB ->  
  - MMB ->  
- Button 5:  
  - LMB ->  
  - RMB ->  
  - MMB ->  

Scroll wheel up/down on window title will roll-up/unroll window (just try it, you'll understand)  

### Virtual desktops
The virtual desktop is organized in a 3x3 matrix. in the bottom right you'll see a navigator if you ever get lost. Hovering your cursor over the edges will move to the neighbouring virtual desktop and windows can be moved freely, even overlapping between virtual desktops.  

### Gestures

### Quake console
Having a quick accessible console window handy is always a good thing. Hitting Alt+F1 on your keyboard will bring up/hide a neat quake-like console, if you're old like me, you know what that is, otherwise just try it and you'll understand...

### Additional stuff
You'll get some system infos rendered directly on the desktop background via conky, unfortunately since it's running in a proot it's heavily limited in what it can display.  
There's a minimal task bar in the top portion of the screen, managed by tint2, it will display running windows and time and date

### Installed software
Terminal emulators: konsole, urxvt  
Text editor: Kate  
Browser: chromium  
Office automation: LibreOffice  
Development: gcc  
Anything else: install what you need. It's a Debian image under the hood...

# 4 Customisation
