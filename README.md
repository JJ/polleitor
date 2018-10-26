# Polleitor
_Version 0.1.1_    
[![Build Status](https://travis-ci.com/JJ/polleitor.svg?branch=master)](https://travis-ci.org/jj/polleitor)
[![Coverage Status](https://coveralls.io/repos/github/oslugr/polleitor/badge.svg?branch=master)](https://coveralls.io/github/oslugr/polleitor?branch=master)

Sistema cliente-servidor para crear widgets de encuestas.

La parte servidor usa LokiDB para almacenar las encuestas y resultados y funciona con REST, la parte cliente JavaScript para configurar las encuestas y enviar los resultados.

La configuración se hace en el servidor y en él se almacenan los resultados.

## Instalación

Tras clonar de este repo:
```bash
npm install
```

Ejecutar Tests (opcional):
```bash
npm test
```

Iniciar servidor:
```bash
npm start
```

De ahí, te vas al menú Principal de Polleitor en http://localhost:3000
y listo. Aparecerá una pequeña demo.

Si usas [Heroku](http://heroku.com), cambia `repository` en el fichero de configuración `app.json` y

    heroku login
	heroku git:remote -a mi-proyecto-en-heroku
	git push heroku master


## Documentación

Generar esta documentación:
```bash
npm install -g groc
groc
```

[Click](https://jj.github.io/polleitor) para ver la documentación online

Los ficheros principales son:

* [Rutas](http://jj.github.io/polleitor/routes.html)
* [Configuración](http://jj.github.io/polleitor/config.html),
  donde efectivamente se crean las encuestas



## API
Se accede al servicio mediante una API REST:

| **Método** | **Ruta**           | **Descripción**       | **Petición**| **Respuesta**|
|:----------:|:------------------:|:---------------------:|:-----------:|:------------:|
| GET        |`:poll`             | Devuelve las preguntas de una encuesta |Sin cuerpo en la petición|`[{question,[options],id}]`|
| GET        |`:poll/resultados`  | Devuelve el poll y los resultados|Sin cuerpo en la petición|`[{question,[options],id,[answers]}]`|
| PUT        |`:poll`             | Envía respuestas a las preguntas de un poll |`[{id,answer}]`|`{poll,updates,failedUpdates}`|

## Quien ha montado esto

> Desarrollado por [JJ Merelo, Germán Martínez y Andrés Ortiz](https://github.com/JJ/polleitor/graphs/contributors) bajo licencia MIT
> Documentación completa en <https://jj.github.io/polleitor>
