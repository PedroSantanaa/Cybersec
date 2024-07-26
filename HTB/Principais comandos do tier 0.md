
Temos o inicio/principal comando da investigação que é o **nmap**

```bash
sudo nmap -sV [IP] # comando padrao de 1000 portas
sudo nmap -sV -T4 -p [x-y] [IP] #comando para procurar mais portas dentro de um range
```

Aqui a gente descobre a rotas/portas que rodam no IP em questão

Temos o **telnet** que por padrão roda na porta 23
```bash
telnet [IP]
```
E com isso se mal programado podemos entrar o o usuario **anonymous**

Temos o **FTP** que roda na porta padrao 21
```bash
ftp [IP]
```
Com isso podemos entrar no ftp e com um comando **get** podemos baixar o arquivo para nossa maquina

Temos o SMB que roda nas portas padroes de 139 e 445
```bash
smbclient -L [IP] # para ver os hosts
smbclient \\\\[IP]\\[HOST] # para tentar conectar no host
```

Temos o **Redis**
```bash
redis-cli #principal comando
redis-cli -h [IP] #para especificar o host
redis-cli info #para ver informações e estatisticas
redis-cli select [database_id] #para ver escolhe o database
keys * # lista as keys
get [key] # ver info da key
```