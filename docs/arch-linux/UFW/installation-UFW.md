# Instalar UWF

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
