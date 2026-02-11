# Instalar Arch Linux

Esta es un guía de como instalar Arch Linux sin usar el comando `arch-install`

## 1. Pre instalación

### 1.1 Descarga de la imagen

1.  Visita [archlinux.org/download](https://archlinux.org/download/) y selecciona un servidor espejo cercano a tu ubicación.
2.  Una vez elegido el país, aparecerán varios enlaces. El archivo ISO es típicamente el tercero en la lista: ![alt text](assets/download-arch.png).

### 1.2 Validar firma

Lee el archivo sha256sums.txt (último enlace) y verifica la firma

### 1.3 Crear USB booteable

1. Se recomienda usar [Rufus](https://rufus.ie/en/) para realizar este proceso.
2. Reinicie el equipo y acceda a la BIOS. Configure el USB como primera opción de arranque.

### 1.4 Arrancar desde la USB

Guarde los cambios en la BIOS y reinicie. El sistema debería iniciar desde el USB.

### 1.5 Verificar el boot mode

Para poder verificar el boot mode, ejecute el siguiente comando: `cat /sys/firmware/efi/fw_platform_size`

| Resultado del comando     | Modo de arranque        |
| ------------------------- | ----------------------- |
| 64                        | UEFI 64 bits            |
| 32                        | UEFI 32 bits (limitado) |
| No such file or directory | BIOS / CSM              |

### 1.6 Conectarse a Internet

Para validar si tiene acceso a internet ejecute el siguiente comando: `ping google.com`

En caso de no estar conectado mediante cable Ethernet: seguir las instrucciones para conectarse por wifi: [iwtcl](https://wiki.archlinux.org/title/Iwd#iwctl)

### 1.7 Validar reloj del sistema

Para validar que el reloj este sincronizado ejecuta el siguiente comando: `timedatectl`

### 1.8 Particionar el disco

|

1. Valide que discos tiene conectados utilizando: `lsblk`
2. Utiliza `cfdisk` para poder particionar el disco, Sigue los pasos que se mencionan para poder particionar el disco:
   1. Ejecutamos: `cfdisk /dev/[Nombre del disco que quieras particionar]`
   2. Si tenemos particiones las eliminamos, en el menu inferior seleccionamos la opción `Delete`, asi con cada partición hasta que quede limpio el disco
   3. Creamos una nueva partición utilizando el botón `New` en la parte inferior
   4. Nos preguntara cuanto espacio necesitamos, ingresamos `1G`
   5. Nos desplazamos hasta en el menu inferior, para seleccionar el botón `Type`
   6. A esta nueva partición que acabamos de crear, le asignamos el tipo `EFI System`
   7. Nos desplazamos para seleccionar el espacio vació en el disco y en el menu inferior seleccionamos el botón `New`
   8. Asignamos el espacio restante del disco
   9. Validamos que el `Type` es `Linux filesystem`
   10. En el menu inferior, seleccionamos el botón `Write` para guardar los cambios
   11. Para terminar, en el menu inferior, seleccionamos el botón `Exit` para salir
3. Imagen de ejemplo: ![cfdisk menu](https://upload.wikimedia.org/wikipedia/commons/8/85/Cfdisk_screenshot.png)

## Documentación

En caso de necesitarlo se puede volver a consultar la documentación oficial de Arch Linux: [Documentación](https://wiki.archlinux.org/title/Installation_guide)
