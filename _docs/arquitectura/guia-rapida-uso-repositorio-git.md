---
title: "Guía rápida de uso del repositorio GIT"
---

# Utilización de repositorios Git

## Objetivo

Este documento pretende explicitar la utilización de Git como repositorio de
código y el modelo de ramas que se implementará para que cualquier desarrollador con las capacidades necesarias pueda colaborar con mejoras o arreglos de defectos en el código de los diferentes productos. 

## Motivación

Teniendo en cuenta el objetivo anterior y siendo que la herramienta (TFS) utilizada hoy en día en Sistran, como repositorio del código de Framework, no ofrece un modelo claro para el manejo de ramas, es que surge la necesidad de utilizar una herramienta que brinde estas características.
En todo esto se basa la decisión de utilizar Git como repositorio de código.
La idea es mantener siempre una rama sana, que será la rama Master, de la cual se irán creando y liberando las versiones del framework de Sistran.

## Utilización de Git

Aquí se ofrece una guía breve de utilización de Git, en el área de Framework.
Para mayor detalle sobre Git, referirse al [Curso de Fundamentos de Git](https://moodle.sistran.com.ar/moodle/enrol/index.php?id=102)

### Instalación de las, herramientas

Se debe descargar el instalador del sitio de Git, que se encuentra en el
siguiente link:

<https://git-scm.com/download/win>

Una vez descargado, ejecutar el instalador, y seguir los pasos.

Se van a presentar una serie de opciones, de las cuales se irán seleccionando
las siguientes:

En la sección de arhivos a asociar a Git:

![SeleccionComponentes](../../assets/images/Uso-repositorio-git/1-InstaladorGit-SeleccionComponentes.png)


Luego, seleccionar el editor de texto de preferencia para aquellas situaciones
como ser la inserción de comentarios de un commit de la resolución de conflictos
en un merge

![SeleccionEditorDeTextos](../../assets/images/Uso-repositorio-git/2-InstaladorGit-UsarNotepadPlusPlus.png)

En las opciones de uso de Git desde consola, seleccionar la segunda opción:

![VariablePATH](../../assets/images/Uso-repositorio-git/3-InstaladorGit-PATHEnvironment.png)

En el caso de la herramienta a utilizar para validar certificados, seleccionar
la segunda opción

![SSLLibrary](../../assets/images/Uso-repositorio-git/4-InstaladorGit-SSLLibrary.png)

Para el caso de la codificación de los fines de línea, seleccionar la primera
opción:

![LineEnding](../../assets/images/Uso-repositorio-git/InstaladorGit-FinDeLinea.png)

Para el emulador de Git Bash, seleccionar la segunda opción:

![Terminal](../../assets/images/Uso-repositorio-git/5-InstaladorGit-Terminal.png)

En las características extra, seleccionar las primeras dos:

![OpcionesExtra](../../assets/images/Uso-repositorio-git/6-InstaladorGit-ExtraOptions.png)

La primera, ofrece una mejora de la performance de Git.

La segunda, instala el Git Credential Manager, a utilizarse al momento de tener
que autenticarse ante un repositorio de Git, desde Windows.

Hacer click en “Install”.

Si la instalación se realiza correctamente, se mostrará la siguiente pantalla:

![PantallaFinal](../../assets/images/Uso-repositorio-git/7-InstaladorGit-PantallaFinal.png)

Destildar el “View Release Notes” y hacer click en “Finish”

### Clonación de un repositorio


Para proceder a clonar un repositorio, primero, se debe disponer de la URL del
mismo.

En el caso del repositorio de framework, va a ser la siguiente:

http://tfs.sistran.com.ar:8080/tfs/DefaultCollection/FWK/_git/Framework

Los pasos para clonarlos son los siguientes:

1.  Disponer de la ubicación en la que se va a clonar el repositorio en el
    escritorio local.

2.  Abrir una ventana de comandos

3.  Dirigirse a la ubicación a descargar en repositorio

4.  Insertar el siguiente comando:  
    git clone \<URLDelRepositorio\>

### Subida de cambios

Una vez se disponga de los cambios que se desee subir, se debe proceder con los
siguientes pasos:

1.  Abrir una ventana de comandos

2.  Dirigirse a la carpeta local del repositorio Git

3.  Allí se puede ingresar el comando “git status” para chequear los cambios

4.  Con el comando git add se van marcando los cambios que se van a subir. Puede
    ser de a uno, o bien con expresiones, como por ejemplo:  
    a. . o \*.\* para todos los cambios  
    b. \*.cs para todos los archivos cs

5.  Luego, se debe hacer commit de los cambios insertando un comentario. Para
    ello se debe ingresar el siguiente comando:  
    git commit –m “\<Comentario\>”

6.  Finalmente, para enviar los cambios al servidor, se debe insertar el
    siguiente comando:  
    git push origin \<branch\>

### Modelo de ramas

Por política de la compañía, no se podrá subir cambios directamente a la rama
master. Esto es para asegurar la sanidad de esa rama, tanto para tener un punto
de partida funcional y para que esté disponible para la generación de nuevas
versiones.

La rama master será la fuente de verdad respecto del código. Allí estarán
integrados los cambios que estén probados y cuyas pruebas hayan sido exitosas.

Siempre que se deba desarrollar algo, se deberá crear una rama a partir de
master. Para ello se debe ingresar el siguiente comando:

git checkout –b \<NombreLaRama\>

Idealmente, cada cambio estará ligado a un ticket en JIRA.

El nombre de la rama debería ser el del ticket de JIRA, como ser: FRW-115. De
esta manera, podemos tener un seguimiento de qué dio origen al cambio.

Una vez los cambios estén desarrollados, y se hayan probado, se creará una
“Solicitud de integración de cambios” desde TFS para que dichos cambios pasen
por una revisión y se integren a la rama master.

Antes de proceder a crear la solicitud, se deberán integrar los últimos cambios
de master en el branch. Para ello, primero, se deberá haber hecho commit de
todos los cambios. Luego, se deberán ejecutar los siguientes comandos:

1.  git checkout master  
    Con este comando, nos movemos a la rama master

2.  git pull origin master  
    Para obtener los últimos cambios de master

3.  git checkout \<branch\>  
    Para movernos a la rama con los cambios

4.  git merge master  
    Para integrar los cambios de master en el la rama

Probablemente, hay conflictos con los cambios.

Estos conflictos serán listados. Para su solución, se deberá ir revisando uno
por uno cada archivo.

Una vez solucionados todos los conflictos, se deberán ejecutar los siguientes
comandos:

1.  git add .

2.  git commit –m “Fix merge”

3.  git push origin \<branch\>

Hecho esto, será posible crear la solicitud de integración de cambios. Habiendo
conflictos irresueltos, TFS no permitirá proceder a crear la solicitud.

### Creación de solicitud de incorporación de cambios (pull request)

Para proceder a crear una solicitud de incorporación de cambios, se deben seguir los siguientes pasos:

1.  Acceder al portal de TFS de Sistran [http://tfs.sistran.com:8080/tfs](http://tfs.sistran.com:8080/tfs)
2.  Acceder al área del proyecto al que pertenezca el repositorio de código.
    ![SelectTFSProject](../../assets/images/Uso-repositorio-git/Create-Pull-Request-Select-Project.png)
3.  Dirigirse a la solapa "Código"
    ![GoToCodeTab](../../assets/images/Uso-repositorio-git/Create-Pull-Request-Code-Tab.png)
4.  Seleccionar el repositorio de código
    ![SelectRepository](../../assets/images/Uso-repositorio-git/Create-Pull-Request-Select-Code-Repository.png)
5.  Hacer click en "Solicitudes de incorporación de cambios"
    ![PullRequests](../../assets/images/Uso-repositorio-git/Create-Pull-Request-Go-To-Pull-Requests.png)
6.  Hacer click en "Nueva solicitud de incorporación de cambios"
    ![CreateNewPullRequest](../../assets/images/Uso-repositorio-git/Create-Pull-Request-Click-New-Pull-Request.png)
7.  Seleccionar la rama origen, cuyos cambios se vayan a integrar en la rama master
    ![SelectBranch](../../assets/images/Uso-repositorio-git/Create-Pull-Request-Select-Branch.png)
8.  Corroborar todos los cambios a integrarse y hacer click en "Crear"
    ![CreatePullRequest](../../assets/images/Uso-repositorio-git/Create-Pull-Request-Create-Pull-Request.png)