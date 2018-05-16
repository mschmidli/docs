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
Die Bereitstellungen von Anwendungen wird durch Docker massiver vereinfacht. Die Docker-Container haben kein eigenes Betriebsleitsystem, die benötigte Leistung wird von dem Host-Betriebssystem genommen. Der ganze Container ist jedoch nicht fest auf dem Host installiert. 


## Eigener Service
Nach der Installation von Docker habe ich mich an dem erstellen eines eigenen Dockerfiles gemacht. Um nicht immer wieder die Docker-Command herauszusuchen habe ich diese in einer Tabelle unten aufgelistet.


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

y
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTM1ODExNjQxNywxMDkwOTMyODgxLC0xMT
E5MzM0MzU4LC03OTcyNTQwNjYsLTE3MzI1MDU4ODIsLTE1Nzc5
NzU0NjEsLTI1MjU4Mjk3MCwxNzMyNzgzMjU4LDE3MzI3ODMyNT
gsMTg1NDkyODIzOSwtODk2MTg4MzY0LC0xNjE0NzQ0ODU0XX0=

-->