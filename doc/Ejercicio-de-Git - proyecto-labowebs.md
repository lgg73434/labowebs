---
author: Sara García Barbas
title: Ejercicio de Git - proyecto labowebs
---

# Ejercicio de Git - Proyecto labowebs

> Sara García Barbas

[TOC]

## Trabajo en local

> Trabajo individual en tu ordenador - Esta parte se resuelve con comandos. 
>
> Tu solución debe incluir el enunciado de cada cuestión, un bloque de código con los comandos GIT utilizados y captura/s de pantalla donde se vea la ejecución de los comandos y su salida.

1. Inicializa un nuevo repositorio Git en una carpeta llamada "`labowebs`" y agrega los archivos proporcionados en el aula virtual. Renombra la rama master a `main` , si es necesario. Realiza el primer commit. Muestra el log del repositorio.

   ```bash
   git init
   git add .
   git commit -m "Repositorio creado"
   git log
   ```

   ![image-20241114092412042](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241114092412042.png)

   

2. Incluye un fichero `.gitignore` para que los ficheros `README.md` , `LICENCE.txt` y `passwords.txt` sean ignorados por el control de versiones. Realiza el commit y muestra los logs del repositorio en una línea.

   ```bash
   gedit .gitignore
   cat .gitignore
   git add .
   git commit -m "Creado fichero .gitignore"
   ```

   ![image-20241114092801929](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241114092801929.png)

   

3. En el repositorio, crea los archivos `README.md` , `LICENCE.txt` y `passwords.txt` con algún contenido. Muestra el estado del repositorio. Muestra el listado de archivos ignorados.

   ```bash
   gedit README.md
   cat README.md
   gedit LICENSE.txt
   cat LICENSE.txt
   gedit passwords.txt
   cat passwords.txt
   git status
   git ls-files --others -i --exclude-standard
   ```

   ![image-20241114093152504](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241114093152504.png)

   

4. Crea una rama `feature-estilos` . Cámbiate a ella. 

   ```bash
   git checkout -b feature-estilos
   ```

   ![image-20241114093230722](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241114093230722.png)

   - Modifica el archivo `estilos.css` : 

     - propiedad color del `body` y de `h2` : `#5a5a5a` 

       ![image-20241114093359536](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241114093359536.png)

       ![image-20241114093422418](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241114093422418.png)

     - propiedad `background-color` de `header` y `footer`: `#2a75cc`

       ![image-20241114093524466](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241114093524466.png)

     - Comprueba el estado del repositorio. Añade los cambios, realiza un commit con el mensaje  "actualizados estilos a azules"

       ```bash
       git status
       git add .
       git commit -m "Actualizados estilos"
       ```
       
       ![image-20241114093718948](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241114093718948.png)
       
       ![image-20241114093748060](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241114093748060.png)
       
       

5. Vuelve a la rama `main` . En el archivo `index.html` añade un comentario donde se indique tu nombre como autor de la página. Comprueba el estado del repositorio. Añade los cambios, realiza un commit con el mensaje ' añadido autor en index'. Muestra los logs del repositorio en una línea, gráficamente y con 'decoración'

   ```bash
   git checkout main
   git status
   git add index.html
   git commit -m "Añadido autor en index"
   git log --oneline --all --decorate
   ```

   ![image-20241114094128570](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241114094128570.png)

   

6. Fusiona la rama `feature-estilos` en la rama `main`. Muestra los logs del repositorio en una línea, gráficamente y con 'decoración'

   ```bash
   git merge feature-estilos
   git log --oneline --all --decorate
   ```

   ![image-20241114094351726](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241114094351726.png)

   ![image-20241114094501691](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241114094501691.png)

<div style="page-break-after: always; break-after: page;"></div>

## Trabajo en remoto

> Esta parte se realizará con la herramienta gráfica `Sourcetree` y con `GitHub`. 
>
> Para cada cuestión, incluye el enunciado y las capturas de pantalla donde se muestre la solución. Si es necesario, incluye alguna explicación

1. Continúa con el repositorio `labowebs`. Añade el repositorio a Sourcetree. 

   ![image-20241114101239538](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241114101239538.png)

   

2. Crea un repositorio remoto y sube al remoto los ficheros de tu repositorio local. Debes subir todas las ramas. 

   - Clicamos en `Repository / Repository Settings`

   ![image-20241114101906020](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241114101906020.png)

   

   - En la pestaña de `Remotes` clicamos en el botón `Add`

   ![image-20241114102213959](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241114102213959.png)

   

   - Rellenamos el campo `Remote name`
   - Rellenamos el campo `URL / Path`
   - Rellenamos el campo `Username`
   - Clicamos en en `OK`

   ![image-20241114102101969](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241114102101969.png)

   

   - En el menú superior, clicamos en `Push`
   - Seleccionamos el checkbox `Select All`
   - Clicamos en `Push`

   ![image-20241114131212633](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241114131212633.png)

   ![image-20241114131305802](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241114131305802.png)

   

   - Los cambios subidos:

   ![image-20241114131517905](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241114131517905.png)

   

