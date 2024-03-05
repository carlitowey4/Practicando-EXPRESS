1. Instalamos y configuramos express
    -> express --view=pug --git

2. Gestionar variables de entornos
    -> npm i dotenv
    -> Editar .env
        PORT=8080

3. Activar dotenv donde sea necesario su uso
    -> Editamos el /bin/www
    -> Añadimos estas lineas:
        require('dotenv').config();
        require('../db/db');

4. Intalamos mongoose:
    -> npm i mongoose

5. Creamos el directorio db y dentro el archivo db.js (Siempre tiene el mismo contenido, solo cambia la uri)

6. Creamos un directorio models donde declaramos los valores que tiene un personaje.

7. Creamos una nueva ruta en el directorio routes, en este caso se llamara personaje.js
    -> Necesita la variable del modelo que hemos exportado como modulo.
    -> Se ajustan todas las rutas posibles.
        res.redirect: Redirecciona a otra ruta
        res.render: Selecciona al pug que atiende la petición

8. Trabajamo el archivo app.js para que la página atienda a la ruta creada.
    -> Añadimos y modificamos estas lineas:
        var personajeRouter = require('./routes/personaje');
        app.use('/', personajeRouter);
        app.use('/personaje', personajeRouter);

9. Preparamos las vistas:
    -> Modificamos layout.pug para que aparezca nuestro nombre arriba siempre
    -> Creamos lista.pug y personaje.pug