# Pos Instalación

La idea es explicar cuales son los pasos recomendados a seguir después de instalar Arch.

## 1. Administración del sistema

### 1.1 Usuarios

Una instalación nueva solo crea el usuario root. Utilizar este usuario de forma habitual se considera inseguro, por lo que se recomienda crear y usar usuarios sin privilegios para el uso cotidiano del sistema.

El comando recomendado es:

`useradd -m -G wheel -s /bin/bash [nombre_de_usuario]`

- `-m` crea el directorio personal del usuario.
- `-G` añade al usuario al grupo de administración `wheel`, comúnmente usado para otorgar privilegios de `sudo`.
- `-s /bin/bash` establece Bash como la terminal (shell) predeterminada.

Para asignar una contraseña, ejecute el siguiente comando:

`passwd [nombre_de_usuario]`

Si no tienes `sudo` instalado, puedes instalarlo ejecutando el siguiente comando:

`pacman -S sudo`

El grupo `wheel` permite otorgar acceso a la utilidad `sudo`, pero este acceso no esta habilitado por defecto. Para activarlo, ejecuta:

`EDITOR=nano visudo`

Luego, elimina el símbolo `#` al inicio de la línea:

`%wheel ALL=(ALL:ALL) ALL`

### 1.2 Seguridad

A continuación, se detallan algunas acciones que deberían ejecutarse para mantener un sistema seguro:

1. Gestión de identidad y acceso
   - No utilices la cuenta `root` para el uso diario.
   - Utiliza `sudo` en lugar de `su`: esto permite ejecutar comando privilegiados de forma controlada.
   - Elige contraseñas robustas.
   - Usa un gestor de contraseñas para almacenar las credenciales de forma segura.
2. Mantenimiento del sistema
   - Es fundamental actualizar el sistema con frecuencia para corregir vulnerabilidades.
   - Asegúrate de tener instaladas las actualizaciones de microcódigo para tu CPU (Intel o AMD), ya que ayudan a mitigar vulnerabilidades de hardware.
3. Protección de red
   - Se recomienda instalar un cortafuegos como UFW.

#### 1.2.1 Instalar UWF

Para instalarlo y realizar la configuración básica, siga estos pasos:

1. Instalación

Primero, instala el paquete utilizando el siguiente comando:

`sudo pacman -S ufw`

Luego, habilita e inicie el servicio con:

`sudo systemctl enable --now ufw.service`

2. Configuración básica

La configuración básica suele consistir en denegar el trafico entrante por defecto y permitir únicamente lo que el usuario necesite.

Ejecuta el siguiente comando para denegar cualquier conexión entrante que no haya sido permitida manualmente:

`ufw default deny`

Si necesitas permitir el tráfico desde tu red local, puedes autorizar el acceso desde tu red interna con:

`ufw allow from 192.168.0.0/24`

Para reducir el riesgo de ataques de fuerza bruta por SSH, utiliza:

`ufw limit ssh`

3. Activación

Una vez definas las reglas básicas, debes activar el firewall con:

`ufw enable`

Este comando solo es necesario una vez

Para verificar qué las reglas están aplicadas y confirmar que el firewall está activo, usa:

`ufw status`

Si desea ver información más detallada, ejecuta:

`ufw status verbose`

4. Gestión de puertos

Si necesita abrir puertos específicos, UFW incluye perfiles de aplicaciones predefinidos. Puedes ver la lista disponible con:

`ufw app list`

Para permitir una aplicación, ejecuta:

`ufw allow [app-name]`

O, si deseas permitir un puerto especifico:

`ufw allow [port]`

## Documentación

Para profundizar más en el tema, se recomienda visitar la página de la documentación oficial sobre recomendaciones generales: [General recommendations](https://wiki.archlinux.org/title/General_recommendations)
