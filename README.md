# Ubuntu 18.04.4 Setup
# Basis installation af Ubuntu
## NB !!! Dette vil slette alt på din hardisk !!!!!!!
* Hent Ubuntu Desktop 18.04.4 LTS [Download Ubuntu Desktop](https://ubuntu.com/download/desktop)
  * køren standard installation
    * Vælg :
      * Velkommen : 
        * Dansk installation
        * Installer ubuntu
      * Tastaturlayout:
        * Dansk
        * Dansk - Dansk (win-taster)
      * Opdateringer og andre programmer
        * Nomal Installation
        * Hent opdateringer mens Ubuntu installeres
        * Installer tredjepartsprogrammer til grafik og wi-fi-hardware og ydeliger mediaformater
      * Installationstype
        * Slet disk og installer Ubuntu
        * Installer Nu
      * Hvor befinder du dig
        * Copenhagen
      * Hvem er du
        * Dit navn
        * Navnet på din computer (det er det navn du ønsker at kalde din computer, hold det kort)
        * Vælg et brugernavn (måske dine initialer)
        * Vælg en adgangskode
      * vent til installationen er færdig
## Opdatering af din Ubuntu Installation
* login og start et Terminal vindue med tast kombinationen [Ctrl]+[Alt]+T
  * opdater din installation til nyeste version, ved at kopiere linier herunder en for en og indsætte den i Terminal vinduet, når du bliver spurt om password, er det det du valgte under installationen.
```bash
# opdater din linux
sudo apt update
sudo apt full-upgrade -y
sudo apt autoremove -y
```
## Tilpasning af din Ubuntu installation
* Cura og FreeCad og andre programmer som vi kommer til at bruge vil vaær at typen [AppImage](https://appimage.org/), disse programmer vil vi gerne installere så dekan opstartes fra Favoritter, der for vil en velformet biblitoks struktur være en god ide
```
~/.local/  
~/.local/bin/*.AppImage    
~/.local/share/  
~/.local/share/applications/*.desktop  
~/.local/share/icons/*.png  
```
  * Opret manglende biblioteker for Appimages programmer
```bash
# opret directory til dine bin filer
mkdir -p ~/.local/bin
mkdir -p ~/.local/share/icons
PATH="$PATH:$HOME/bin"
```
  * Vi vil også oprette bibliteks struktur for vores arbejdsfiler
```bash
# opret mappe til projecter
mkdir -p ~/Dokumenter/GitHub/
mkdir -p ~/Dokumenter/FreeCad/
mkdir -p ~/Dokumenter/ESP32/
mkdir -p ~/Dokumenter/Hypercube/
```
  * Insstallation sf nyttige værktøjer
```bash
sudo apt install -y git pinta geany* vlc python3-distutils printrun
```
  * Vi får brug for at kunne tilgå vores seriale porte 
```bash
# giv default bruger adgang til serial port
sudo usermod -a -G dialout $USER  
```
## Genstart Nu
  * Det vil nu være et godt tidspunkt at genstarte sin pc skriv 
```bash
reboot
```
# Tilpas Mozilla-Firefox
* Start nu Firefox 
  * indtast i adresselinien "google.dk" og tast [Enter]
* Klik på Abn menu iconen
    * Vælg indstillinger
      * Klik Generelt
        * Filer og programmer
          * Filhentning
            * Vælg "Spørg mig altid, hvor filer skal gemmes"
      * Klik Hjem
        * Sæt "Startside og nye vinduer" til "Tilpassede URL'er..."
          * Vælg "Andvend nuværende side"
* Luk Indstillinger
* Abn nyt faneblad
  * Skriv i adresselinien https://github.com/mstedet
    * Klik Stjernen 
      * Sæt Mappe: til "Bogmærkelinje"
        * klik Færdig
  * Skriv i adresselinien https://github.com/sekt1953
    * Klik Stjernen 
      * Sæt Mappen til "Bogmærkelinje"
        * klik Færdig
  * 
# AppImages programmer
## Filstruktur for AppImages Programmer
```
  ~/.local/bin
  ~/.local/share/applications
  ~/.local/Share/icons
```  
* Appimages filerne placeres i "~/.local/bin" mappen  
* .desktop filerne placeres i "~/.local/share/applications", desktop filen er den fil der linker Appimages programmet og des icon sammen, desktop filer er også den fil som vi linker til fra favoritter.
* Ikoner til Appimages programmerne placeres her.
## Hent Iconer til AppImages programmer
### Ultimaker_Cura
* Skriv i adresselinien https://en.wikipedia.org/wiki/Cura_(software) 
  * Højre klik Cura Icon 
    * Vælg "Gem billed som..."
      * Klik Hjem i Filer
        * Tast [Ctrl]+H for at se skjulte mapper
          * Vælg mappen "~/.local/share/icons/
            * Ændre navn til "Ultimaker_Cura.png"
              * klik "Gem"
### FreeCad
* Skriv i adresselinien https://www.norwegiancreations.com/2016/02/a-quick-look-at-freecad/
  * Højre klik FreeCad Icon 
    * Vælg "Gem billed som..."
      * Klik Hjem i Filer
        * Tast [Ctrl]+H for at se skjulte mapper
          * Vælg mappen "~/.local/share/icons/
            * Ændre navn til "FreeCad_0.19.png"
              * klik "Gem"
## Opret desktop filer for AppImages filer
#### Ultimaker_Cura-4.5.0
* Åbn Terminal vindue med [Ctrl]+[Alt]+T,  Åbn nu teksbehandlinge nano:

```bash
nano ~/.local/share/applications/Ultimaker_Cura-4.5.0.desktop
```
* Indsæt nu følgende:
```bash
[Desktop Entry]
Type=Application
Name=Ultimaker_Cura-4.5.0.desktop
Name[da_DK]=Ultimaker_Cura-4.5.0.desktop
GenericName=3D Slicer Software for 3D Printers
GenericName[da_DK]=3D Slicer Software
Comment=Ultimaker_Cura-4.5.0
Icon=220px-Logo_for_Cura_Software.png
Exec=Ultimaker_Cura-4.5.0.AppImage
Terminal=false
MimeType=
Categories=Graphics;2DGraphics;3DGraphics;RasterGraphics;GTK;
StartupNotify=true
```
  * Tast [Ctrl]+X for afslutte derefter [J] & [Enter] for at gemme 

#### FreeCAD_0.19-19955-Linux-Conda_glibc2.12-x86_64.AppImage
* Åbn Terminal vindue [Ctrl]+[Alt]+T og skriv følgende:

```bash
nano ~/.local/share/applications/FreeCAD_0.19-19955-Linux-Conda_glibc2.12-x86_64.desktop
```
* Indsæt nu følgende:
```bash
[Desktop Entry]
Type=Application
Name=FreeCAD_0.19-19955-Linux-Conda_glibc2.12-x86_64.App
Name[da_DK]=FreeCAD_0.19-19955-Linux-Conda_glibc2.12-x86_64.desktop
GenericName[da_DK]=CAD-program
Comment=FreeCAD_0.19-19955-Linux-Conda_glibc2.12-x86_64
Icon=2000px-FreeCAD-logo.svg_-300x300.png
Exec=FreeCAD_0.19-19955-Linux-Conda_glibc2.12-x86_64.AppImage
Terminal=false
MimeType=application/x-extension-fcstd;
Categories=Graphics;Science;Engineering;
StartupNotify=true
```
  * Tast [Ctrl]+X for afslutte derefter [J] & [Enter] for at gemme 

### Hent Appimages filer
#### Ultimaker_Cura-4.5.0
* Åbn Firefox
  * Skriv adressen https://ultimaker.com/software/ultimaker-cura
    * Klik "Download for free"
      * Vælg "Ultimaker Cura 4.5 - Linux 64 bit"
        * Klik "Download Now"
          * Hvad skal Firefox gøre med denne fil? - Gem fil
            * Vælg mappen "~/.local/bin"
              * Klik "Gem"

### FreeCAD_0.19-19955
* Åbn Firefox
  * Skriv adressen https://github.com/FreeCAD/FreeCAD/releases/tag/0.19_pre
    * Rull ned til "Development versions" 
      * Klik "FreeCAD releases page."
        * Rull ned til Asset 12
          * Klik "FreeCAD_0.19-19955-Linux-Conda_glibc2.12-x86_64.AppImage"
            * Hvad skal Firefox gøre med denne fil? - Gem fil
              * Vælg mappen "~/.local/bin"
                * Klik "Gem"
* Luk Firefox når filerne er hentet

## Klargør Appimages filern for drift
### Tilpas rettigheder, tillad kørsel af filerne som et program
* Åbn Terminal vindue [Ctrl]+[Alt]+T
```bash
cd ~/.local/bin
chmod +x Ultimaker_Cura-4.5.0.AppImage
chmod +x FreeCAD_0.19-19955-Linux-Conda_glibc2.12-x86_64.AppImage

cd ~/.local/share/applications
chmod +x Ultimaker_Cura-4.5.0.desktop
chmod +x FreeCAD_0.19-19955-Linux-Conda_glibc2.12-x86_64.desktop
```
* luk Terminal vindue
### Åbn Filer og test start FreeCad & Cura
* Klik på Filer 
  * Klik Hjem
    * Tast [Ctrl]+ H for at vise skjulte filer
      * Double Klik - .local 
        * Double Klik - bin
          * Højre Klik FreeCAD_0.19-19955-Linux-Conda_glibc2.12-x86_64.AppImage
            * Vælg Kør
              * Luk programmet igen
          * Højre Klik Ultimaker_Cura-4.5.0.AppImage
            * Vælg Kør
              * Klik Get started
                * Klik Agree
                * Klik Next
                * Klik Next
                * Vælg Add a non-networked printer
                * Klik Wanhao
                * Vælg Wanhao Duplicator 9
                * Klik Next
                * Klik Finish
                * Luk programmet igen
    * Klik .local
      * Double Klik - share
        * Double Klik - applications
          * Højre Klik - FreeCAD_0.19-19955-Linux-Conda_glibc2.12-x86_64.desktop
            * Klik Åbn
              * Vælg - Hav tillid til og kør 
              * Luk programmet igen
        * Højre Klik - Ultimaker_Cura-4.5.0.desktop
            * Klik Åbn
              * Vælg - Hav tillid til og kør 
              * Luk programmet igen
## Tilpas Favoritter (Dok)
* Klik Indstillinger
  * Vælg Dok
    * Sæt Ikonstørrelse til 36
      * Luk indstillinger

#### Fjern programmer fra Favoritter (Dok)
* Højre-Klik "Mozilla Thunderbird"
  * Klik "Fjern fra favoritter"
* Højre-Klik "Rhytmbox"
  * Klik "Fjern fra favoritter"
* Højre-Klik "LibreOffice Writer"
  * Klik "Fjern fra favoritter"
* Højre-Klik "Ubuntu software"
  * Klik "Fjern fra favoritter"
* Højre-Klik "Hjælp"
  * Klik "Fjern fra favoritter"

#### Tilføj programmer til Favoritter (Dok)
* Klik "Vis programmer" i favoritter
  * Søg efter (f)
    * Højre Klik FreeCad_0.19-...
      * Vælg Føj til favoritter
  * Søg efter (c)
    * Højre Klik Ultimaker_Cur...
      * Vælg Føj til favoritter
  * Søg efter ()
    * Højre Klik Geany
      * Vælg Føj til favoritter
  * Søg efter (p)
    * Højre Klik Pinta
      * Vælg Føj til favoritter
    * Højre Klik Pronterface
      * Vælg Føj til favoritter
  * Søg efter (v)
    * Højre Klik VLC media pla...
      * Vælg Føj til favoritter
  tryk [ESC] flere gange til du er ude


## Hent Visual Studio Code & PlatformIO
### VSC
* Åbn Firefox
  * Skriv adressen https://code.visualstudio.com/Download
    * Vælg Linux .deb - Debian, Ubuntu
      * Åbn med "Softwareinstallation()standard"
        * Klik "Installer"
          * Indtast password
            * Afslut Installer vindue når installation er færdig
              * Luk Firefox
* Klik Favoritter "Vis programmer"
  * søg efter "v"
    * Højreklik "Visual Studio ..."
      * Føj til favoritter
        * Tryk [ESC] og engan til [ESC]
* 
For nu følg denne vejledning [Installation af Visual Studio Code (VSC) & PlatformIO :](https://github.com/sekt1953/ESP32-Seniorhus-2020-1#installation-af-visual-studio-code-vsc--platformio-)