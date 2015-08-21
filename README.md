# Custom page for Domoticz

<img src="https://drive.google.com/uc?id=0BxlxVZPVHBfPeFRsVmpENmdrNGc"/>

# Installation

<pre>
sudo apt-get install git
git clone https://github.com/vil1driver/monitor.git /home/pi/domoticz/www/monitor
</pre>

# Configuration

Editez le fichier <pre>/home/pi/domoticz/www/monitor/js/<b>frontpage_settings.js</b></pre>
Pour cela, je vous recommande les logiciels suivant:<br>
<a href=http://www.clubic.com/telecharger-fiche11156-winscp.html>WinSCP</a> (explorateur de fichier utilisant la connexion SSH, permettant transferts, �ditions, suppressions..)<br>
<a href=http://www.clubic.com/telecharger-fiche9567-notepad.html>NotePad++</a> comme �diteur (� pr�ciser dans les option de WinSCP)

renseignez l'url de votre domoticz
<pre>$.domoticzurl="http://USER:PASS@IP:PORT";</pre>
puis les idx de vos devices, l'info � glaner (value), le nom de la cellule dans laquelle les placer, la l�gende, etc... 
exemple avec l'heure en haut � gauche (cellule 1)
<pre>
['0','Clock','cell1','','','','font-family:digital;color:#8BFD1C;font-size:160%'],</pre>

Cette commande donne la liste des values potentiellement utilisables, d'un device<br>
remplacez IDX par l'idx de votre device
<pre>
/json.htm?type=devices&rid=IDX
</pre>

# Utilisation

vous aurez sans doute remarqu� la pr�sence des fichiers nomm�s frontpage.html et frontpage3.html<br>
ce dernier offre une page suppl�mentaire (soit 3 pages) par rapport au fichier frontpage.html (qui n'en compte que 2)

� votre convenance (si vous souhaitez avoir 3 pages),<br>
renommez <b>frontpage.html</b> en <b>frontpage2.html</b> et <b>frontpage3.html</b> en <b>frontpage.html</b>
<pre>
cd /home/pi/domoticz/www/monitor/
mv frontpage.html frontpage2.html && mv frontpage3.html frontpage.html
</pre>
puis afficher votre nouvelle interface via <br>
<a href="#">http://user:pass@ip:port/monitor/frontpage.html</a><br>
ou<br>
<a href="#">http://ip:port/monitor/frontpage.html</a><br>

# Mise � jour

<pre>
cd /home/pi/domoticz/www/monitor/
mv js/frontpage_settings.js js/frontpage_settings_old.js
git fetch --all
git reset --hard origin/master
</pre>
puis �ditez de nouveau le fichier <b>frontpage_settings.js</b><br>
pour y configurer les nouveaux param�tres qui peuvent y avoir �t� ajout�<br>
et rapatrier votre configuration sauv�e dans <b>frontpage_settings_old.js</b>

<pre>
##########################################################
#### vvvvv   USER VALUES below vvvvv   #######
##########################################################

			Lors d'une mise � jour,
		ne conserver que ce qui se trouve ici.

##########################################################
#### ^^^^^   USER VALUES above ^^^^^   #######
##########################################################
</pre>
