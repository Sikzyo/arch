# pacman

`pacman` es el gestor de paquetes de Arch Linux, diseñado para administrar de forma sencilla tanto los paquetes de los repositorios oficiales como las compilaciones realizadas por el usuario.

---

1. Operaciones básicas de paquetes
   - Para instalar un paquete (incluyendo sus dependencias), utiliza:
     - `sudo pacman -S [nombre-del-paquete]`
   - para sincronizar las bases de datos y actualizar todos los paquetes del sistema. usa:
     - `sudo pacman -Syu`
     - Evita las actualizaciones parciales (por ejemplo, `sudo pacman -Sy`) ya que pueden provocar errores de dependencias. Siempre se recomienda actualizar el sistema completo.
   - `sudo pacman -R [nombre-del-paquete]` elimina únicamente el paquete
   - `sudo pacman -Rs` elimina el paquete y sus dependencias que no estén siendo utilizadas por otros programas (recomendado)

---

2. Búsqueda e información
   - Buscar en los repositorios:
     - `sudo pacman -Ss [nombre]`
     - Busca paquetes por nombre o descripción en los repositorios
   - Buscar en el sistema:
     - `sudo pacman -Qs [nombre]`
     - Busca en tre los paquetes ya instalados
   - Información detallada:
     - `sudo pacman -Si [nombre]` muestra información del paquete en los repositorios remotos.
     - `sudo pacman -Qi [nombre]` muestra información del paquete instalado local.

---

3. Mantenimiento
   - Limpieza de cache:
     - `pacman` guarda los paquetes descargados en:
     - `/var/cache/pacman/pkg/`
     - No los elimina automáticamente para facilitar posibles downgrades.
     - Para evitar que el disco se llene, puedes usar:
       - `paccache -r` conserva solo las tres versiones más recientes de cada paquete.
       - `pacman -Sc` limpia la caché completa.
   - Configuración:
     - Los ajustes principales se encuentran en:
     - `/etc/pacman.conf`

---

4. Conceptos claves
   - Razón de instalación:
     - Los paquetes pueden estar marcados como:
       - Solicitados directamente por el usuario.
       - Instalados porque otro paquete los necesita para funcionar
   - Archivos `.pacnew`:
     - Durante una actualización, si has modificado un archivo de configuración, `pacman` no lo sobrescribirá. En su lugar, creará un archivo con la extención `.pacnew` para que revises y decidas cómo fusionar los cambios.
