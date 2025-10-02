# Imagen
### Descargar imagen
Descarga la última versión de la imagen disponible en el registro de Docker.

```
docker pull <nombre imagen> 
```

Descarga una versión específica de la imagen, cada imagen tiene etiquetas (tags) para diferentes versiones.
Una imagen puede tener la etiqueta latest para representar la última versión, si no se especifica una etiqueta se hará referencia a la versión latest.

```
docker pull <nombre imagen>:<tag>
```

Descargar la imagen **hello-world**
```
docker pull hello-world
```

**¿Qué es nginx**
```
Es un servidor web, proxy inverso y balanceador de carga de código abierto de alto rendimiento
```

Descargar la imagen  **nginx** en la versión **alpine**

```
docker pull nginx
```

### Listar imágenes

```
docker images
```

<img width="984" height="522" alt="image" src="https://github.com/user-attachments/assets/b2650dba-d11e-4b0d-b564-7e91c287d2db" />


**Identificadores**

En Docker, se utilizan varios identificadores para diferenciar de manera única los elementos del sistema, como imágenes, contenedores, volúmenes y redes. Estos identificadores son generados automáticamente por Docker y son únicos dentro del contexto del sistema Docker en el que se encuentran. 

### Inspeccionar una imagen
El comando docker inspect se utiliza para obtener información detallada sobre un objeto de Docker específico, como un contenedor, una imagen, un volumen o una red.  Proporciona información en formato JSON sobre el objeto especificado.

```
docker inspect <nombre imagen>
docker inspect <nombre imagen>:<tag>
```

Inspeccionar la imagen hello-world 
```
docker inspet hello-world
```

<img width="819" height="351" alt="image" src="https://github.com/user-attachments/assets/ca0ca91f-92ce-404a-99ce-ed86f33b4614" />


**¿Con qué algoritmo se está generando el ID de la imagen**
```
Mediante un hash criptográfico de la imagen, y típicamente se utiliza el algoritmo SHA256

```

### Filtrar imágenes

```
docker images | grep <termino a buscar>

```

<img width="522" height="223" alt="image" src="https://github.com/user-attachments/assets/c9548773-863a-4009-8af4-f80cbd5939d4" />


### Para eliminar una imagen
Eliminar permanentemente la imagen de tu sistema Docker.

```
docker rmi <nombre imagen>:<tag>
```

Eliminar la imagen hello-world 

<img width="773" height="126" alt="image" src="https://github.com/user-attachments/assets/73e1665c-90cf-4364-b09b-ac2ebdd83f90" />


-f: Es la opción para forzar la eliminación de la imagen incluso si hay contenedores en ejecución que utilizan esa imagen.
Cuando eliminas una imagen Docker, Docker no elimina automáticamente los contenedores que se han creado a partir de esa imagen. Esto significa que, aunque hayas eliminado la imagen, el contenedor seguirá ejecutándose normalmente.  
**Considerar**
Eliminar una imagen no afecta a los contenedores que se han creado a partir de esa imagen, a menos que esos contenedores dependan de archivos o configuraciones específicas de la imagen eliminada. En ese caso, es posible que los contenedores se comporten de manera inesperada después de eliminar la imagen.
Es una buena práctica detener y eliminar todos los contenedores que dependan de una imagen antes de eliminar la imagen en sí.

```
docker rmi -f <nombre imagen>:<tag>
```
