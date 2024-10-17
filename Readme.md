# Tarea 2 SXE
## 1. Descarga la imagen "alpine" SIN ARRANCARLA y comprueba que está en tu equipo
```
docker pull alpine
```
### 
```
docker images -it alpine
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
