# Contenedor con twurl

Este repositorio tiene como proposito el crear un contenedor con [twurl](https://github.com/twitter/twurl).
twurl es un aplicativo que facilita el acceso via linea de comandos a los web services expuestos por [twitter](https://twitter.com).

## Modo de uso

* Ejecutar el contenedor

```
docker run -it --rm -v $(pwd):/myroot josanabr/twurl /bin/bash
```

Una vez dentro del contenedor se ejecuta

```
twurl authorize --consumer-key AAAA --consumer-secret BBBB
```

---
**NOTA**
Usted debe cambiar `AAAA` y `BBBB` con sus propios valores. 
Para ello usted debe crear su aplicacion.
Visite este enlace [https://apps.twitter.com/](https://apps.twitter.com/).

Una vez creada la aplicacion, ingresar a dicha aplicacion y visitar la pestana **Keys and Access Tokens**.
---

## Algunos comandos

* `twurl /1.1/statuses/home_timeline.json | jq . | more`
* `twurl /1.1/statuses/home_timeline.json | jq '[.[] | {user_id: .id_str,user_name: .name}]'`

# Webgrafia

* [Twitter en GitHub](https://github.com/twitter/twurl)
* [Tutorial twurl en twitter](https://developer.twitter.com/en/docs/tutorials/using-twurl.html)
* [Tutorial de twurl](https://medium.com/@sunnat629/twurl-curl-for-the-twitter-api-with-jq-65dce6230ecd)
