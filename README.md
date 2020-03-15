# Ubuntu 18.04.4 Installation og setup for undervisning

## 01 - Basic Installation af Ubuntu
Denne del at vejledningen, forventer at du har en Blank PC, eller en PC hvor alt indhold kan over skrives   
NB!!! følger du denne vejledning vil din disk blive slettet, og kan ikke gendannes !!!
* Hold [Ctrl] og klik denne link [01-Basis installation af Ubuntu 18.04.4 LTS](https://github.com/mstedet/Ubuntu-18.04-Setup/blob/master/01-Basis%20installation%20af%20Ubuntu.md) for at åbne vejledning i et nyt fane blad.

## 02 - Tilpasning af din Ubuntu installation
I dette afsnit tilpasser vi Biblioteks strukturen for [AppImage](https://appimage.org/), Opretter Biblioteker til projekter, og installerer en række nyttige værktøjer, som vi kan få brug for i vores undervisning. Vi tager også hånd om at tildele rettigerheder.
* Hold [Ctrl] og klik denne link [02-Tilpasning af din Ubuntu installation.md](https://github.com/mstedet/Ubuntu-18.04-Setup/blob/master/02-Tilpasning%20af%20din%20Ubuntu%20installation.md) for at åbne vejledning i et nyt fane blad.

## 03 - Tilpas Mozilla-Firefox
Her er nogle få ændringer af Firefox som jeg bruger, som Filhentning indstillinger, Startside, Bogmærker og Udvidelser.
* Hold [Ctrl] og klik denne link [03- Tilpas Mozilla-Firefox.md](https://github.com/mstedet/Ubuntu-18.04-Setup/blob/master/03-%20Tilpas%20Mozilla-Firefox.md) for at åbne vejledning i et nyt fane blad.

## 04 - AppImages programmer

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