# Microcode

El micro código son actualizaciones de estabilidad y seguridad para el procesador, publicadas por Intel y AMD.

Sin estas actualizaciones, el sistema puede experimentar bloqueos inesperados o cierres repentinos difíciles de diagnosticar. Incluye parches contra vulnerabilidades a nivel del procesador.

1. Como instalarlo
   Según el tipo de procesador, debes instalar uno de los siguientes paquetes desde los repositorios.
   - Para procesadores AMD instala: `amd-ucode`
   - Para procesadores Intel instala: `intel-ucode`

2. Configuración
   Para que las actualizaciones surtan efecto, el micro código debe cargarse muy temprano durante el inicio del sistema.

3. Como verificar que está activo
   Después de iniciar el sistema, puedes comprobar si el micro código se cargó correctamente ejecutando el siguiente comando:

   `journalctl -k --grep='microcode:'`

   Si la actualización fue exitosa, aparecerá un mensaje similar a:

   `kernel: microcode: Current revision: 0x...`

4. ¿Que hacer en casos de problemas?
   En el caso poco frecuente de que una actualización de microcódigo cause problemas durante el arranque, puedes desactivar temporalmente su carga añadiendo el parámetro `dis_ucode_ldr` a las opciones de arranque del cargador de arranque.
