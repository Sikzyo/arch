# hyprpaper

Hyprpaper es una herramienta ligera y rápida para gestionar fondos de pantalla en Hyprlan, con soporte de control en tiempo real mediante IPC.

---

1. Instalación
   Ejecuta el siguiente comando
   `sudo pacman -S hyprpaper`

---

2. Configuración
   - El archivo de configuración se encuentra en la ruta:
     `~/.config/hypr/hyprpaper.conf`
   - Configurar fondos de pantalla
     - Cada monitor se configura mediante su propio bloque `wallpaper {}`
     - Si el campo `monitor` se deja vacío, el fondo se utilizará como fallback, es decir se aplicará a cualquier monitor que no tenga un fondo asignado explícitamente.

       ```
       wallpaper {
        monitor = DP-3
        path = ~/fondos/imagen.jxl
        fit_mode = cover
       }

       wallpaper {
        monitor = DP-2
        path = ~/fondos/imagen2.jpg
        fit_mode = contain
       }

       wallpaper {
        monitor =
        path = ~/fondos/fallback.png
        fit_mode = cover
       }
       ```

   - Parámetros del bloque `wallpaper`

     | Parámetro | Descripción                                                     | Valores                            |
     | --------- | --------------------------------------------------------------- | ---------------------------------- |
     | monitor   | Monitor donde se mostrará el fondo. Vacío = fallback            | ID del monitor                     |
     | path      | Ruta a una imagen o a una carpeta con imágenes                  | rita absoluta o `~/...`            |
     | fit-mode  | Modo de ajuste de la imagen (Por defecto `cover`)               | `cover`, `contain`, `tile`, `fill` |
     | timeout   | Intervalo en segundos si `path` es una carpeta (Por defecto 30) | Numero entero                      |

   - Opciones generales
     Estas opciones se definen fuera de los bloques `wallpaper {}`

     | Parámetro      | Descripción                                  | Valores         |
     | -------------- | -------------------------------------------- | --------------- |
     | splash         | Muestra el splash de Hyprland sobre el fondo | `true`, `false` |
     | splash_offset  | Desplazamiento vertical del splash           | Numero entero   |
     | splash_opacity | Opacidad del splash                          | 0.0 - 1.0       |
     | pic            | Habilita el control mediante IPC             | `true`, `false` |

---

3. Ejecutar al inicio
   Añade la siguiente línea a tu archivo `~/.config/hypr/hyprland.conf`:
   ```
   exec-once = hyprpaper
   ```

---

4. Control por IPC
   Es posible cambiar los fondos de pantalla sin reiniciar el compositor usando `hyprctl`:

   ```
   hyprctl hyprpaper wallpaper '[monitor], [path], [fit_mode]'
   ```

---

5. Organización con `source`
   Puedes dividir la configuración en varios archivos para mantenerla ordenada:
   `source = ~/.config/hypr/hyprpaper.d/*.conf`
