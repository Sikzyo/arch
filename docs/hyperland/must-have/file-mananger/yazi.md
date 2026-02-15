# yazi

Para instalar yazi en Arch de forma rápida y completa, sigue estos pasos:

1. Requisitos

   Debes tener instalado el paquete `file`, necesario para la detección de tipos de archivos.

   Para instalarlo ejecuta el siguiente comando:

   `sudo pacman -S file`

---

2. Instalación

   El método más sencillo es usar el repositorio oficial de Arch. El siguiente comando instala yazi junto con todas las dependencias recomendadas:

   `sudo pacman -S yazi ffmpeg 7zip jq poppler fd ripgrep fzf zoxide resvg imagemagick`

---

3. Soporte para el portapapeles

   Para que yazi pueda copiar contenido al portapapeles del sistema, asegúrate de tener instalado.

   `wl-clipboard`

---

4. Documentación

   Para obtener más información se recomienda visitar la pagina oficial de [yazi](https://yazi-rs.github.io)