3. Crea una rama `feature-index`. Añade el siguiente código dentro de la `<section class="about">`. Añade los cambios y crea un commit. Sube los cambios al remoto.

   ![image-20241114095027354](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241114095027354.png)

   

   - En el menú superior clicamos en `Branch`
   - Rellenamos el campo `New Branch`
   - Clicamos en `Create Branch`

   ![image-20241114132621676](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241114132621676.png)

   

   - Una vez realizados lo cambios en `index.html`, clicamos en `Stage All`

   ![image-20241114133350662](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241114133350662.png)

   

   - En el menú superior clicamos en `Commit`
   - Añadimos un mensaje al commit
   - Clicamos en `Commit`

   ![image-20241114133530543](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241114133530543.png)

   

   - En el menú superior, clicamos en `Push`
   - Seleccionamos el checkbox `Select All`
   - Clicamos en `Push`

   ![image-20241114133855690](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241114133855690.png)

   

4. En el repositorio local, fusiona la rama `feature-index` en la rama `main`. 

   - Nos cambiamos a la rama `main`
   - Hacemos click derecho sobre la rama que queremos fusionar, en este caso `feature-index`
   - Clicamos en la opción `Merge feature-index into current branch`

   ![image-20241114135307845](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241114135307845.png)

   

5. Edita el fichero `contacto.html`. Muestra los ficheros con cambios pendientes y las diferencias. Añade los cambios y haz un commit. 

   - Hacemos algún cambio desde Visual Studio en `contacto.html` y guardamos.

   ![image-20241115084022504](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115084022504.png)

   

   - Vemos como nos aparece el cambio en SourceTree

   ![image-20241115084441579](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115084441579.png)

   

   - Clicamos en el botón `Stage All` para añadir los cambios

   ![image-20241115084544915](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115084544915.png)

   

   - En el menú superior clicamos en `Commit`
   - Añadimos un mensaje
   - Clicamos en el botón `Commit`

   ![image-20241115084710200](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115084710200.png)

   

   - Vemos como nos aparece el commit que acabamos de hacer

   ![image-20241115084748767](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115084748767.png)

   

6. Te das cuenta del error. Deshaz el commit anterior. Captura el estado actual del repositorio. 

   - Clicamos con el botón derecho en el commit que queramos revertir
   - En el desplegable seleccionamos la opción `Reverse commit...`

   ![image-20241115085006536](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115085006536.png)

   

   - El commit ha sido revertido:

   ![image-20241115085118250](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115085118250.png)

   

   - Vemos que en el archivo `contacto.html` ya no aparece la línea añadida anteriormente:

   ![image-20241115085220625](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115085220625.png)

   

7. Crea una rama `feature-mapa`. Incluye este código en el archivo `contacto.html`. Añade los cambios. Realiza un commit. Sube los cambios al remoto. Muestra en el remoto los cambios del archivo `contacto.html` en la rama `feature-mapa`.

   ![image-20241114095121557](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241114095121557.png)

   

   - En el menú superior clicamos en `Branch`
   - Rellenamos el campo `New Branch`
   - Clicamos en `Create Branch`

   ![image-20241115085502478](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115085502478.png)

   - Añadimos el código en `contacto.html` y guardamos

   ![image-20241115090017911](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115090017911.png)

   

   - Clicamos en el botón `Stage All`

   ![image-20241115090114203](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115090114203.png)

   

   - En el menú superior clicamos en `Commit`
   - Añadimos un mensaje
   - Clicamos en el botón `Commit`

   ![image-20241115090242832](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115090242832.png)

   

   - En el menú superior clicamos en el botón `Push`

   ![image-20241115090328282](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115090328282.png)

   

   - Seleccionamos la rama de la que queramos hacer el push y clicamos en el botón `Push`

   ![image-20241115090423436](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115090423436.png)

   

   - En GitHub, clicamos en `Compare & pull request`
   - Y luego en `Create pull request` para que se añadan los cambios desde el repositorio local al repositorio remoto

   ![image-20241115090543424](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115090543424.png)

   ![image-20241115090652671](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115090652671.png)

   

   - Resultado del push una vez realizados los pasos anteriores

   ![image-20241115090751695](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115090751695.png)

   

8. En GitHub, en la rama `main` , fusiona la rama `feature-mapa` . Baja los cambios del remoto a local. Deja los dos repositorios sincronizados.

   - En el menú superior clicamos en `Pull request`
   - Y después en `View pull request`


![image-20241115091231296](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115091231296.png)

![image-20241115091416579](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115091416579.png)	

- Por último clicamos en `Merge pull request`
- Podemos añadir un comentario
- Y clicamos en `Confirm merge`

![image-20241115091624950](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115091624950.png)

