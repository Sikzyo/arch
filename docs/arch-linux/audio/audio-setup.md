# Audio

1. ¿Qué es PipeWire y WirePlumber?
   - PipeWire es un framework multimedia de bajo nivel diseñado para gestionar audio y video con una latencia minina. Funciona como un remplazo moderno de PulseAudio y JACK.
   - WirePlumber es el gestor de sesiones recomendado para PipeWire. Se encarga de la lógica de conexión, como decidir qué aplicaciones se conectan a cada dispositivo de entrada o salida.

---

2. Instalación

   Se deben instalar los siguientes paquetes básicos:
   - Framework base:
     - `sudo pacman -S pipewire`
   - Gestor de sesiones:
     - `sudo pacman -S wireplumber`
   - Soporte de audio:
     - `sudo pacman -S pipewire-audio `
   - Capas de compatibilidad:
     - `sudo pacman -S pipewire-pulse`
     - `sudo pacman -S pipewire-alsa`
     - `sudo pacman -S pipewire-jack`

   PipeWire y WirePlumber se administran mediante `systemd` a nivel de usuario. Normalmente, los servicios se activan automáticamente tras la instalación o después de reiniciar el sistema.

   Para que el usuario pueda acceder a los dispositivos de audio, es necesario agregarlo al grupo `audio`:

   `sudo usermod -aG audio $USER`

   Después de ejecutar este comando, cierra sesión y vuelve a iniciarla para que los cambios surtan efecto.

---

3. Uso y comandos básicos

   La herramienta principal para interactuar con PipeWire desde la terminal es `wpctl`.
   - Ver el estado actual:
     - `wpctl status`
     - Muestra todos los dispositivos de audio (Sinks/Source) junto con sus IDs numéricos
   - Cambiar el dispositivo predeterminado:
     - `wpctl set-default [ID]`
     - Sustituye `[ID]` por el número correspondiente mostrado en `wpctl status`
   - Control de volumen:
     - Subir volumen: `wpctl set-volume @DEFAULT_AUDIO_SINK@ 5%+`
     - Bajar volumen: `wpctl set-volume @DEFAULT_AUDIO_SINK@ 5%-`
     - Silenciar / Activar sonido: `wpctl set-mute @DEFAULT_AUDIO_SINK@ toggle`
     - Activar / Desactivar micrófono: `wpctl set-mute @DEFAULT_AUDIO_SOURCE@ toggle`
   - Verificar compatibilidad con PulseAudio:
     - `pactl info`
     - En el campo Server Name debería aparecer: PulseAudio (on PipeWire x.x.xx)

---

4. Configuración

   Nunca edites los archivos ubicados en `/usr/share/pipewire` o `/usr/share/wireplumber/`, ya que se sobrescriben durante las actualizaciones.
   - Jerarquía de archivos de configuración: Para personalizar el comportamiento, copia los archivos a:
     - Global: `/etc/pipewire/` o `/etc/wireplumber/`
     - Usuario: `~/.config/pipewire/` o `~/.config/wireplumber/`
   - Formato de WirePlumber: A partir de la versión 0.5, utiliza archivos `.conf` (formato SPA-JSON) en lugar de `.lua`
   - Cambio de calidad (resampling): Si deseas mejorar la calidad del remuestreo, crea el archivo `~/.config/pipewire/client.conf.d/resample.conf` y añade la siguiente línea:

     `stream.properties = { resample.quality = 10 }`

---

5. Aplicaciones gráficas

   Para usuarios promedio, estas herramientas facilitan considerablemente la gestión del audio:
   - `pavucontrol`: Control de volumen clásico de PulseAudio, totalmente compatible con PipeWire
   - `qpwgraph`: Un "patchbay" visual que permite conectar virtualmente aplicaciones y dispositivos de audio
   - `EasyEffects`: Herramienta avanzada para aplicar efectos a nivel de sistema, como ecualización, reducción de ruido y limitadores

---

6. Solución de problemas comunes
   - Audio bajo tras reiniciar: Abre `alsamixer`, selecciona tu tarjeta con F6 y asegúrate de que los niveles de ALSA estén al 100%
   - Retrasos o "pops" al iniciar el audio: Suele deberse a la suspensión de nodos inactivos. Puedes desactivarla creando el archivo `/etc/wireplumber/wireplumber.conf.d/disable-suspension.conf` con la propiedad:

     `session.suspend-timeout-seconds = 0`

   - Restablecer la configuración: Si algo falla, puedes eliminar el estado local de WirePlumber con `rm -r ~/.local/state/wireplumber/` y reiniciar el servicio

---

## Enlaces a documentación oficial

- PipeWire Wiki: https://gitlab.freedesktop.org/pipewire/pipewire/-/wikis/home
- WirePlumber Documentation: https://pipewire.pages.freedesktop.org/wireplumber/
