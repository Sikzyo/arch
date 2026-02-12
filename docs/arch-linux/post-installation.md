# Pos Instalación

La idea es explicar cuales son los pasos recomendados a seguir después de instalar Arch.

## 1. Administración del sistema

### 1.1 Usuarios

Una instalación nueva solo crea el usuario root. Utilizar este usuario de forma habitual se considera inseguro, por lo que se recomienda crear y usar usuarios sin privilegios para el uso cotidiano del sistema.

El comando recomendado es:

`useradd -m -G wheel -s /bin/bash [nombre_de_usuario]`

- `-m` crea el directorio personal del usuario.
- `-G` añade al usuario al grupo de administración `wheel`, comúnmente usado para otorgar privilegios de `sudo`.
- `-s /bin/bash` establece Bash como la terminal (shell) predeterminada.

Para asignar una contraseña, ejecute el siguiente comando:

`passwd [nombre_de_usuario]`

Si no tienes `sudo` instalado, puedes instalarlo ejecutando el siguiente comando:

`pacman -S sudo`

El grupo `wheel` permite otorgar acceso a la utilidad `sudo`, pero este acceso no esta habilitado por defecto. Para activarlo, ejecuta:

`EDITOR=nano visudo`

Luego, elimina el símbolo `#` al inicio de la línea:

`%wheel ALL=(ALL:ALL) ALL`

## Documentación

Para profundizar más en el tema, se recomienda visitar la página de la documentación oficial sobre recomendaciones generales: [General recommendations](https://wiki.archlinux.org/title/General_recommendations)
