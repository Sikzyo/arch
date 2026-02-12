# Systemctl

systemctl es la herramienta principal de arch para inspeccionar y controlar el administrador de sistema y servicios systemd.

1. **El comando principal: `systemctl`**

   La herramienta fundamental para controlar `systemd` es `systemctl`. Se utiliza para examinar el estado del sistema y gestionar los servicios (programas que se ejecutan en segundo plano).

2. **Gestión de unidades (Units)**

   En `systemd` todo lo que se gestiona se denomina unidad. La más comunes son los servicios (`.service`) pero también existen puntos de montaje (`.mount`) y sockets (`.socket`)
   - Generalmente puedes omitir la extension `.service`. Por ejemplo, usar `systemctl start bluetooth` es lo mismo que `systemctl start bluetooth.service`
   - Por defecto, los comandos actúan sobre el sistema (requieren privilegios `root`). Si deseas gestionar servicios solo para tu usuario actual, añade el parámetro `--user` (sin sudo).

   ***

   **Comandos esenciales de gestión:**

   **Ver estado:**

   `systemctl status [unit]`

   Muestra si la unidad está activa, detenida o si ha fallado.

   **Iniciar/Detener**

   `systemctl start [unit]`

   `systemctl stop [unit]`

   Inicia o detiene la unidad de inmediato.

   **Reiniciar**

   `systemctl restart [unit]`

   Detiene e inicia nuevamente la unidad.

   **Habilitar al arranque**

   `systemctl enable [unit]`

   Configura la unidad para que se inicie automáticamente al encender el equipo.

   **Deshabilitar**

   `systemctl disable [unit]`

   Evita que la unidad se inicie automáticamente al arrancar.

   **--Now**

   `systemctl enable --now`

   `systemctl disable --now`

   Habilita e inicia la unidad al mismo tiempo o Deshabilita e detiene la unidad al mismo tiempo.

   **Enmascarar**

   `systemctl mask [unit]`

   `systemctl unmask [unit]`

   Impide que la unidad pueda iniciarse, incluso si otro servicio intenta hacerlo.

3. **Gestión de energía**

   Systemctl permite apagar o reiniciar el equipo. Si estás en una sesión local.
   - **Apagar:** `poweroff`
   - **Reiniciar:** `reboot`
   - **Suspender/Hibernar:** `suspend` o `hibernate`
