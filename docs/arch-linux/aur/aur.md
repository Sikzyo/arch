# Arch User Repository

El Arch User Repository (AUR) es un repositorio mantenido por la comunidad que contiene descripciones de paquetes llamadas PKGBUILDS. Estas permiten compilar software desde código fuente usando `makepkg` y luego instalarlos mediante `pacman`. Muchos paquetes comienzan en el AUR y si ganan popularidad y cumplen los requisitos, pueden llegar a los repositorios oficiales.

1. Instalación y uso manual (Paso a paso)
   Para utilizar el AUR sin herramientas externas, sigue estos pasos:
   1. Instala el meta-paquete `base-devel` y `git`, que incluye `make` y otras herramientas esenciales para compilar.
   2. Busca el paquete en la web de AUR y clona su repositorio GIT
      `git clone https://aur.archlinux.org/nombre_del_paquete.git`
   3. Revisa cuidadosamente el archivo `PKGBUILD` y cualquier archivo `.install` para asegurarte de que no contenga comandos maliciosos.
      Puedes leerlo con:
      `less PKGBUILD`
   4. Entra en el directorio del paquete y ejecuta:
      - `makepkg -si`
      - La opción `-s` instala automáticamente las dependencias necesarias y `-i` instala el paquete después de compilarlo correctamente.
2. Consideraciones criticas
   - Los paquetes del AUR son creados por usuarios. Son extraoficiales y no están auditados por el equipo de Arch. Úsalos bajo tu propia responsabilidad.
   - `pacman` no actualiza automáticamente los paquetes del AUR. Debes entrar en el directorio del paquete, ejecutar `git pull` para obtener los cambios y volver a compilar con `makepkg`.
   - Puede ser necesario reconstruir un paquete del AUR cuando se actualizan bibliotecas del sistema, incluso si el paquete en sí no ha cambiado.
3. Se recomida instalar un AUR helper, para la instalación de `yay` consulta [yay](yay.md)
