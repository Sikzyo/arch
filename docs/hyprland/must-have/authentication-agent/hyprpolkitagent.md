# Hyprpolkitagent

1. ¿Qué es?
   Es un demonio de autenticación polkit para Hyprland. Permite que las aplicaciones gráficas soliciten permisos elevados, por ejemplo, cuando es necesario ingresar la contraseña para instalar software o realizar cambios en el sistema.

2. Instalación
   - Desde los repositorios oficiales:
     `sudo pacman -S hyprpolkitagent`
   - También es necesario instalar qt6-wayland:
     - `sudo pacman -S qt6-wayland`

3. Configuración
   Agrega la siguiente línea en el archivo `~/.config/hypr/hyprland.conf`
   `exec-once = systemctl --user start hyprpolkitagent`

4. Paso final
   Reinicia el sistema para aplicar los cambios.