![image-20241115091933984](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115091933984.png)



- Resultado del mergeo de las ramas:
- En esta misma pantalla podemos elegir si borrar la rama mergeada o no.

![image-20241115092101356](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115092101356-1731658862651-1.png)



- Para hacer el pull de Sourcetree, clicamos en `Pull`, o en `Repository / Pull...`

![image-20241115092233137](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115092233137.png)

![image-20241115092611402](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115092611402.png)



- Clicamos en el botón `Pull`

![image-20241115093035795](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115093035795.png)



- Ya podemos ver en la interfaz la sincronización con nuestro repositorio remoto:

![image-20241115093411736](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115093411736.png)


<div style="page-break-after: always; break-after: page;"></div>


## Conflicto

1. Crea una rama `hotfix-js` . Cámbiate a ella. Añade este código en el fichero `script.js` . Confirma el cambio y haz un commit. (Fíjate en los números de línea...)

   ![image-20241115093606999](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115093606999.png)

   

   - En el menú superior clicamos en `Branch`
   - Rellenamos el campo `New Branch`
   - Clicamos en `Create Branch`

   

   ![image-20241115093938318](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115093938318.png)

   

   - Hacemos los cambios que nos piden:

   ![image-20241115094220441](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115094220441.png)

   

   - Clciamos en el botón `Stage All`

   ![image-20241115094305343](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115094305343.png)

   

   - En el menú superior clicamos en `Commit`
   - Añadimos un mensaje
   - Clicamos en el botón `Commit`

   ![image-20241115094434527](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115094434527.png)

   

   - Vemos en la interfaz como nos aparece el commit que acabamos de hacer

   ![image-20241115094521288](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115094521288.png)

   

2. Vuelve a la rama `main` . En el fichero `script.js` en las mismas líneas que en la cuestión anterior, añade el código siguiente. Confirma el cambio y haz un commit.

![image-20241115093634888](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115093634888.png)



- Hacemos doble click sobre la rama a la que nos queremos mover, en este caso `main`

![image-20241115094612135](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115094612135.png)



- Realizamos los cambios solicitados en el fichero:

![image-20241115094723194](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115094723194.png)



- Clicamos en el botón `Stage All`

![image-20241115094800971](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115094800971.png)





- En el menú superior clicamos en `Commit`
- Añadimos un mensaje
- Clicamos en el botón `Commit`

![image-20241115094953187](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115094953187.png)



- Ya nos aparece en la interfaz el commit que acabamos de realizar

![image-20241115095049036](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115095049036.png)



3. Fusiona la rama `hotfix-js` en `main` . Debe producirse un conflicto. Resuélvelo. Cuando termines la resolución del conflicto sube los cambios al remoto - Deja los repositorios sincronizados - 

   > Esta parte se realizará con la herramienta gráfica Sourcetree y con GitHub . Para cada cuestión, incluye el enunciado y las capturas de pantalla donde se muestre la solución. Si es necesario, incluye alguna explicación
   
   - Nos cambiamos a la rama `main`
   - Hacemos click derecho sobre la rama que queremos fusionar, en este caso `hotfix-js`
   - En el desplegable, seleccionamos la opción `Merge hotfix-js into current branch`	

![image-20241115095227092](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115095227092.png)



- Nos sale un aviso que nos indica que tenemos un conflicto sin resolver

![image-20241115095255776](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115095255776.png)



- Para solucionar el conflicto, abrimos el fichero en Visual Studio Code:
  - El propio Visual nos dará distintas opciones para solucionar el conflicto. En este caso he decido pulsar en `Aceptar cambio entrante`

![image-20241115095451910](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115095451910.png)



- Se aplica en el archivo la solución que hayamos elegido

![image-20241115095521635](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115095521635.png)



- Volvemos a SourceTree y realizamos de nuevo el commit:

![image-20241115095755966](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115095755966.png)



- Vemos que ahora la fusión de las ramas si se ha llevado a cabo

![image-20241115095833836](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115095833836.png)



- Realizamos el Push para subir los cambios al repositorio remoto

![image-20241115095941119](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115095941119.png)



- Ya podemos ver en GitHub los cambios subidos desde nuestro repositorio local

![image-20241115100038505](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115100038505.png)

<div style="page-break-after: always; break-after: page;"></div>

## Subida de documentación

En la carpeta del proyecto `labowebs` añade una carpeta `docs` . Copia en esa carpeta el fichero markdown y la carpeta con las imágenes. Incluye también el `pdf` . Añade todo al repositorio. Súbelo al remoto.

Este apartado se puede realizar en SourceTree o con comandos.

![image-20241115101046688](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115101046688.png)

![image-20241115115214747](./Ejercicio-de-Git - proyecto-labowebs.assets/image-20241115115214747.png)



Ahora repetimos los pasos para realizar el Stage All, después realizariamos un commit y por último un push para subirlo todo a nuestro repositorio remoto.
