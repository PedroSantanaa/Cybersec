Como encontrar vulnerabilidades em algum cms, apache
```
sudo searchsploit -w [nome do item]
```
Após encontrar da para baixar para sua VM
```
sudo searchsploit -m [exploit]
```
Mudar o chmod para executar
```
sudo chmod +x [arquivo]
```
Para executar o arquivo tem que passar a url e a wordlist no executavel
```
sudo python3 [arquivo] -u [URL] --crack -w [wordlist]
```