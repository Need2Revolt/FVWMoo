Coming soon™ please bear with me 🐻   
  
TODO:  
- clean config
- create separate repo for fvwm config only (and friends, conky urxvt)
- window borders
- wallpapers preview
- add screenshots
- create and publish the actual image  


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
  - MMB -> identify (show window infos)   
- Button 2:  
  - LMB -> reorder windows from top left (needs more space)   
  - RMB -> rearrange windows using all screen space    
  - MMB -> reorder windows from top left and roll them (needs more space)   
- Button 3:  
  - LMB -> send window to left virtual desktop  
  - RMB -> send window to right virtual desktop    
  - MMB -> send window to left virtual desktop and follow view    
- Button 4:  
  - LMB -> send window to foreground    
  - RMB -> send window to background    
  - MMB -> set sticky (always foreground)    
- Button 5:  
  - LMB -> maximize window 
  - RMB -> maximize window horizontally  
  - MMB -> maximise window vertically  

Scroll wheel up/down on window title will roll-up/unroll window (just try it, you'll understand)  

### Virtual desktops
The virtual desktop is organized in a 3x3 matrix. in the bottom right you'll see a navigator if you ever get lost. Hovering your cursor over the edges will move to the neighbouring virtual desktop and windows can be moved freely, even overlapping between virtual desktops.  

### Gestures
Gestures in FVWM are the main reason I choose this VM back in the day, they allow you to draw shapes with your mouse and have the VM react to it. You will not get a visual cue of the shape being drawn.  
Possible shapes follow a keypad style matrix:  
789  
456  
123  
so an L shape would be 74123  
Available gestures are:
- 258 (straight line down to up): open browser  
- 78963 (left then down): open terminal
- 78963 while holding shift key (left then down): open terminal with -su (you'll need to provide root password)
- 12369 (left then up: open file manager
- 74123 (down then left): open text editor


### Quake console
Having a quick accessible console window handy is always a good thing. Hitting Alt+F1 on your keyboard will bring up/hide a neat quake-like console, if you're old like me, you know what that is, otherwise just try it and you'll understand...

### Additional stuff
You'll get some system infos rendered directly on the desktop background via conky, unfortunately since it's running in a proot it's heavily limited in what it can display.  
There's a minimal task bar in the top portion of the screen, managed by tint2, it will display running windows and time and date

### Installed software
Terminal emulators: Konsole, urxvt  
Text editor: Kate  
Browser: Chromium  
Office automation: LibreOffice  
Development: gcc    
Anything else: install what you need. It's a Debian image under the hood... Most items in the menu won't work as I wanted to ship a minimal version and avoid cluttering everyone with my own choices...

# 4 Customisation
If you want to create your own user you'll need to copy .fvwm .concyrc and .X session to it's home folder; be sure to check execution permissions for the .fvwm/scripts/ folder's content.  
You'll also need to edit the startup script and replace the username there.
  
If you want to customise FVWM I suggest you look here: TODO  
General applications are defined as variables in .fvwm/config file, everything else is split logically in files under .fvwm/conf they might look like a lot, but you'll get used to them.  


# 5 Thank you
If you've read this far, thank you. I hope you'll enjoy this little critter and will customize it even further to suit your needs. The beauty of FVWM is just that and it gave me so much freedom and fun back in the day, that's why I decided to revive it. For archeological purposes here's the original post: [Cyb'](www.opendesktop.org/p/1018274)
