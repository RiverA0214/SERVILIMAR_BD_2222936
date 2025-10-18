# SERVILIMAR_BD_2222936
base de datos de Servilimar


- Descargar y ejecutar el contenedor de PostgreSQL 14
<img width="966" height="312" alt="image" src="https://github.com/user-attachments/assets/e03140ba-eed6-4faa-83c2-dc5024daa2ce" />

Ejecutando el codigo:
docker run -d --name postgres_ulimar --network servilimar_net -e POSTGRES_USER=ulimar -e POSTGRES_PASSWORD=ex4men_db -e POSTGRES_DB=turnos_db -p 5432:5432 postgres:14

En donde:

--name postgres_ulimar → nombra el contenedor

--network servilimar_net → conecta a la red de docker

-e POSTGRES_USER=ulimar → crea el usuario ulimar

-e POSTGRES_PASSWORD=ex4men_db → asigna la contraseña

-e POSTGRES_DB=turnos_db → crea una base de datos inicial llamada turnos_db

-p 5432:5432 → abre el puerto para conectarse desde la PC

postgres:14 → imagen PostgreSQL versión 14


- verificamos que este corriendo

Con el comando:
docker ps

deberia salir algo asi:
<img width="1176" height="83" alt="image" src="https://github.com/user-attachments/assets/e42268e0-fffd-49e0-b7a4-625c60e322d3" />

- Descargar y ejecutar el Contenedor PGAdmin v4
<img width="1184" height="308" alt="image" src="https://github.com/user-attachments/assets/3d6e47e7-8976-481c-9ebd-b79f5e6fafea" />

Ejecutando el codigo:

docker run -d --name pgadmin4 --network servilimar_net -e PGADMIN_DEFAULT_EMAIL=usuario@servilimar.com -e PGADMIN_DEFAULT_PASSWORD=limar#123 -p 5050:80 dpage/pgadmin4

En donde definimos los datos de acceso:

Email: usuario@servilimar.com

Contraseña: limar#123

- Accedemos a http://localhost:5050/

En el navegador web y entramos con los datos de acceso definidos anteriormente

inicio de seccion:
<img width="1920" height="954" alt="image" src="https://github.com/user-attachments/assets/8b4c2574-d4ab-4052-9b00-d956234cdb27" />

seccion iniciada:
<img width="1920" height="956" alt="image" src="https://github.com/user-attachments/assets/b20cc96e-b7b2-4c75-86f2-bc06690cd097" />

- Crear la Base de Datos Servilimar
  
Una vez adentro hacemos click derecho en "servers" en la parte superior izquierda y vamos a "Register → server"

<img width="1920" height="951" alt="image" src="https://github.com/user-attachments/assets/047e2c3c-2482-4110-b646-2299082bf1bf" />

En la pestaña General, escribe:

Name: Servidor LiMar
<img width="723" height="573" alt="image" src="https://github.com/user-attachments/assets/9dfa5ed1-ebf5-4933-8ff4-bd2822ce07bf" />

En la pestaña Connection

Host name/address: postgres_ulimar

Port: 5432

Username: ulimar

Password: ex4men_db

<img width="714" height="566" alt="image" src="https://github.com/user-attachments/assets/3fe71a84-6804-4c8b-b47a-077c839cdd8c" />

Y ahi ya presionamos el boton "Save" en la parte inferior derecha

- Creamos las Tablas DDL

Abrimos el arbol de la izquierda "Servidor LiMar → Databases → turnos_db" y hacemos click izquierdo y seleccionamos "Query Tool"
<img width="1920" height="948" alt="image" src="https://github.com/user-attachments/assets/3418d7b5-b18e-431e-8be5-a6fbd368d2ee" />

Ahi podremos escribir el codigo DDL y luego darle click al boton (Run/Execute) para ejecutar todo
<img width="1920" height="952" alt="image" src="https://github.com/user-attachments/assets/0c307a48-08a6-41f5-a4af-93e35d0f991f" />
Sabremos que se hizo bien cuando sale un mensaje verde que dice "Query returned successfully in X ms."

- Insertamos los datos con DML

Debajo de todo el codigo DDL podemos escribir el codigo DML para insertar los datos en las tablas ya creadas y luego ejecutarlo con el mismo boton de (Run/Execute)
<img width="1920" height="921" alt="image" src="https://github.com/user-attachments/assets/5975efdc-1530-41f6-8416-7f7121e8c308" />

- Fin

Asi ya tenemos nuestra Base de Datos con la informacion insertada, podemos revisar que quedo bien en "Servidor LiMar → Databases → turnos_db → Schemas → public → Tables" donde deben aparecer las tablas

y tambien ejecutando un comando de busqueda para ver los datos de las tablas (ej: SELECT * FROM MEDIO;)
para correr solo una linea de texto se selecciona la linea y se unde el boton de "Run1" que esta a la derecha de "Run"
<img width="1920" height="950" alt="image" src="https://github.com/user-attachments/assets/dc5200a4-93bc-4136-aee7-391e9e79b011" />











