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

## Eigener Service
Nach der Installation von Docker habe ich mich an dem erstellen eines eigenen Dockerfiles gemacht. Um nicht immer wieder die Docker-Command herauszusuchen habe ich diese in einer Tabelle unten aufgelistet.

### Docker-Commands
| Command | Beischreibung |
|--|--|
| docker run "Name" | Führt das gewünschte Docker-Image aus (Ohne "") |
|--|--|

Command

Description

docker create`

creates a container but does not start it.

`docker rename`

allows the container to be renamed.

`docker run`

creates and starts a container in one operation.

`docker rm`

deletes a container.

`docker update`

updates a container’s resource limits.

`docker ps`

shows running containers.

`docker images`

shows all images.

`docker build`

creates image from Dockerfile.
<!--stackedit_data:
eyJoaXN0b3J5IjpbOTg2NTA1Njk0LDE4NTQ5MjgyMzksLTg5Nj
E4ODM2NCwtMTYxNDc0NDg1NF19
-->