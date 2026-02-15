# xdg-desktop-portal-hyprland

1. ¿Qué es?

   Es la implementación de XDG Desktop Portal para Hyprland. Permite que aplicaciones externas se comuniquen con el compositor a través de D-Bus para funciones como compartir pantalla y atajos globales.

---

2. Instalación

   Para instalarlo utiliza el siguiente comando:

   `sudo pacman -S xdg-desktop-portal-hyprland`

---

3. Uso y verificación
   - XDPH se inicia automáticamente mediante D-Bus cuando arranca Hyprland
   - Abre una aplicación como OBS y selecciona la fuente `PipeWire`. Si todo funciona correctamente, aparecerá un menu de Qt para elegir qué ventana o monitor deseas compartir.
   - Si el portal falla, algunas fuentes recomiendan reiniciar los procesos `xdg-desktop-portal-hyprland` y `xdg-desktop-portal`.

---

4. Configuración

   Hay dos archivos principales para ajustar ek comportamiento del portal:
   - `~/.config/hypr/xdph.conf`: Permite definir opciones como los FPS de la captura de pantalla.
   - `~/config/xdg-desktop-portal/hyprland-portals.conf`: Si prefieres usar el selector de archivos de KDE en lugar de GTK, puedes indicarlo aquí.

---

5. Mantenimiento

   Si notas lentitud al abrir aplicaciones o problemas con el comportamiento de pantalla:
   - Ejecuta `systemctl --user -status. xdg-desktop-portal-hyprland`
   - Los errores más comunes suelen deberse a la ausencia de `qt6-wayland`
   - Si el servicio no inicia, es probable que las variables de entorno de XDG no estén configuradas correctamente.

---

## Documentación

Para información más detallada y actualizada, consulta:

- [XDPH](https://wiki.hypr.land/Hypr-Ecosystem/xdg-desktop-portal-hyprland/)
