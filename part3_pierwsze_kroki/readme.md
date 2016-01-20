# Part3 - Pierwsze kroki z Dockerem

## Hello World
```bash
docker run ubuntu:14.04 /bin/echo 'Hello world'
```

## Interaktywny bash
```bash
docker run -t -i ubuntu:14.04 /bin/bash
```

## Daemonowy Hello World
```bash
docker run -d ubuntu:14.04 /bin/sh -c "while true; do echo hello world; sleep 1; done"
```

## Dockerowe daemony
```bash
docker ps -a
```
Przykładowy output:
```bash
$ docker ps -l
CONTAINER ID  IMAGE                   COMMAND       CREATED        STATUS        PORTS                    NAMES
bc533791f3f5  training/webapp:latest  python app.py 5 seconds ago  Up 2 seconds  0.0.0.0:49155->5000/tcp  nostalgic_morse
```

## Sprzątanie
```bash
docker stop
```

### Porządki w szafie
```bash
docker rm --force `docker ps -qa`
```

## Debugowanie
```bash
docker logs insane_babbage
```
Przykładowy output:
```bash
$ docker logs -f nostalgic_morse
* Running on http://0.0.0.0:5000/
10.0.2.2 - - [23/May/2014 20:16:31] "GET / HTTP/1.1" 200 -
10.0.2.2 - - [23/May/2014 20:16:31] "GET /favicon.ico HTTP/1.1" 404 -
```

### Podglądamy top kontenera
```
$ docker top nostalgic_morse
PID                 USER                COMMAND
854                 root                python app.py
```

### Głęboka woda
```bash
docker inspect nostalgic_morse
```

```json
[{
    "ID": "bc533791f3f500b280a9626688bc79e342e3ea0d528efe3a86a51ecb28ea20",
    "Created": "2014-05-26T05:52:40.808952951Z",
    "Path": "python",
    "Args": [
       "app.py"
    ],
    "Config": {
       "Hostname": "bc533791f3f5",
       "Domainname": "",
       "User": "",
. . .
```
