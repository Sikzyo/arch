# Journalctl

El journal de systemd es el sistema de registro (logs) propio de `systemd`, diseñado para recopilar y almacenar los mensajes del sistema de forma centralizada. No necesitas instalar un programa adicional para gestionar los registros, ya que el propio journal se encarga de ello.

A continuación, los puntos clave para comenzar a utilizarlo:

---

1. Herramienta principal

   Para leer y consultar los registros del sistema se utiliza el comando `journalctl`.

   Por defecto, los registros se almacenan de forma persistente en:

   `/var/log/journal/`

   Si esta carpeta no existe, los registros se guardan de forma temporal en memoria RAM:

   `/run/log/journal/`

---

2. Comandos esenciales

   Filtrar la información es fundamental para no perderse entre miles de líneas. Estos son los filtros más útiles:
   - Ver registros en tiempo real: `journalctl -f`
   - Registros de arranque actual: `journalctl -b`
   - Registros del arranque anterior: `journalctl -b -1`
   - Filtrar por un programa o servicio: `journalctl -u [name-service]`
     - Por ejemplo: `journalctl -u bluetooth.service`
   - Ver solo errores: `journalctl -p err..alert`
   - Registros de los últimos 20 minutos: `journalctl --since "20 min ago"`

---

3. Niveles de importancia

   El journal clasifica los mensajes según su nivel de gravedad. Los niveles más importantes que debes conocer son:
   - 0 - 3: Fallos críticos o errores que impiden el funcionamiento correcto del sistema.
   - 4: Advertencias sobre posibles problemas futuros.
   - 5 - 6: mensajes informativos normales que no requieren atención.

---

1. Mantenimiento y espacio en disco

   Si el journal ocupa demasiado espacio, puedes limitar su tamaño o eliminar registros antiguos:
   - Limpiar por tamaño:
     - `journalctl --vacuum-size=100M`
     - Elimina registros antiguos hasta que el tamaño total sea de 100 MB
   - Limpiar por tiempo:
     - `journalctl --vacuum-time=2weeks`
     - Elimina todos los registros anteriores a dos semanas
   - Configuración permanente:
     - Puedes establecer un límite máximo editando el archivo:
     - `/etc/systemd/journald.conf`
     - Y configurando el parámetro:
     - `SystemMaxUse=50M`

---

5. ¿Quién puede ver los registros?

Por razones de seguridad, un usuario normal solo puede ver sus propios registros. Para acceder a los registros completos del sistema, debes usar `sudo` o pertenecer a grupos específicos como `systemd-journal`, `adm` o `wheel`.
