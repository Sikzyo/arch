# Genshin Impact

Genshin Impact es un juego de rol de acción en mundo abierto desarrollado por miHoYo.

1. Instalación

   Para instalar Genshin Impact, primero debes descargar el instalador oficial desde su [página web oficial](https://genshin.hoyoverse.com).

   Una vez descargado, agrégalo a Steam como programa externo:
   - Abre Steam y selecciona **Add a Game** > **Add a Non-Steam Game**
   - Haz clic en **Browse** y busca el instalador en tu carpeta de descargas
   - Selecciona el instalador y haz clic en **Add Selected Program**

   Configura la compatibilidad:
   - En tu biblioteca de Steam, haz clic derecho en el instalador y selecciona **Properties**
   - Ve a la pestaña **Compatibility**
   - Marca **Force the use of a specific Steam Play compatibility tool**
   - Selecciona **Proton Experimental**

   Ejecuta el instalador desde Steam y completa la instalación del juego.

   Una vez terminada, cierra el instalador.

   Configura el acceso directo:
   - Abre las propiedades del programa en Steam
   - En **Target**, selecciona el ejecutable del launcher
   - En **Start In**, selecciona la carpeta que contiene el ejecutable

2. Instalación en otro disco

   Si deseas instalar el juego en otro disco, sigue estos pasos:
   - Al ejecutar el instalador, añade esto a las opciones de lanzamiento: `STAM_COMPAT_MOUNTS=/data %command%`
   - Cierra el instalador por completo después de la instalación
   - Encuentra el ID de la carpeta `compatdata` ejecutando:
     ```bash
     ls -dt ~/.steam/root/steamapps/compatdata/* | head -n 1
     ```
   - Navega a la carpeta de dispositivos:
     ```bash
     cd ~/.steam/root/steamapps/compatdata/TU_ID_AQUI/pfx/dosdevices/
     ```
   - Crea un enlace apuntando a tu disco:
     ```bash
     ln -s /data d:
     ```

## Documentación

Para obtener más información, se recomienda visitar la página oficial de [Genshin Impact](https://genshin.hoyoverse.com/) y la documentación de Arch Linux en [Gaming](https://wiki.archlinux.org/title/Gaming)
