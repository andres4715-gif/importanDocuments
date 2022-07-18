# _Como hacer una integración entre jenkins local y bitbucket:_

Se puede validar este [video](https://www.youtube.com/watch?v=zpscQ1ONFmk&t=423s) para el paso a paso o tambien la documentación en la [web](https://medium.com/@jairosolarte/integraci%C3%B3n-continua-ci-2-integrar-jenkins-y-bitbucket-amazone-aws-9a01e81f9120)

Lo primero que hay que hacer es:

1. En jenkins descargar el plugin de bitbucket

```shell
Bitbucket Plugin
Version223.vd12f2bca5430
Integrates with BitBucket
Report an issue with this plugin
```

2. Dentro del proyecto que estamos configurando en el apartado de **build triggers** se debe activar la opción

```text
Build when a change is pushed to BitBucket
```

Los siguientes pasos son en Bitbucket y la consola:

Los pasos en la consola son:

1. Instalar ngrok
   Esto se hace con el comando de homebrew:

```shell
$ brew install ngrok/ngrok/ngrok
```

Esto lo que hace es generar un link con el cual podemos ingresar en Bitbucket:

2. Despues de instalado se ejecuta el comando en la terminal:

```shell
$ ngrok http 8080
```

3. El resultado por consola es parecido a esto:

```shell
ngrok                                                                                                                                 (Ctrl+C to quit)

Phishing is against the TOS. Don't do it.

Session Status                online
Session Expires               1 hour, 30 minutes
Terms of Service              https://ngrok.com/tos
Version                       3.0.6
Region                        United States (us)
Latency                       225ms
Web Interface                 http://127.0.0.1:4040
Forwarding                    https://f2de-2800-e2-1180-e0b-f5e2-3abc-abf8-2a2a.ngrok.io -> http://localhost:8080

Connections                   ttl     opn     rt1     rt5     p50     p90
                              1       0       0.00    0.00    5.32    5.32
```

Ahora los pasos a continuación son en BitBucket:

1. Localizado en el repositorio que estamos trabajado
2. En los setting del proyecto
3. En la parte de WORKFLOW encontramos el apartado de: Webhooks
4. Se crea un nuevo Webhooks con agregando el nombre y la url que nos dio por consola la ejecución de ngrok:

Ejemplo:

```shell
$ https://f2de-2800-e2-1180-e0b-f5e2-3abc-abf8-2a2a.ngrok.io
```

5. Se le debe agregar un complemento:

```shell
/bitbucket-hook/
```

El link completo queda de la siguiente forma:

```text
https://f2de-2800-e2-1180-e0b-f5e2-3abc-abf8-2a2a.ngrok.io/bitbucket-hook/
```

6. Se deja la opción de status: Active
7. Se deja la opción en Triggers en Push
8. Click en **save**

Ahora los pasos son en el programa (codigo)

Se realiza algún cambio en el codigo y se hace todo el proceso de git

- git add.
- git commit ...
- git push ...

y se valida que en la consola escuchando de ngrok se muestre la ejecución.

- Se debe mostrar de esta forma:

```shell
ngrok                                                                                                                                 (Ctrl+C to quit)

Phishing is against the TOS. Don't do it.

Session Status                online
Session Expires               1 hour, 20 minutes
Terms of Service              https://ngrok.com/tos
Version                       3.0.6
Region                        United States (us)
Latency                       84ms
Web Interface                 http://127.0.0.1:4040
Forwarding                    https://f2de-2800-e2-1180-e0b-f5e2-3abc-abf8-2a2a.ngrok.io -> http://localhost:8080

Connections                   ttl     opn     rt1     rt5     p50     p90
                              1       0       0.00    0.00    5.32    5.32

HTTP Requests
-------------

POST /bitbucket-hook/          200 OK
```

Ahora se valida en bitbucket que tambien quede en el historial de bitbucket en el apartado de Webhooks

```shell
Event	Details		Actions
repo:push	24 minutes ago	200	View details
```

Esto lo que ejecuta es a nivel de jenkins cada vez que se realice un push a la rama seleccionada en el repositorio de bitbucket

En jenkins se debe ejecutar el proyecto.
