# Mako

Mako es un daemon de notificaciones ligero para Wayland, compatible con Hyprland y otros compositores Wayland. Implementa la especificación de freedesktop.org, lo que garantiza compatibilidad con aplicaciones estándar de Linux

> Más información: [Mako manual](https://man.archlinux.org/listing/extra/mako/)

---

1.  Instalación

    Instala mako con:

    `sudo pacman -S mako`

---

2. Ejecución

   Mako se inicia automáticamente mediante activación por D-Bus cuando una aplicación envía una notificación. En la mayoría de los casos, no es necesario iniciarlo manualmente.

---

3. Configuración
   - El archivo de configuración de mako se encuentra en:
     - `~/.config/mako/config`
   - Si no existe, lo puedes crear con:
     - `mkdir -p ~/.config/mako`
     - `nano ~/.config/mako/config`

   Para ver todas las configuraciones disponibles para mako, consultar: [Mako 5](https://man.archlinux.org/man/extra/mako/mako.5.en)

---

1.  `makoctl`

    `makoctl` permite controlar mako en tiempo real desde la terminal.

    Comando básicos:
    - Cerrar la notificación activa:
      - `makoctl dismiss`
    - Cerrar todas las notificaciones
      - `makoctl dismiss --all`
    - Ejecutar la acción asociada a la notificación activa
      - `makoctl invoke`
    - Recargar la configuración sin reiniciar mako
      - `makoctl reload`
    - Mostrar el modo actual
      - makoctl mode
    - Activar un modo especial (por ejemplo, no molestar)
      - `makoctl mode -a do-not-disturb`
    - Desactivar el modo
      - `makoctl mode -r do-not-disturb`

---

1. Probar notificaciones

   Para enviar notificaciones de prueba, necesitas tener instalado `libnotify`

   `notify-send "Título" "Este es el cuerpo de la notificación"`
