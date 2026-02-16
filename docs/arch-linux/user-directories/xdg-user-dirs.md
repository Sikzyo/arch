# xdg-user-dirs

Esta herramienta permite gestionar los directorios personales estándar del usuario (Descargas, Música, Documentos, etc.) de forma automática y coherente con las especificaciones XDG.

1. Instalación

   Instala el paquete utilizando el siguiente comando:

   `sudo pacman -S xdg-user-dirs`

   Algunos entornos de escritorio, como GNOME, ya lo incluyen por defecto.

2. Creación de directorios

   Para generar automáticamente las carpetas estándar dentro de tu directorio personal, ejecuta:

   `xdg-user-dirs-update`

   Este comando crea el archivo `~/.config/user-dirs.dirs`, que las aplicaciones utilizan para localizar tus carpetas estándar.
