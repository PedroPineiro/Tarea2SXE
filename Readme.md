# Tarea 2 SXE
## 1. Descarga la imagen "alpine" SIN ARRANCARLA y comprueba que está en tu equipo
```
docker pull alpine
```
### 
```
docker images alpine
```
## 2. Crea un contenedor sin ponerle nombre. ¿está arrancado? Obtén el nombre
```
docker run -it alpine
```
### Como nos encontramos dentro del contenedor, significa que está en ejecución
### Para ver el nombre del contenedor usamos
```
docker ps -a
```
### El Container ID es 611d22ff7d90, y el nombre es affectionate_turing, ya que pone este nombre aleatorio por defecto
## 3. Crea un contenedor con el nombre 'dam_alp1'. ¿Cómo puedes acceder a él?
```
docker run -it --name dam_alp1 alpine
```
### Para acceder a él, primero tenemos que ejecutar el contenedor
```
docker start dam_alp1
```
### Seguidamente acceder con
```
docker exec -it dam_alp1 /bin/sh
```
## 4. Comprueba que ip tiene y si puedes hacer un ping a google.com
### Primero tenemos que acceder a él de la misma forma que antes si es que no estamos ya dentro
```
docker start dam_alp1
docker exec -it dam_alp1 /bin/sh
```
### Para comprobar la ip hacemos
```
ip addr
```
### Para hacer un ping a google.com hacemos
```
ping google.com
```
## 5. Crea un contenedor con el nombre 'dam_alp2'. ¿Puedes hacer ping entre los contenedores?
```
docker run -it --name dam_alp2 alpine
```
### Nos aseguramos de que tenemos los dos contenedores arrancados
```
docker start dam_alp1
docker start dam_alp2
```
### Necesitamos la ip de uno de los contenedores
```
docker inspect dam_alp2 | grep IPAddress
```
### Ahora entramos en el otro contenedor para hacer ping con la ip
```
docker exec -it dam_alp1 /bin/sh
ping 172.17.0.3(En mi caso)
```