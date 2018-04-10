---


---

<h1 id="m300---dokumentation-michel-schmidli">M300 - Dokumentation Michel Schmidli</h1>
<p>Im Modul 300 wurde uns die Arbeit mit Containers und Virtuellen Maschienen näher gebracht.</p>
<h2 id="auftrag">Auftrag</h2>
<p>Der Auftrag war es, Services mittels Vagrant und GitHub zu realisieren. Mit Vagrant kann man mit einem Vagrantfile eine VM erstellen ohne irgendwelche konfigurationen zu machen.</p>
<h2 id="bewertung">Bewertung</h2>
<p>• Umgebung (Multi VM) funktionsfähig auf eigenem Notebook (Note 4.0)<br>
• Bestehende VM aus Vagrant Cloud zum laufen bringen (Note 4.5)<br>
• Eigener Service auf Basis IaC implementieren (Note 5.0 – 5.5)<br>
• Projekt auf github Ablegen und Dokumentieren (Markdown) (Note 5.5 – 6.0)</p>
<h2 id="vorgehen">Vorgehen</h2>
<p>Ich habe mir den Auftrag genau angeschaut und informierte mich. Anschliessen planten ich unser Vorgehen. Die Vorgehensweise wurde vom Auftragsdokument übernommen, da dort alles genau beschrieben wurde. Ich arbeitete somit das Skript durch. Ich verstand nicht jede Aufgabe, jedoch konnte ich was ich nicht verstand im Internet nachschlagen.</p>
<h2 id="github">GITHUB</h2>
<p>Ich haben mein Konto bei GITHUB erstellt. GITHUB bietet die Möglichkeit Dateien auf einfachem Wege hochzuladen, leicht bearbeitbar und offen zugänglich zu machen.</p>
<p>Mit Github ist es möglich den Kontakt zu anderen Entwickler auf der ganzen Welt zu aufzubauen. Genau auf diesem Wege werde ich auch mein fertige Vagrantfiles mit unserem Lehrer kommunizieren.</p>
<h2 id="produktive-nutzung">Produktive Nutzung</h2>
<p>Meine Umgebung ist darauf aufgebaut, dass man mit wenigen Commands eine ganze VM Umgebung aufsetzen kann, die sich automatisch installiert und Konfiguriert.</p>
<p>Bsp. kann ein Informatiker, der mehrere VMs pro Tag aufsetzten muss sich sehr viel Arbeit, Zeit und Nerven sparen.</p>
<p>So kann er mit Git Bash in ein Verzeichnis gehen, wo sich ein Vagrant-File befindet. In diesem Verzeichnis kann er ganz einfach den command “vagrant up” ausführen und das Vagrant-File wird ausgeführt.</p>
<p>In diesem Vagrant-File ist definiert von wo er sich das OS grabben soll, welche konfigurationen er vornehemen soll und wie ist installiert wird.</p>
<h2 id="eigener-service">Eigener Service</h2>
<p>Ich haben bei dem Auftrag des eigenen Services zuerst darauf geschaut, dass ich das Vagrantfile überhaupt verstehe. Durch logisches überlegen, konnten ich Anpassungen in diesem File vornehmen.<br>
Sie sehen gleich mein Vagrantfile bei dem Ubuntu mit einer Firewall Reproxy installiert wird. Die Ports haben ich so abgeändert, dass jegliche Kommunikation von der IP 10.0.2.2 zugelassen wird.<br>
Außerdem das Protokoll TCP über den Port 80 in jedem Fall zugelassen.<br>
Um sicherzugehen, dass diese Commands auch ausgeführt werden, führen wir den Command Force ein.</p>
<p>Das Vagrantfile ist als Code folgender masse aufgebaut. Zuerst kommt ein Script welche die Konfigurationen an der installierten VM vornimmt. Danach kommt der Code welche die VM konfiguriert und schlussendlich auch das Script ausführt.</p>
<pre><code>$Script = &lt;&lt;-Script
sudo apt-get update
sudo apt-get install apache2 -y
sudo apt-get install ufw -y
sudo ufw allow from 10.0.2.2 to any port 22
sudo ufw allow 80/tcp
sudo ufw --force enable
sudo apt-get install libapache2-mod-proxy-html -y
sudo apt-get install libxml2-dev -y
a2enmod proxy
a2enmod proxy_html
a2enmod proxy_http/41
sed -i '$aServerName localhost' /etc/apache2/apache2.conf
sudo rm /var/www/html/index.html
    sudo touch /var/www/html/index.php
    cat &lt;&lt; EOF &gt; /var/www/html/index.html
    &lt;!doctype html&gt;
    &lt;head&gt;
			Titel - Test        
    &lt;/head&gt;
    &lt;body&gt;
            Dies ist der Test, wlecher aufzeigt, dass das Vagrantfile funktioniert.
    &lt;/body&gt;
    &lt;/html&gt;
