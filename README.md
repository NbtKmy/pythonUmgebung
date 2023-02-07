# Umgebung für Python mit Docker erstellen

## Requirements
- Docker Desktop
- git 

## How to

1. Dieses Repo clonen
```
$ git clone https://github.com/NbtKmy/pythonUmgebung.git
``` 

Je nach Bedarf kann man weitere Libraries & Module in "requiremeints.txt" hinzufügen.

2. Den Ordner wechseln
```
$ cd pythonUmgebung
```

3. Docker-Image und Container bilden und aktivieren
```
$ docker-compose up -d --build
```

## Direkt im Container arbeiten
Wenn der Container aktiv läuft...;

1. In den Container gehen

```
$ docker-compose exec python3 bash
```
... Dann kann man Libraries & Modules installieren oder die Python-Codes laufen lassen

2. Version Check
```
$ python --version
```

3. Hello World
```
$ python helloWorld.py
```

4. Aus den Container ausloggen
```
$ exit
```

## Jupyter-Notebook
Wenn der Container aktiv läuft...;

1. Den folgenden Befehl im Terminal eingeben
```
$ docker run -v $PWD/src:/usr/src -w /usr/src -it --rm -p 7777:8888 pythonumgebung-python3 jupyter-lab --ip 0.0.0.0 --allow-root -b localhost
```

2. ... Irgendwann zeigt sich die folgende Meldung im Terminal:
```
1 active kernel
    Jupyter Server 2.2.1 is running at:
        http://918072908807e:8888/lab?token=xxxxx
        http://127.0.0.1:8888/lab?token=xxxxx
```

Das Token (xxxxx) kopieren und den Terminal laufen lassen. Und im Web-Browser den URL "localhost:7777" eingeben und öffenen.

Wenn es gut läuft, kommt man auf die Login-Seite von Jupyter-Notebook. Das Token dort eingeben. Eventuell wird __nach der Admin-Berechtigung__ des PCs gefragt.
Danach kann man im Browser arbeiten.

3. Arbeit im Jupyter-Notebook stoppen

Im Terminal, wo Jupyter läuft, `Ctrl + C` drücken.

Die ipynb-File sind im src-Ordner zu finden.
