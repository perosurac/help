# Installer un GUI sur Ubuntu-WSL2
Le principe est de faire un "remote desktop" en local ...
```
$ sudo apt install xrdp
$ sudo apt install xfce4
$ sudo apt install xfce4-goodies
$ sudo cp /etc/xrdp/xrdp.ini /etc/xrdp/xrdp.ini.bak
$ sudo sed -i 's/3389/3390/g' /etc/xrdp/xrdp.ini
$ sudo sed -i 's/max_bpp=32/#max_bpp=32\nmax_bpp=128/g' /etc/xrdp/xrdp.ini
$ sudo sed -i 's/xserverbpp=24/#xserverbpp=24\nxserverbpp=128/g' /etc/xrdp/xrdp.ini
$ echo xfce4-session > ~/.xsession
$ sudo vim /etc/xrdp/startwm.sh
```
Commenter les lignes 
```
# test -x /etc/X11/Xsession && exec /etc/X11/Xsession
# exec /bin/sh /etc/X11/Xsession
```
A la fin du fichier, ajouter la ligne
```
startxfce4
```
Démarrer xrdp
```
$ sudo /etc/init.d/xrdp start
```
A partir du PC sur lequel est installé WSL2, faire un remote desktop avec l'adresse 
```
localhost:3390
```
avec les credentials de WSL2 !!!
