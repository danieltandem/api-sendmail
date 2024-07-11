# API SENDMAIL por Daniel Vargas #

## Descripcion ##

Este api es un examen en el que mostramos como mandar un email en php con el metodo POST

## Instalacion ##

1. Crear las carpetas del proyecto api-sendmail/v1/endpoint-webservice/index.php
2. Creamos todo lo relevante a git siguiendo los 5 pasos:
    -git init
    -git add .
    -git commit -m "primer commit"
    -git remote add origin <https://github.com/danieltandem/apiexamen.git>
    -git push origin master
3.Copiamos el codigo en index.php y revisamos que no haya fallos
4.Probamos que no haya fallos con el archivo sendmail.http y las peticiones al servidor

## Uso endpoint ##

En el endpoint ponemos primero los headers  que necesitemos. Establecemos una variable que se va a llamar $webmaster_email que es el email al que vamos a mandasr el correo. Luego hacemos tres parametros que son 3 inputs que on nombre el email y el mensaje. Metemos un pequeño codigo para que no haya campos vacios. Creamos las 3 variables $subject $body y $headers que son los elementos que va a tener el codigo y terminamos con un if en el que el correo si se ha enviado correctamente nos sacara un mensaje de exito y correo enviado y un else en caso de que no se haya podido enviar por algun error

## Ejemplo de solicitudes ##

En este archivo vamos a realizar las pruebas.

1. Tenemos la primera prueba en la que nos va a dar exito y va a mandasr un correo:

POST <http://localhost/api-sendmail/v1/endpoint-webservice/>

{
    "name": "Daniel",
    "email": "<tandem.danielvdm@gmail.com>",
    "message": "Hola"
}

2. Ahora vamos con los casos en los que no funciona:

-En este caso falta un campo con lo cual va a dar error

POST <http://localhost/api-sendmail/v1/endpoint-webservice/>

{
    "email": "<tandem.danielvdm@gmail.com>",
    "message": "Hola"
}

-Ahora vamos a probar con el email erroneo:

POST <http://localhost/api-sendmail/v1/endpoint-webservice/>

{
    "name": "Daniel",
    "email": "<danielvdm@gmail.com>",
    "message": "Hola"
}
-Y por ultimo con todos los datos faltantes:

POST <http://localhost/api-sendmail/v1/endpoint-webservice/>

{
}
