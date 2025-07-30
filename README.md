# Fonts CDN

Repositorio de fuentes, utilizado como un CDN para proyectos web.

## Agregar fuentes

Modifica el archivo `data.json` agregando un nuevo elemento en al array `fonts` siguiendo la misma estructura de las demás fuentes registradas. Para generar su atributo `integrity` abre una terminal en linux y ejecuta lo siguiente:

```bash
cat FILENAME.css | openssl dgst -sha384 -binary | openssl base64 -A
```

Donde `FILENAME` es el nombre del archivo de la hoja de estilos.

### Generar SRI (Subresource Integrity) hash en Windows

En un entorno Windows, puedes crear una herramienta para generar SRI hashes con el siguiente código:

```bat
@echo off
set bits=384
openssl dgst -sha%bits% -binary %1% | openssl base64 -A > tmp
set /p a= < tmp
del tmp
echo sha%bits%-%a%
pause
```

Para utilizar ese código:

Guarda ese código en un archivo llamado `sri-hash.bat` en la carpeta SendTo de Windows en su entorno (por ejemplo, `C:\Users\USER\AppData\Roaming\Microsoft\Windows\SendTo`).

Haz clic con el botón derecho en un archivo en el Explorador de archivos, selecciona Enviar a… y, a continuación, seleccione `sri-hash`. Verás el valor de integridad en un cuadro de comando.

Selecciona el valor de integridad y haz clic con el botón derecho para copiarlo al portapapeles. Presiona cualquier tecla para cerrar el cuadro de comando.

>[!NOTE]
>Si el repositorio de las fuentes cambia de dominio, modifica el atributo `cdn` con la URL correspondiente.
