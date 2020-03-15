# 01-Basis installation af Ubuntu 18.04.4 LTS
## NB !!! Dette vil slette alt på din hardisk !!!!!!!
## 1. Installer din Ubuntu fra USB-Key eller CD, her er en kort beskrivelse:
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
## 2. Opdatering af din Ubuntu Installation
* Efter genstart login og start et Terminal vindue med tast kombinationen [Ctrl]+[Alt]+T
* opdater din installation til nyeste version, ved at kopiere linier herunder en for en og indsætte den i Terminal vinduet, når du bliver spurt om password, er det det du valgte under installationen.
```bash
# opdater din linux
sudo apt update
sudo apt full-upgrade -y
sudo apt autoremove -y
```
