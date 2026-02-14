# Documentación

La idea es explicar cuales son los pasos recomendados a seguir después de instalar Arch.

## 1. Administración del sistema

### 1.1 Usuarios

Una instalación nueva solo crea el usuario root. Utilizar este usuario de forma habitual se considera inseguro, por lo que se recomienda crear y usar usuarios sin privilegios para el uso cotidiano del sistema.

Para crear un nuevo usuario, consulta la sección: [crear usuario](./users/user.md)

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
   - Se recomienda instalar un cortafuegos como [UFW](./UFW/installation-UFW.md).

### 1.3 Administración de servicios

Arch utiliza systemd como gestor central del sistema y de los servicios. Su administración se basa en dos herramientas principales:

- [systemctl](./systemd/systemctl.md): El comando utilizado para interactuar con systemd y controlar los servicios.
- [journalctl](./systemd/journalctl.md): Herramienta para consultar el sistema de registros (logs).

Es fundamental conocer los conceptos básicos de estas herramientas para realizar un mantenimiento adecuado del sistema.

### 1.4 Mantenimiento del sistema

Arch Linux requiere mantenimiento regular. Para más información, consulta [Mantenimiento del sistema](./system-maintenance/system-maintenance.md)

## 2 Gestor de paquetes

### 2.1 pacman

`pacman` es el gestor de paquetes de Arch y aprender a utilizarlo correctamente es fundamental para administrar el sistema

Para más información, consulta [pacman](./pacman/pacman.md)

### 2.2 Repositorios

Se recomienda consultar la sección de repositorios oficiales para obtener más información: [repositorios](./repositories/repositories.md)

### 2.3 Espejos(Mirrors)

Para optimizar la velocidad y actualización de los repositorios, se recomienda mirar el articulo de [mirrors](./mirrors/mirrors.md)

### 2.4 Arch Build System

El ABS es el mecanismo que permite a los usuarios compilar su propio software (ya sea proveniente de los repositorios oficiales o del AUR) y asegurarse de que el resultado final sea un paquete que el sistema pueda reconocer, instalar y administrar fácilmente.

Se recomienda mirar el articulo [ABS](./abs/abs.md)

### 2.5 AUR

Arch User Repository (AUR) trata sobre el repositorio comunitario de Arch.

Se recomienda mirar el articulo [AUR](./aur/aur.md)

## 3 Boot

### 3.2 Microcode

Los procesadores pueden presentar comportamientos defectuoso. Para corregir estos fallos, el kernel puede actualizar el micro código del procesador durante el inicio del sistema.

Para más información, consulta: [Microcode](./microcode/microcode.md)

## 4 Interfaz gráfica del usuario

### 4.2 Controladores de pantalla

Aunque el controlador predeterminado `modesettting` funciona correctamente con la mayoría de las tarjetas de video, se recomienda instalar los controladores específicos para productos de AMD, Intel o NVIDIA. Esto permite obtener un mejor rendimiento del sistema y acceder a funciones adicionales propias de cada tarjeta gráfica.

[AMD](./display-drivers/amd.md)
[Intel](./display-drivers/intel.md)
[NVIDIA](./display-drivers/nvidia.md)

## 11 Apariencia

### 11.1 Fuentes

Instalar fuentes TrueType para mejorar la compatibilidad y ampliar la cobertura Unicode, ya que el sistema base solo incluye fuentes de mapa de bits.

Para la configuración de las fuentes consulta [Fuentes](./fonts/fonts.md)

## Documentación

Para profundizar más en el tema, se recomienda visitar la página de la documentación oficial sobre recomendaciones generales: [General recommendations](https://wiki.archlinux.org/title/General_recommendations)
