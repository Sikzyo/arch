# yay

Un AUR helper automatiza la búsqueda, resolución de dependencias y compilación de paquetes. Sin embargo, estas herramientas no cuentan con soporte oficial por parte de Arch.

1. ¿Que es yay?
   `yay` (Yet Another Yogurt) es un envoltorio de `pacman` escrito en Go. Es popular por su buena resolución de dependencias y porque permite revisar las diferencias (diffs) de los archivos antes de instalar un paquete.

2. Cómo instalar yay
   Dado que `yay` está en el AUR, debes instalarlo manualmente:
   1. Asegúrate de tener `base-devel` y `git` instalados.
   2. Clona el repositorio: `https://aur.archlinux.org/yay.git`
   3. Entra en el directorio: `cd yay`
   4. Compila e instala: `makepkg -si`

3. Como usar yay correctamente
   - Para instalar un paquete (de repositorios oficiales o AUR)
     - `yay`
   - Buscar por palabras claves:
     - `yay [palabra-clave]` mostrará una lista numerada de resultados para elegir
   - Limpiar dependencias innecesarias:
     - `yay -Yc`
   - Nunca uses `sudo`, yay debe ejecutarse como usuario normal, pedirá sudo cuando lo necesite.

4. Nota importante
   Cuando uses `yay`, se te preguntará si deseas revisar los cambios en el `PKGBUILD`. No omitas este paso. Revisar lo que vas a compilar es fundamental para mantener la seguridad y estabilidad de tu sistema.