service apache2 restart
cd /etc/apache2/sites-enabled
wget https://pastebin.com/raw/GbjFC2ii
cp GbjFC2ii 001-reverseproxy.conf
Script

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64" 
  config.vm.network "private_network", ip:"192.168.50.50"
  config.vm.network "forwarded_port", guest:80, host:8090, auto_correct: true
  config.vm.synced_folder ".", "/var/www/html"
  config.vm.provider "virtualbox" do |vb| 
    vb.memory = "512"
  end
  config.vm.provision "shell", inline: $Script
end
</code></pre>
<h2 id="test">Test</h2>
<p>Für den Test habe ich fünf Test-Case erstellt.</p>
<p>Die Test-Case sind wie folgendes Beispiel aufgeführt:</p>
<p>Was wird getestet / was ist zu erwarten / was ist passiert<br>
Test / Test funktioniert / Test funktioniert</p>
<p><strong>Erstellung VM</strong> / <em>Nach “Vagrant up” wird das File ausgeführt und die Vm ist in “Virtualbox” sichtbar</em>. / Nach ausführen des Vagrantfiles, wurde die VM in Virtualbox erstellt.<br>
<img src="https://perrone.myqnapcloud.com:450/share.cgi/V_Schmidli.PNG?ssid=02YbC2K&amp;fid=02YbC2K&amp;path=%2F&amp;filename=V_Schmidli.PNG&amp;openfolder=normal&amp;ep=" alt=""></p>
<p><strong>SSH Verbindung</strong> / <em>Über GitBash kann auf die VM mittels SSH zugegriffen werden</em> / Die Verbindung zu dieser VM ist mit SSH möglich.<br>
<img src="https://perrone.myqnapcloud.com:450/share.cgi/SSH_Schmidli.PNG?ssid=02YbC2K&amp;fid=02YbC2K&amp;path=%2F&amp;filename=SSH_Schmidli.PNG&amp;openfolder=normal&amp;ep=" alt=""></p>
<p><strong>Firewall</strong> / <em>Die Firewall ist im Status “Gestartet”</em>. / Die Firewall ist gestartet.<br>
<img src="https://perrone.myqnapcloud.com:450/share.cgi/Firewall_Schmidli.PNG?ssid=02YbC2K&amp;fid=02YbC2K&amp;path=%2F&amp;filename=Firewall_Schmidli.PNG&amp;openfolder=normal&amp;ep=" alt=""></p>
<p><strong>Betrieb</strong> / <em>Die Website ist über “localhost:8090” ansprechbar.</em> / Die Website ist über “localhost:8090” ansprechbar.<br>
<img src="https://perrone.myqnapcloud.com:450/share.cgi/apache_Schmidli.PNG?ssid=02YbC2K&amp;fid=02YbC2K&amp;path=%2F&amp;filename=apache_Schmidli.PNG&amp;openfolder=normal&amp;ep=" alt=""></p>
<p><strong>Apache</strong> / <em>Apache ist als Prozess sichtbar.</em> / Apache ist als Prozess sichtbar.<br>
<img src="https://perrone.myqnapcloud.com:450/share.cgi/Unbenann.PNG?ssid=02YbC2K&amp;fid=02YbC2K&amp;path=%2F&amp;filename=Unbenann.PNG&amp;openfolder=normal&amp;ep=" alt=""></p>

