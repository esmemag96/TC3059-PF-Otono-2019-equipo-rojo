# API (Posts V2)

Creado: @antony999k

[![version](https://img.shields.io/badge/version-1.0.0-ff69b4.svg)]()
[![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/wasabeef/awesome-android-ui)

Gestiona los posts en Colibri

# Microservicio en Docker

Se debe crear el Dockerfile con su respectivo .dockerignore que incluya node_modules

- Hacer build de la imagen:  `docker build -t pf_api_post:<version_api> .`
- Correr docker: `docker run -p 8001:8001 pf_api_post:<version_api>`

# Endpoints

Ruta Desarrollo: http://127.0.0.1:8001/

## Obtener los posts de usuarios a los que sigue un usuario (GET) ![#c5f015](https://placehold.it/15/c5f015/000000?text=+)
    /posts/feed
    
### Header
    "Authorization": "$token"
    
### Body
    N/A

#### Respuesta esperada
    [
        {
            "keys": [
                "p.text",
                "p.created_at",
                "u2.username",
                "u2.name",
                "u2.profile_img_url"
            ],
            "length": 5,
            "_fields": [
                "Hola soy antony666k",
                {
                    "year": {
                        "low": 2019,
                        "high": 0
                    },
                    "month": {
                        "low": 5,
                        "high": 0
                    },
                    "day": {
                        "low": 9,
                        "high": 0
                    },
                    "hour": {
                        "low": 7,
                        "high": 0
                    },
                    "minute": {
                        "low": 43,
                        "high": 0
                    },
                    "second": {
                        "low": 1,
                        "high": 0
                    },
                    "nanosecond": {
                        "low": 156000000,
                        "high": 0
                    },
                    "timeZoneOffsetSeconds": {
                        "low": 0,
                        "high": 0
                    },
                    "timeZoneId": null
                },
                "antony666k",
                "Adrian",
                "profile_2.png"
            ],
            "_fieldLookup": {
                "p.text": 0,
                "p.created_at": 1,
                "u2.username": 2,
                "u2.name": 3,
                "u2.profile_img_url": 4
            }
        },
        {
            "keys": [
                "p.text",
                "p.created_at",
                "u2.username",
                "u2.name",
                "u2.profile_img_url"
            ],
            "length": 5,
            "_fields": [
                "Esto es una prueba",
                {
                    "year": {
                        "low": 2019,
                        "high": 0
                    },
                    "month": {
                        "low": 5,
                        "high": 0
                    },
                    "day": {
                        "low": 9,
                        "high": 0
                    },
                    "hour": {
                        "low": 6,
                        "high": 0
                    },
                    "minute": {
                        "low": 42,
                        "high": 0
                    },
                    "second": {
                        "low": 39,
                        "high": 0
                    },
                    "nanosecond": {
                        "low": 494000000,
                        "high": 0
                    },
                    "timeZoneOffsetSeconds": {
                        "low": 0,
                        "high": 0
                    },
                    "timeZoneId": null
                },
                "lakar",
                "Karla R",
                "profile_3.png"
            ],
            "_fieldLookup": {
                "p.text": 0,
                "p.created_at": 1,
                "u2.username": 2,
                "u2.name": 3,
                "u2.profile_img_url": 4
            }
        },
        {
            "keys": [
                "p.text",
                "p.created_at",
                "u2.username",
                "u2.name",
                "u2.profile_img_url"
            ],
            "length": 5,
            "_fields": [
                "Hola este es mi primer post con DB en kubernetes",
                {
                    "year": {
                        "low": 2019,
                        "high": 0
                    },
                    "month": {
                        "low": 5,
                        "high": 0
                    },
                    "day": {
                        "low": 9,
                        "high": 0
                    },
                    "hour": {
                        "low": 6,
                        "high": 0
                    },
                    "minute": {
                        "low": 36,
                        "high": 0
                    },
                    "second": {
                        "low": 11,
                        "high": 0
                    },
                    "nanosecond": {
                        "low": 831000000,
                        "high": 0
                    },
                    "timeZoneOffsetSeconds": {
                        "low": 0,
                        "high": 0
                    },
                    "timeZoneId": null
                },
                "lakar",
                "Karla R",
                "profile_3.png"
            ],
            "_fieldLookup": {
                "p.text": 0,
                "p.created_at": 1,
                "u2.username": 2,
                "u2.name": 3,
                "u2.profile_img_url": 4
            }
        }
    ]

## Crear un Post (POST) ![#c5f015](https://placehold.it/15/c5f015/000000?text=+)
    /post
    
### Header
    "Authorization": "$token"
    
### Body
    {
        "Text": "Este es un post de prueba"
    }

#### Respuesta esperada
    {
        "status": 201,
        "name": "Created",
        "customMessage": "El post fue creado con éxito",
        "message": "Recurso creado"
    }

## Eliminar un Post (DELETE) ![#c5f015](https://placehold.it/15/c5f015/000000?text=+)
    /post
    
### Header
    "Authorization": "$token"
    
### Body
    {
        "id":$id_int
    }

#### Respuesta esperada
    {
        "status": 200,
        "name": "OK",
        "customMessage": "El post fue eliminado con éxito",
        "message": "OK"
    }

## Obtener losultimos post disponibles limitado a 30 (GET) ![#c5f015](https://placehold.it/15/c5f015/000000?text=+)
    /posts/latest
    
### Header
    "Authorization": "$token"
    
### Body
    {
        "id":$id_int
    }

#### Respuesta esperada
    {
        "status": 200,
        "name": "OK",
        "customMessage": "El post fue eliminado con éxito",
        "message": "OK"
    }

## Obtener un posts de mi usuario (GET) ![#c5f015](https://placehold.it/15/c5f015/000000?text=+)
    /posts/me
    
### Header
    "Authorization": "$token"
    
### Body
    N/A

#### Respuesta esperada
    [
        {
            "keys": [
                "n.text",
                "n.created_at",
                "u.username",
                "u.name",
                "u.profile_img_url"
            ],
            "length": 5,
            "_fields": [
                "Hola soy antony666k",
                {
                    "year": {
                        "low": 2019,
                        "high": 0
                    },
                    "month": {
                        "low": 5,
                        "high": 0
                    },
                    "day": {
                        "low": 9,
                        "high": 0
                    },
                    "hour": {
                        "low": 7,
                        "high": 0
                    },
                    "minute": {
                        "low": 43,
                        "high": 0
                    },
                    "second": {
                        "low": 1,
                        "high": 0
                    },
                    "nanosecond": {
                        "low": 156000000,
                        "high": 0
                    },
                    "timeZoneOffsetSeconds": {
                        "low": 0,
                        "high": 0
                    },
                    "timeZoneId": null
                },
                "antony666k",
                "Adrian",
                "profile_2.png"
            ],
            "_fieldLookup": {
                "n.text": 0,
                "n.created_at": 1,
                "u.username": 2,
                "u.name": 3,
                "u.profile_img_url": 4
            }
        }
    ]


## Obtener un post por su id (GET) ![#c5f015](https://placehold.it/15/c5f015/000000?text=+)
    /post/:id
    
### Header
    N/A
    
### Body
    N/A

#### Respuesta esperada
        {
            "keys": [
                "n.text",
                "n.created_at",
                "u.username",
                "u.name",
                "u.profile_img_url"
            ],
            "length": 5,
            "_fields": [
                "Hola soy antony666k",
                {
                    "year": {
                        "low": 2019,
                        "high": 0
                    },
                    "month": {
                        "low": 5,
                        "high": 0
                    },
                    "day": {
                        "low": 9,
                        "high": 0
                    },
                    "hour": {
                        "low": 7,
                        "high": 0
                    },
                    "minute": {
                        "low": 43,
                        "high": 0
                    },
                    "second": {
                        "low": 1,
                        "high": 0
                    },
                    "nanosecond": {
                        "low": 156000000,
                        "high": 0
                    },
                    "timeZoneOffsetSeconds": {
                        "low": 0,
                        "high": 0
                    },
                    "timeZoneId": null
                },
                "antony666k",
                "Adrian",
                "profile_2.png"
            ],
            "_fieldLookup": {
                "n.text": 0,
                "n.created_at": 1,
                "u.username": 2,
                "u.name": 3,
                "u.profile_img_url": 4
            }
        }



## Obtener un posts de un usuario (GET) ![#c5f015](https://placehold.it/15/c5f015/000000?text=+)
    /posts/:username
    
### Header
    N/A
    
### Body
    N/A

#### Respuesta esperada
    [
        {
            "keys": [
                "n.text",
                "n.created_at",
                "u.username",
                "u.name",
                "u.profile_img_url"
            ],
            "length": 5,
            "_fields": [
                "Hola soy antony666k",
                {
                    "year": {
                        "low": 2019,
                        "high": 0
                    },
                    "month": {
                        "low": 5,
                        "high": 0
                    },
                    "day": {
                        "low": 9,
                        "high": 0
                    },
                    "hour": {
                        "low": 7,
                        "high": 0
                    },
                    "minute": {
                        "low": 43,
                        "high": 0
                    },
                    "second": {
                        "low": 1,
                        "high": 0
                    },
                    "nanosecond": {
                        "low": 156000000,
                        "high": 0
                    },
                    "timeZoneOffsetSeconds": {
                        "low": 0,
                        "high": 0
                    },
                    "timeZoneId": null
                },
                "antony666k",
                "Adrian",
                "profile_2.png"
            ],
            "_fieldLookup": {
                "n.text": 0,
                "n.created_at": 1,
                "u.username": 2,
                "u.name": 3,
                "u.profile_img_url": 4
            }
        }
    ]


## Likear un post (POST) ![#c5f015](https://placehold.it/15/c5f015/000000?text=+)
    /post/:id/like
    
### Header
    "Authorization": "$token"
    
### Body
    N/A

#### Respuesta esperada
    {
        "status": 201,
        "name": "Created",
        "customMessage": "El post(1) fue likeado",
        "message": "Recurso creado"
    }


## Dislikear un post (DELETE) ![#c5f015](https://placehold.it/15/c5f015/000000?text=+)
    /post/:id/like
    
### Header
    "Authorization": "$token"
    
### Body
    N/A

#### Respuesta esperada
    {
        "status": 201,
        "name": "Created",
        "customMessage": "El post(1) fue deslikeado",
        "message": "Recurso creado"
    }

## Obtener numero de post de mi usuario (GET) ![#c5f015](https://placehold.it/15/c5f015/000000?text=+)
    /posts_n/me
    
### Header
    "Authorization": "$token"
    
### Body
    N/A

#### Respuesta esperada
    {
        "keys": [
            "followers"
        ],
        "length": 1,
        "_fields": [
            {
                "low": 1,
                "high": 0
            }
        ],
        "_fieldLookup": {
            "followers": 0
        }
    }

## Obtener numero de post de un usuario (GET) ![#c5f015](https://placehold.it/15/c5f015/000000?text=+)
    /posts_n/:username
    
### Header
    N/A
    
### Body
    N/A

#### Respuesta esperada
    {
        "keys": [
            "followers"
        ],
        "length": 1,
        "_fields": [
            {
                "low": 1,
                "high": 0
            }
        ],
        "_fieldLookup": {
            "followers": 0
        }
    }

## Revisar estado del api (GET) ![#c5f015](https://placehold.it/15/c5f015/000000?text=+)
    /health

#### Respuesta esperada
    {
    "status": 200,
    "name": "OK",
    "message": "i'm healthy",
    "customMessage": "API en funcionamiento"
    }

# Errores

## Manejo de Errores
Para manejar errores personalizados hay que crear el error y lanzar un next.

Todos los errores deben pasar por helper/error.helper.js.

### Ejemplo
let e = new Error('{mensaje customizado de tu error}');
e.name = "{ErrorType}";
return next(e);

### ErrorType
Código de error  | ErrorType (e.name)
------------- | -------------
301  | movedPermanently
303  | seeOther
304  | notModified
307  | temporaryRedirect
308  | permanentRedirect
400  | badRequest
401  | unautorized
403  | forbidden
404  | notFound
405  | methodNotAllowed
409  | conflict
415  | unsupportedMediaType
418  | imATeapot
500  | internal
501  | notImplemented
502  | badGateway
503  | serviceUnavailable
504  | gatewayTimeout
507  | insufficientStorage

## Respuesta de errores
Los errores son retornados en JSON. Cada error tiene un **status**, **name**, **message** y **customMessage**.
El campo **message** es personalizado y debe estar en ingles

### Ejemplo de un status 400
    {
        "status": 400,
        "name": 'badRequest',
        "message": 'Bad Request' + (err.message ? ': ' + err.message : ''),
        "customMessage": 'Solicitud Erronea'
    }

# Contribuir con el API

## Paquetes/Librerias recomendadas (Globales/Locales)
- Nodejs: `v8.11.3`
- Nodemon `v1.18.7` (Opcional para testing)

## Iniciar aplicación (Desarrollo)
- `npm install` Instalar paquetes de npm
- `npm start` Para iniciar con node
- `npm test` Para iniciar con nodemon
- `npm run dev` Para iniciar en modo desarrollo (muesta los logs)

## Pasos para correcto funcionamiento
1. Instalar paquetes/librerias Locales
2. Descargar el repositorio
3. Instalar paquetes de npm
4. Es necesario contar con el archivo *.env*, este no se puede descargar via Github ya que contiene claves privadas (pedir al administrador del repositorio)
5. Correr el servidor

## Archivo *.env* (sin "")
    PORT=<Puerto de la aplicación>

    NEO4J_USER=<username *default:neo4j*>
    NEO4J_PASSWORD=<password>

    REDIS_HOST=<IP o dominio>
    REDIS_PORT=<puerrto>
    REDIS_PASSWORD=<redis password>

## Guía de estilos
### Mensajes en los Commits de Git

- Utilizar oraciones en presente ("Botón añadido" no "Se añadio botón")
- Comenzar el commit con mayúsculas
- Cuando solo se cambia documentacion añadir `[ci skip]` en el título del commit
- Considerar comenzar el commit con un emoji
- :rocket: `:rocket:` cuando se lanza una nueva versión
- :sparkles: `:sparkles:` cuando se añade nuevo código
- :art: `:art:` mejora en el formato/estructura del código
- :racehorse: `:racehorse:` mejora en el performance del código
- :book: `:book:` cuando se escribe documentación
- :bug: `:bug:` cuando se corrige un bug
- :fire: `:fire:` cuando se eliminó código o archivos

## Notas

# Changelog

# Ayuda
@antony999k, antony999k@hotmail.com
