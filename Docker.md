# M300 - Dokumentation Michel Schmidli
  ## LB01 - Docker
Im Modul 300 wurde uns mit Docker das Arbeiten mit Container erklärt.

## Auftrag

Der Auftrag war es,  mittels Docker sogenannte "Container" zu erstellen und den ganzen Ablauf mittels Github zu Dokumentieren. Mit Docker können Services in eine art Container betrieben werden. Der Service greift auf die Ressourcen des Hostes zu ist jedoch aber ganz isoliert von dem Betriebssystem. Das heißt der Service kann jeder zeit einfach mit seinem Container von einer Maschine zu einem anderem Host transportiert werden.


## Bewertung

• Umgebung funktionsfähig auf eigenem Notebook (Note 4.0)  
• Bestehende Docker Container kombinieren oder Container als Backend, Desktop App als Frontend (Note 4.5)  
• Eigene Container erstellen (Note 5.0 – 5.5)  
• Projekt auf github Ablegen und Dokumentieren (Markdown) (Note 5.5 – 6.0)

## Vorgehen

Ich habe mir den Auftrag genau angeschaut und mich drüber informierte mich. Meine Vorgehensweise wurde vom Auftragsdokument übernommen, da dort alles genau beschrieben wurde. Ich arbeitete das das Skript durch und anschließend die Installation von Docker habe ich mittels dem folgende Link erarbeitet: 
https://docs.docker.com/get-started/
Mittels dieser Anleitung konnte ich die Docker Installation sehr gut nachvollziehen. Für das weiter vorgehen habe ich im Internet recherchiert und dann auf der Ubuntu VM ausprobiert.

## Docker

**Docker**  ist eine Open Source-Software zur Isolierung von Anwendungen mit Containervirtualisierung.
Die Bereitstellungen von Anwendungen wird durch Docker massiver vereinfacht. Die Docker-Container haben kein eigenes Betriebsleitsystem, die benötigte Leistung wird von dem Host-Betriebssystem genommen. Der Container ist ein Isolierter bereich welcher nicht fest auf dem Host installiert ist. So kann man diesen beliebig einfach und ohne großen Aufwand au eine neuen Host migrieren. 


### Docker-Commands
| Command | Beischreibung |
|--|--|
|docker create| Erstellt einen Container aber startet diesen nicht. |
|	docker rename| Der Container kann mit diesem Befehl Umbennent werden. |
| docker run "Name" | Führt das gewünschte Docker-Image aus. (Ohne "") |
| docker rm | Der ausgewählte Container wird gelöscht. |
| docker update | Die Ressourcen von dem Container könne angepasst werden. |
| docker ps | Listet die laufenden Container auf. |
| docker images | Listet alle Docker-Iamges auf dem Host auf. |
| docker build | Erstellt aus einem Dockerfile ein Image. |

## Eigener erstellten Service mit Docker

Um eine Grundwissen zu erarbeiten, wie die Docker-Container funktionieren, habe ich zu beginn die verschieden Images, welche von Docker bereitgestellt werden, angeschaut. Dann zu der Anleitung von Docker habe ich mittels einem vorgegeben Image einen Container aufgesetzt. Nach diesem Schritt habe ich das aufsetzen von Container verstanden. 
Ich habe mich nun an die Erstellung eines eigenen Images gemacht. 

 #### PHP
 
 In meinem ersten Docker-Image habe ich einen PHP aufgesesetzt.
 
 1. Als erstes bin ich auf die Docker Webseite ( https://docker.com ) und habe dort nach der aktuelles PHP-Version welche von Docker unterstützt wird gesucht. Dabei bin ich auf Folgende Version gestoßen `FROM php:7.0-apache`.
 2. Nun habe ich ein PHP-File mit einem einfachen Text in meinem erstellten Ordner gespeichert. 
 **Bild von Terminal mit PHP Text**
 3. Als nächstes habe ich das Dockerfile erstellt, welches als Grundlage für das Image dient.
 **Bild von Terminal Dockerfile PHP**
 4. Dann habe ich mittels dem Befehl `docker build -t schmidlifinal .` das Image erstellt.
**Bild Terminal Befehl "docker build"**
 6. Im den Container dann zu starten musste ich noch den Befehl `docker run -p 80:80 schmidlifinal` eingeben.
 **Bild Terminal "docker run"**
 7. Um zu überprüfen ob es funktioniert hat, habe ich im Browser *localhost:80* eingegeben und bin erstellten Seite gelandet.
**Bild PHPFirefox**
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIwNDkyMTY0MjEsLTE5NTE1ODA1ODMsMT
EzOTg5ODc1OCwxMTA3NzM0NDY4LC0xMjU0MzIyMDU4LC05NjM1
NDEzMDAsMjAzMDEwMTY4OCwxMDUyMTAyMjQ2LDE0NzI3MDA1MD
ksNjMyMzI3NDQzLDEwOTA5MzI4ODEsLTExMTkzMzQzNTgsLTc5
NzI1NDA2NiwtMTczMjUwNTg4MiwtMTU3Nzk3NTQ2MSwtMjUyNT
gyOTcwLDE3MzI3ODMyNTgsMTczMjc4MzI1OCwxODU0OTI4MjM5
LC04OTYxODgzNjRdfQ==
-->