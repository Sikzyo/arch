# QuickShell

QuickShell es un toolkit flexible y ligero para crear desktop shells con QtQuick. Es compatible con Hyprland y otros compositores Wayland, permitiendo crear barras de estado, widgets y elementos de escritorio interactivos.

---

1. Instalación

   Instala quickShell con:

   `sudo pacman -S quickshell`

---

2. Ejecución

   Añade la siguiente línea al archivo `~/.config/hypr/hyprland.conf`

   ```
   exec-once = quickshell
   ```

---

3. Configuración

   Creamos una carpeta con para las configuraciones en

   `~/.config/quickshell`

   Creamos el archivo shell.qml dentro de la nueva carpeta que creamos
