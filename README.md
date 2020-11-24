# Ubuntu 18.04.4 Installation og setup for undervisning
## [The mind behind Linux | Linus Torvalds](https://www.youtube.com/watch?v=o8NPllzkFhE)
## [Tech Talk: Linus Torvalds on git](https://www.youtube.com/watch?v=4XpnKHJAok8)


## 01 - Basic Installation af Ubuntu
Denne del at vejledningen, forventer at du har en Blank PC, eller en PC hvor alt indhold kan over skrives   
NB!!! følger du denne vejledning vil din disk blive slettet, og kan ikke gendannes !!!
* Hold [Ctrl] og klik denne link [01-Basis installation af Ubuntu 18.04.4 LTS](https://github.com/mstedet/Ubuntu-18.04-Setup/blob/master/01-Basis%20installation%20af%20Ubuntu.md) for at åbne vejledning i et nyt fane blad.

## 02 - Tilpasning af din Ubuntu installation
I dette afsnit tilpasser vi Biblioteks strukturen for [AppImage](https://appimage.org/), Opretter Biblioteker til projekter, og installerer en række nyttige værktøjer, som vi kan få brug for i vores undervisning. Vi tager også hånd om at tildele rettigerheder.
* Hold [Ctrl] og klik denne link [02-Tilpasning af din Ubuntu installation.md](https://github.com/mstedet/Ubuntu-18.04-Setup/blob/master/02-Tilpasning%20af%20din%20Ubuntu%20installation.md) for at åbne vejledning i et nyt fane blad.

## 03 - Tilpas Mozilla-Firefox
Her er nogle få ændringer af Firefox som jeg bruger, som Filhentning indstillinger, Startside, Bogmærker og Udvidelser.
* Hold [Ctrl] og klik denne link [03-Tilpas Mozilla-Firefox.md](https://github.com/mstedet/Ubuntu-18.04-Setup/blob/master/03-Tilpas%20Mozilla-Firefox.md) for at åbne vejledning i et nyt fane blad.

## 04 - AppImages programmer
I dette afsnit viser jeg hvordan man kan installerer Appimage programmer, oprette desktop-filer til disse programmer. En af hjørne stenene i at få Appimages programmer til at fungerer er desktop-filerne. 
* Hold [Ctrl] og klik denne link [04-AppImages programmer.md](https://github.com/mstedet/Ubuntu-18.04-Setup/blob/master/04-AppImages%20programmer.md) for at åbne vejledning i et nyt fane blad.

## 05 - Tilpas Favoritter (også kaldet Dok)
Her hjælpes du igennem opsætning af Favoritter som vi vil bruge dem i undervisningen
* Hold [Ctrl] og klik denne link [05-Tilpas Favoritter.md](https://github.com/mstedet/Ubuntu-18.04-Setup/blob/master/05-Tilpas%20Favoritter.md) for at åbne vejledning i et nyt fane blad.

## 06 - Installation af Visual Studio Code med PlatformIO 
Her gennemgår vi opsætningen af Visual Studio Code med PlatformIO, og laver de nødvendige tilpasninger så indstillinger af VSC & PlatformIO passer til vores projekt biblioteker, som vi oprettede i afsnit ## 02 - Tilpasning af din Ubuntu installation.
* Hold [Ctrl] og klik denne link [06-Installation af Visual Studio Code med PlatformIO.md](https://github.com/mstedet/Ubuntu-18.04-Setup/blob/master/06-Installation%20af%20Visual%20Studio%20Code%20med%20PlatformIO.md) for at åbne vejledning i et nyt fane blad.

## 07 - Start et nyt Project i PlatformIO
Her vises hvordan vi starter et projekt (ESP32_Blink) til vores ESP32 prosessor.
* Hold [Ctrl] og klik denne link [07-Start et nyt Project i PlatformIO.md](https://github.com/mstedet/Ubuntu-18.04-Setup/blob/master/07-Start%20et%20nyt%20Project%20i%20PlatformIO.md) for at åbne vejledning i et nyt fane blad.

## 08 - Github Setup

## 09 - Git Setup

## 10 - SSH Setup for github konto

## 11 - SSH Setup for flere Github kontoer

## 12 - Github kontrol fra PlatformIO

## 13 - Git & GitHub med PlatformIO

## Ubuntu 20.04 Extra
Når du installerer Ubuntu 20.04 vil det være en god idea at åbne en terminal og tilføje følgnde kommandoer
```
sudo dpkg --configure -a  # får mDNS til at virke
sudo apt-get update       # opdaterer index
sudo apt-get upgrade -y   # opgraderer 
sudo apt-get autoremove   # fjerner programmer der ikke bruges længere
```

