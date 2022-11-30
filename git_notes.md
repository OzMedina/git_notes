## Configuracion

**Origen:** [Youtube](https://git-scm.com/downloads)

1. **Descarga:** [Aquí](https://git-scm.com/downloads)

2. Instalar considerando **Git con Bash**

3. **Comandos de configuración inicial**

    Verificar versión de Git:
    
        git --version

    Poner usuario por defecto para todos los proyectos:

        git config --global user.name "Oz Medina"

    Poner correo por defecto para todos los proyectos:

        git config --global user.email tucorreo@gmail.com

    Poner Visual Studio Code como editor por defecto (se debe instalar VS Code antes y reiniciar) esto hará que se espere cerrar el archivo de configuración antes de seguir usando el bash:
        
        git config --global core.editor "code --wait" 

    Revisar el archivo de configuración:

        git config --global -e

    Configurar el salto de línea "CRLF" según sistema operativo
    
    Para windows:
        
        git config --global core.autocrlf true

    Para Mac y Linux:

        git config --global core.autocrlf input

    Para ver los comandos disponibles:

        git config -h


4. **Comandos de posición y navegación**

    Para listar las carpetas y archivos de la ubicacion actual:
        
        ls

    Para saber la ruta actual de donde te encuentras:
        
        pwd

    Para moverse de directorio(carpeta):
        
        cd el nombre de la carpeta de destino

    Para retroceder a la raiz de carpeta anterior:

        cd ..

5. **Comandos de uso básico**

    Crear una carpeta dentro de la posición actual:

        mkdir nombre-del-directorio

    Inicializar o crear un proyecto "git" en directorio existente:

        git init

    El directorio creado anteriormente no será visible con el comando "ls", por lo que si queremos ver los directorios ocultos se debe usar el comando:

        ls -a

    Desde el terminal se puede abrir el directorio en el editor de texto con el comando:

        code .

6. **Comandos de operación**

    Para *conocer el estado actual* de nuestro repositorio:

        git status

    Para *agregar archivos al commit* se utiliza el siguiente comando:

        git add nombre de archivo(con su extensión)
        git add *(extensión) para agregar todos los archivos con esa extensión
        git add . agraga todos los archivos marcados en rojo en git status o todos los archivos en el directorio

    Para *agregar varios archivos al commit* 

        git add archivo1 archivo2

    Se puede *realizar un commit 2 dos formas:*

        git commit -m "Nombre del Commit que describa el cambio"
        
        git commit + Enter 
        
        nos llevará al editor de texto, donde colocaremos en la parte superior la descripción del commit, debemos guardar y cerrar, eso realizará el commit
    ---
    Para ver el contenido de nuestro archivo:

        git cat nombre-del-archivo
    ---

    Visualizar los commits realizados:

        git log --oneline

    ---
    Saber en qué rama nos encontramos:

        git branch

    *Presionamos q para salir*

    ---

    Crear una nueva rama:

        git checkout -b nombre-rama

    *algunas empresas lo colocan como features/nombre-de-la-funcionalidad,
    otras colocan directamente el número de ticket a atender o solucionar*

    ---

    Borrar una rama:

        git checkout -d nombre-rama

    ---

    Para cambiar de rama:

        git checkout nombre-de-la-rama
    ---
    
    Para traer los cambios desde una rama secundaria hacia la rama principal o rama "main" debemos dirigirnos a la rama principal y hacer un merge a la rama desde donde queremos traer los cambios

        git checkout main

        git merge nombre-rama-con-cambios
    ---
    
    Para subir nuestro repositorio a GitHub

    *Creamos nuestro repositorio en la web de GitHb*  
    *Copiamos el link git remote para indicar el origen y destino de los datos*
    
        git remote add origin https://github.com/cuenta/repositorio.git

    *Luego hacemos un push que es el comando para subir los datos*  
    *Al ser el primer envío de datos la rama main no esxite en nuestro repositorio remoto, por lo que debemos crearla*

        git push -u origin main
        
    Para verificar si nuestro repositorio se guardó:
    
        git remote
        git remote -v
        
    Traer la versión del repositorio remoto y hacer merge para crear un commit con los archivos de ambas partes.  
    Podemos usar git fetch y git merge o solo:  
    
        git pull con el flag --allow-unrelated-histories:
    
---
7. **Seguridad**

    Listar las llaves .SSH de seguridad existentes 

        ls -al ~/.ssh

    Generar una nueva llave SSH

        ssh-keygen -t ed25519 -C "your_email@example.com"

    Correr la llave generada para luego agregarla

        eval "$(ssh-agent -s)"
    
    Agregar la llave generada

        ssh-add ~/.ssh/id_rsa



    
