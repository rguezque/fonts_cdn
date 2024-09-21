# Fonts CDN

Repositorio de fuentes, utilizado como un CDN para proyectos web.

## Agregar fuentes

Modifica el archivo `data.json` agregando un nuevo elemento en al array `fonts` siguiendo la misma estructura de las demás fuentes registradas. Para generar su atributo `integrity` abre una terminal en linux y ejecuta lo siguiente:

```bash
cat FILENAME.css | openssl dgst -sha384 -binary | openssl base64 -A
```

Donde `FILENAME` es el nombre del archivo de la hoja de estilos.

>[!NOTE]
>Si el repositorio de las fuentes cambia de dominio, modifica el atributo `cdn` con la URL correspondiente.
