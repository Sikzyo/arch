# Mantenimiento del sistema

Para mantener un sistema saludable, lo más importante para un usuario común se resume en los siguientes puntos claves:

---

1. Actualización segura del sistema
   - Antes de actualizar, revisa la página principal de [Arch Linux](https://archlinux.org) para conocer cambios que requieran intervención manual.
   - Realiza siempre una actualización total del sistema con:
     - `sudo pacman -Syu`
     - Nunca realices actualizaciones parciales (por ejemplo, instalar un paquete sin actualizar el resto del sistema), ya que no están soportadas y pueden romper el sistema.
     - Lee los avisos que muestra `pacman` durante la actualización. Si aparecen archivos `.pacnew`, revíselos y aplíquelos cuanto antes para mantener tus configuraciones compatibles.
     - Después de actualizar componentes críticos como el kernel o el entorno gráfico, reinicia el equipo para aplicar correctamente los cambios.

2. Monitoreo y limpieza
   - Verifica periódicamente si existen servicios fallidos con:
     - `systemctl --failed`
     - también puedes revisar los registros del arranque actual con:
     - `journalctl -b`
   - Elimina paquetes huérfanos con:
     - `sudo pacman -Qtd`
     - Además, limpia regularmente el caché de paquetes en:
     - `/var/cache/pacman/pkg/`
     - para liberar espacio en disco

---

3. Buenas practicas
   - Realiza copias de seguridad de tus archivos de configuración antes de modificarlos y conserva una lista de los paquetes instalados por si necesitas reinstalar el sistema.
   - Instala software siempre mediante `pacman` o desde el AUR. Evita instalaciones manuales que el sistema no pueda rastrear.
