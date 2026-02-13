# Repositorios oficiales

Los repositorios oficiales de Arch son almacenes de software esencial y popular que se gestionan con `pacman`. Se actualizan de forma constante, lo que garantiza que los paquetes estén siempre en sus versiones más recientes y sean compatibles entre sí.

1. Repositorios estables:
   - Core:
     - Contiene los paquetes fundamentales para que el sistema arranque, se conecte a internet y permita reparar archivos.
   - Extra:
     - Incluye software que no forma parte de la base del sistema, como entornos de escritorio, navegadores web y reproductores multimedia. Desde 2023, también incorpora los paquetes que antes pertenecían al repositorio community.
     - Multilib:
       - Es necesario si planeas usar aplicaciones de 32 bits en un sistema de 64 bits, como ocurre con Steam. Debe habilitarse manualmente en el archivo
         - `/etc/pacman.conf`

---

Cómo habilitar el repositorio multilib en Arch

1. Abre el archivo de configuración de pacman ubicado en `/etc/pacman.conf` con un editor de texto y privilegios de superusuario.
2. Busca la sección `[multilib]` y elimina el símbolo de comentario `#` en las líneas correspondientes para habilitarla.
3. Guarda los cambios y cierra el editor.
4. Actualiza el sistema ejecutando el comando de bases de datos, por ejemplos:
   `sudo pacman -Syu`

   Esto permitirá que los nuevos paquetes de 32 bits estén disponibles para su instalación.

Una vez habilitado, puedes listar los paquetes con el comando `pacman -Sl multilib`. Notaras que la mayoría de las bibliotecas de 32 bits comienzan con el prefijo `lib32-`
