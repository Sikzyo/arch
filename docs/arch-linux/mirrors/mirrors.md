# Espejos

Los mirrors son servidores que almacenan copias de los paquetes de software para su descarga. Estos son los puntos más importantes:

- La lista de servidores se encuentra en el archivo `/etc/pacman.d/mirrorlist`. Para activar un servidor, debes descomentar la línea correspondiente (quitar el símbolo `#`) que comienza con `Server`
- `pacman` utiliza los mirrors en el orden en que aparecen en la lista. Se recomienda colocar tus 5 servidores preferidos o los más rápidos en la parte superior.
- Es fundamental usar mirrors actualizados para evitar problemas de compatibilidad. Puedes consultar el estado de cada servidor en la página oficial de [Mirror status](https://archlinux.org/mirrors/status/)
- Cada vez que modifiques la lista de mirrors, debes ejecutar el comando `pacman -Syyu` para forzar la actualización de las bases de datos de paquetes y sincronizar el sistema.
- En lugar de editar la lista manualmente, es más práctico utilizar herramientas como [Reflector](mirrors.md), que buscan, filtran y ordenan automáticamente los mirrors más rápidos y actualizados según tu ubicación.
