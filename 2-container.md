# Contenedores

### Crear un contenedor
Para crear un nuevo contenedor Docker a partir de una imagen específica, pero sin iniciarlo automáticamente. 

```
docker create --name <nombre contenedor> <nombre imagen>:<tag>
```
Crear el contenedor  **srv-web** usando la imagen nginx version alpine

<img width="526" height="99" alt="image" src="https://github.com/user-attachments/assets/fcf78bdf-a723-4805-850b-6ab2da6899f7" />


Si creas un contenedor en Docker sin asignarle un nombre específico utilizando la opción --name, Docker asignará automáticamente un nombre aleatorio al contenedor. Este nombre suele consistir en una combinación de palabras y números.  

Crear el contenedor usando la imagen hello-world

<img width="521" height="61" alt="image" src="https://github.com/user-attachments/assets/6b253cd6-5d17-411f-acef-5ab5bfff4254" />



### Listar los contenedores ejecutándose o no

```
docker ps -a
```

<img width="1065" height="137" alt="image" src="https://github.com/user-attachments/assets/dd5e0a51-a127-4a4b-a1ff-48a9a392f7c4" />


### Para iniciar un contenedor

```
docker start <nombre contenedor o identificador>
```

Iniciar el contenedor srv-web 

<img width="343" height="99" alt="image" src="https://github.com/user-attachments/assets/4265a2e7-c5c1-4861-99c2-777bf2ad5739" />


### Listar los contenedores ejecutándose
```
docker ps 
docker ps | grep <nombre contenedor>
```

<img width="870" height="118" alt="image" src="https://github.com/user-attachments/assets/16d74f9e-f43b-4276-8aa7-94ab0e8c7fa9" />


### Para detener un contenedor

```
docker stop <nombre contenedor>
```

### Para crear un contenedor y ejecutarlo inmediatamente

```
docker run --name <nombre contenedor> <nombre imagen>:<tag>
```
![Ecosistema de Docker](dockerRun.PNG)

Crear y ejecutar inmediatamente el contenedor **srv-web2** usando la imagen nginx:alpine

```
docker run --name srv-web2 nginx:alpine
```

**¿Qué sucede luego de la ejecución del comando?**
```
El contenedor está siendo ejecutado en la terminal, por lo que no se puede seguir escribiendo comandos.
```

Cuando ejecutas un contenedor en primer plano sin la opción -d (modo detach), el contenedor captura la entrada estándar (stdin) del terminal, lo que significa que el terminal queda "atrapado" y no puedes introducir más comandos hasta que detengas el contenedor.

### Para crear un contenedor y ejecutarlo inmediatamente sin estar vinculados al mismo
-d: Es la opción que indica a Docker que ejecute el contenedor en segundo plano (en modo "detach").
Cuando un contenedor se ejecuta en segundo plano, Docker devuelve el control al terminal inmediatamente después de iniciar el contenedor, lo que permite al usuario seguir ejecutando otros comandos en el mismo terminal sin que el contenedor detenga la interacción.

```
docker run -d --name <nombre contenedor> <nombre imagen>:tag
```
Crear y ejecutar inmediatamente el contenedor **srv-web3** en modo detach usando la imagen nginx:alpine
```
docker run -d --name srv-web3 nginx:alpine
```

### Para eliminar un contenedor

```
docker rm <nombre contenedor>
```
Eliminar el contenedor que se creó a partir de la imagen hello-world 
```
docker rm nifty_vaughan
```

Verificar que el contenedor que se eliminó
```
docker ps -a
```

### Para eliminar un contenedor que esté ejecutándose

```
docker rm -f <nombre contenedor>
```
Eliminar el contenedor **srv-web3**
```
docker rm -f srv-web3
```
Verificar que el contenedor que se eliminó
```
docker rm ps
```
### Para inspecionar un contenedor 

Inspeccionar el contenedor **srv-web** 
```
docker inspect srv-web
```
