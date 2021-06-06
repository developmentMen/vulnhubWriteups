
# IMMERSION
### COLDDWORLD series
*write up de la siguiente*
## [maquina de Vulnhub](https://www.vulnhub.com/entry/colddworld-immersion,668/)

---

## Port scan
`nmap -sV -p- <ip-victima>`
![immersion vulnhub](img/immersion1.png)
El *escaneo de puertos* muestra **2 servicios** que parecen ser un **http** en el clasico **puerto 80** y un **ssh** pero en un **puerto poco comun**, el **3042**, hydra podria ayudarnos a probar fuerza bruta en el ssh pero primero veamos que encontramos en el http

## Dir fuzz
`dirb http://<ip-http>`
![immersion vulnhub](img/immersion2.png)
Buscando directorios, mediante algunas de las muchas herramientas que existes (*gobuster, dirb, wfuzz*) nos encontramos rapidamente y sin muchas vueltas con la pagina de login, entre otras
![immersion vulnhub](img/immersion3.png)
vamos al **codigo fuente**
![immersion vulnhub](img/immersion4.png)
introducimos cualquier username y password
![immersion vulnhub](img/immersion5png)
presten atencion al url y la manera en como parsea el php, nos podria dejar ver archivos como el de carls.txt
![immersion vulnhub](img/immersion6png)