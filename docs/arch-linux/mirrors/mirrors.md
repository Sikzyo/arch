# Espejos

Los mirror (espejos) son servidores que alojan copias de los repositorios oficiales de Arch Linux, lo que permite a los usuarios descargar e instalar paquetes.

Su importancia se basa en dos factores clave: velocidad y sincronización. El orden en que aparecen los servidores en tu lista determina su prioridad; si un espejo falla o responde lentamente, `pacman` intentará usar el siguiente. Además, es fundamental utilizar espejos actualizados para evitar errores de descarga o "actualizaciones parciales" que puedan desestabilizar el sistema.

1. Comandos y herramientas básicas
   - `pacman -Syyu`
     - Se usa después de modificar la lista de mirrors para forzar la actualización de las bases de datos de paquetes y asegurarse de que coincidan con el nuevo servidor.
   - `rankmirrors`
     - Script incluido en `pacman-contrib` que permite probar y ordenar una lista de espejos según su velocidad de conexión.
   - `reflector`
     - Herramienta recomendada para automatizar la obtención de la lista más reciente de mirror, filtrarla y actualizar automáticamente el archivo de configuración.

2. Guía de configuración.
   1. El archivo principal se encuentra en:
      `/etc/pacman.d/mirrorlist`
   2. Habilitar mirrors manualmente:
      - Edita el archivo con permisos de administrador
      - Busca tu región geográfica y elimina el `#` de las líneas que comienzan con `Server =` de los espejos que desees utilizar
      - Coloca tus 5 espejos preferidos al inicio de la lista para gestionarlos más fácilmente
   3. Puedes usar el generador de listas en la web de Arch Linux o herramientas como `rankmirrors` o `rate-mirrors` para encontrar los servidores más rápidos cercanos a tu ubicación.
   4. Después de editar la lista, ejecuta siempre `pacman -Syyu` para aplicar los cambios y sincronizar tu sistama con los nuevos servidores seleccionados.
