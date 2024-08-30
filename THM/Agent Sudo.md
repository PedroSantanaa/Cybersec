Para fazer analise de imagens fakes atras de passwords usamos:
```
binwalk -e [imagem]
```
Com isso achamos um zip escondido dentro da imagem
Agora precisamos quebrar a senha necessaria no ZIP
```
zip2john [zip] > cracked
```
Com isso achamos essa hash
```
8702.zip/To_agentR.txt:$zip2$*0*1*0*4673cae714579045*67aa*4e*61c4cf3af94e649f827e5964ce575c5f7a239c48fb992c8ea8cbffe51d03755e0ca861a5a3dcbabfa618784b85075f0ef476c6da8261805bd0a4309db38835ad32613e3dc5d7e87c0f91c0b5e64e*4969f382486cb6767ae6*$/zip2$:To_agentR.txt:8702.zip:8702.zip
```
E para quebrar essa hash usamos
```
john [file]
```
![[Pasted image 20240830092739.png]]
Achamos dentro do arquivo uma string base64
QXJlYTUx
```
echo QXJlYTUx | base64 -d
```
E achamos a palavra Area51
Temos outra forma de procurar dados nas imagens
```
steghide extract -sf [imagem]
```
![[Pasted image 20240830093239.png]]
Achamos a senha de ssh dele e o nome, e podemos logar no ssh
