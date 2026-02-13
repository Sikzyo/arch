# Arch build System

Es un sistema de scripts de construcción (similar al sistema "Ports" de BSD) que se ejecuta en el entorno local del usuario. Su objetivo principal es permitir la creación de paquetes instalables a partir del código fuente de forma organizada y estandarizada.

1. ¿Como funciona?
   - PKGBUILDS:
     - Son los scripts principales del sistema. Contienen toda la información necesaria sobre un programa: versión, licencias, URL del proyecto y las instrucciones detalladas para su compilación y empaquetado.
   - makepkg:
     - Es la herramienta que interpreta los archivos PKGBUILD. Se encarga de descargar el código fuente, resolver dependencias necesarias para compilar, construir el programa y generar un paquete comprimido listo para instalar.
   - Una vez que `makepkg` crea el paquete, este puede instalarse y administrarse de forma limpia mediante `pacman`, el gestor de Arch. Esto permite actualizarlo o eliminarlo sin dejar archivos residuales.
