# XScreenSaver

[Ask Ubuntu - How can I change or install screensavers?](https://askubuntu.com/questions/64086/how-can-i-change-or-install-screensavers)
[SciFi Addict - screensaver / Slideshow for Linux??](https://www.youtube.com/watch?v=R8uuAyuzWbM)


## XScreenSaver installation

```bash
sudo apt-get install xscreensaver xscreensaver-gl-extra xscreensaver-data-extra

# Now remove gnome-screensaver

sudo apt-get remove gnome-screensaver

# Now start the xscreensaver configuration tool - from a terminal:

xscreensaver-demo
```
## Configure XScreenSaver
* Vælg fanebladet "Skærmtilstande"
  * Sæt Tilstand til : Only One Screen Saver
  * Sæt Screen Saver til : GLSlideshow
  * Sæt Start efter til : 1 min
  * Sæt Gentag efter til : 1 min
* Vælg fanebladet "Avanceret"
  * Select : Benyt Skrivebordsbilleder
  * Select : Vælg tilfældigt billed
  * Indtast sti til dine billeder

## Starting xscreensaver from login

* Start Opstartsprogrammer  
 ![IndstillingerForOpstartsprogrammer](/Images/IndstillingerForOpstartsprogrammer.png)
* Vælg Tilføj  
   ![Tilføj](/Images/Tilføj.png)
* Udfyld skema som vist og Tryk [Tilføj]
 

