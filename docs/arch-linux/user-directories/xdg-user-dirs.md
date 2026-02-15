# xdg-user-dirs

Instalación
Instala el paquete xdg-user-dirs. Algunos entornos de escritorio, como GNOME, ya lo incluyen por defecto.
Creación de directorios
Para generar automáticamente las carpetas estándar (Descargas, Música, Escritorio, etc.) dentro de tu directorio personal, ejecuta:
xdg-user-dirs-update
• Nombres en inglés: Si prefieres que las carpetas conserven sus nombres en inglés independientemente del idioma del sistema, utiliza:
LC_ALL=C.UTF-8 xdg-user-dirs-update --force
• Funcionamiento: Este comando crea el archivo ~/.config/user-dirs.dirs, que las aplicaciones utilizan para localizar tus carpetas estándar.

Personalización y consulta
• Cambiar una ruta: Puedes asignar una carpeta personalizada usando:
xdg-user-dirs-update --set <NOMBRE_CARPETA> <RUTA>
Ejemplo: xdg-user-dirs-update --set DOWNLOAD ~/Internet
• Consultar ubicación: Para saber qué ruta tiene asignada una carpeta específica, ejecuta:
xdg-user-dir <NOMBRE>
Ejemplo: xdg-user-dir TEMPLATES
• Seguridad: Evita usar el comando de consulta con entradas de texto no verificadas, ya que podría permitir la ejecución de código malicioso.
