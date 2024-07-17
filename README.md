# MoviePlatform

Este proyecto está dividido en:
- FrontEnd realizado en React
- BackEnd realizado en Python con FastAPI
- DB con MongoDB

## Despliegue
Para su puesta en funcionamiento, además de clonar el repositorio en una carpeta local, necesitaremos tener instalado [Docker](https://www.docker.com/products/docker-desktop/).

Una vez cumplidos estos dos pasos, habría que acceder por terminal en la carpeta raiz del proyecto donde se encuentra el archivo `docker-compose.yaml` y sería suficiente con ejecutar uno de los siguientes comandos para poner a funcionar los 3 dockers que componen este proyecto en función de si queremos permanecer atachados o no al log de los mismos:

```bash
    docker-compose up
    docker-compose up -d
```

Una vez iniciados los dockers podremos ir nuestro navegador web y entrar al frontend del mismo por la ruta `http://localhost:30080/`

Incialmente, la web debería ser como se muestra en la siguiente imagen:

![MovieApp demo image](docs/imgs/MoviePlatform.png)

## Backend
Para el backend se ha utilizado Python junto con la librería [FastAPI](https://fastapi.tiangolo.com/). La implementación de la API se encuentra en el archivo `api.py` que emplear el archivo `mongo.py` donde se realiza la comunicación con la DB de MongoDB por medio de pymongo.

Para ver la información detallada de la API, una vez estén corriendo los dockers. Podemos ir a `http://localhost:3000/docs` (si no se ha cambiado la configuración por defecto) y consultar la documentación de la API así como probar directamente desde esta web las distintas llamadas y ver el resultado que se obtiene.

También se han implementado Test unitarios para la API donde se valida el correcto funcionamiento de todas las funcionalidades implementadas en ella.


## Frontend
Para el frontend se ha utilizado React acompañado de Vite. Para su desarrollo se debe ejecutar el comando `npm run dev` que nos permitirá ver en el navegador cada cambio que realicemos en el código fuente.
Para llevarlo a producción deberemos crear los archivos de distribución. Para ello se ejecutar `npm run build`. Al ejecutar este comando debemos asegurarnos de que en el interior de la carpeta "assets" se encuentran todos los assets que habíamos referenciado, en ocasiones puede perderse alguno.

> Se puede configurar en vite la copia de los assets a la carpeta de distribución pero no está funcionando en este momento

