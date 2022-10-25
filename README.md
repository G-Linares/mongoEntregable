# Entregable Mongo

## Requerimientos:

- Docker
- Docker Compose
- Admin tool para Mongo (Yo uso Compass pero puedes ocupar Robot3T o alguna otra)

## Puertos:

Como ocupo BD se ocupara el siguiente puerto

- 27017 (MongoDB)

## Notas antes de iniciar:

Para el correcto funcionamiento se necesita tener inicializado docker en tu maquina. Asi como tener los archivos correspondientes en la base del proyecto. Se neceista crear un archivo llamado ".env" con el contenido similar al ".env.example" en la base del proyecto. Ahi se definen los puertos a usar, si no se modifica nada, solo copia y pega el example al .env creado.

## Como iniciar proyecto:

- Clonar repositorio

```
git clone https://github.com/G-Linares/mongoEntregable.git
```

- Creaer archivo ".env" en root de proyecto con el contenido de ".env.example"

- Iniciar docker en tu computadora

- Situarse en la capeta del proyecto y correr el comando

```
docker-compose up -d
```

- Despues de que docker monte la base de datos, verificamos que todo este correcto con:

```
docker ps -a
```

- Si el proceso esta ahi, ya tienes la base de datos montada en puerto dsesignado(si dejaste el .env como estaba el example deberia estar en el puerto 27017) de mongo DB.
- Si tienes MongoDB instalado con super user y contraseña, puedes intentar acceder con esa misma en Robot3T o Compass, si no con la que se define en el .env
- Para acceder al shell de mongo debes ejecutar el siguiente comando.

```
docker exec -it mongo-entregable bash
```

- Una vez accedas a la terminal del contenedor, puedes ejecutar el comando

```
mongosh
```

- Ahi deberias estar dentro de mongo con la base de datos montada. Ahora tienes que hacer login como admin a mongo :

```
use admin
```

```
db.auth("username", "password")
```

- Deberias recibir un {ok:1} si no verifica que la contraseña y el username correspondan con los cargados en el env.
- Después accede a la BD con

```
use entregable
```

- Y listo, ya puedes probar los scripts mencionados en el archivo .txt de la root
