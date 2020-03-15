# 02-Tilpasning af din Ubuntu installation
* Cura og FreeCad og andre programmer som vi kommer til at bruge vil være at typen [AppImage](https://appimage.org/), disse programmer vil vi gerne installere så de kan opstartes fra Favoritter, der for vil en velformet biblitoks struktur være en god ide, herunder er vis den struktur vil benytte:
```bash
# biblitoks struktur
~/.local/  
~/.local/bin/*.AppImage    
~/.local/share/  
~/.local/share/applications/*.desktop  
~/.local/share/icons/*.png  
```
  * Opret manglende biblioteker for Appimages programmer
  * kopiere linier herunder en for en og indsætte den i Terminal vinduet:
```bash
# opret directory til dine bin filer
mkdir -p ~/.local/bin
mkdir -p ~/.local/share/icons
PATH="$PATH:$HOME/bin"
```
  * Vi vil også oprette bibliteks struktur for vores arbejdsfiler
  * kopiere linier herunder en for en og indsætte den i Terminal vinduet
```bash
# opret mappe til projecter
mkdir -p ~/Dokumenter/GitHub/
mkdir -p ~/Dokumenter/FreeCad/
mkdir -p ~/Dokumenter/ESP32/
mkdir -p ~/Dokumenter/Hypercube/
```
  * Insstallation af nyttige værktøjer, 
    * [git](https://git-scm.com/) -  [frit, distribueret versionsstyringssystem](https://da.wikipedia.org/wiki/Git)
    * pinta - [Pinta is a free, open source program for drawing and image editing.](https://pinta-project.com/pintaproject/pinta/)
    * geany - [Geany is a powerful, stable and lightweight programmer's text editor](https://www.geany.org/)
    * vlc - [VLC er en fri og open source multimedieafspiller](https://www.videolan.org/vlc/index.da.html)
    * printrun - [Printrun is a full suite of host interfaces for 3D printers and CNC, consisting of: Pronterface, Pronsole, or... Printcore, a standalone non-interactive G-Code host](https://www.pronterface.com/)
    * python3-distutils - [en python udvidelse som skal briges sammen med PlatformIO](https://platformio.org/)
  * kopiere linien herunder til dit Terminal vinduet
```bash
sudo apt install -y git pinta geany* vlc printrun python3-distutils 
```
  * I linux verden har man ikke adgang til serial-IO som standard bruger, derfor skal vores bruger tilknyttes til gruppen "dialout" så kopiere linien herunder til dit Terminal vinduet
```bash
# giv default bruger adgang til serial port
sudo usermod -a -G dialout $USER  
```
## Genstart Nu
  * Det vil nu være et godt tidspunkt at genstarte din pc, så kopiere linien herunder til dit Terminal vinduet: 
```bash
reboot
```