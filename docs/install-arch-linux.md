# Instalar Arch Linux

Esta es una guía sobre cómo instalar Arch Linux sin utilizar el comando `archinstall`.

## 1. Pre instalación

### 1.1 Descarga de la imagen

1.  Visita [archlinux.org/download](https://archlinux.org/download/) y selecciona un servidor espejo cercano a tu ubicación.
2.  Una vez elegido el país, se mostrará una lista con varios enlaces disponibles. El archivo ISO suele aparecer como el tercer enlace de la lista: ![alt text](assets/download-arch.png).

### 1.2 Validar firma

Abre el archivo sha256sums.txt (último enlace de la lista) y verifica que la firma SHA256 coincida con la del archivo ISO que descargaste.

### 1.3 Crear USB booteable

1. Se recomienda usar [Rufus](https://rufus.ie/en/) para crear el USB booteable.
2. Reinicie el equipo y entra a la BIOS.
3. Configura el USB como primera opción de arranque.

### 1.4 Arrancar desde la USB

1. Guarda los cambios en la BIOS.
2. Reinicia el equipo.

### 1.5 Verificar el boot mode

Para comprobar el modo de arranque, ejecuta el siguiente comando:

`cat /sys/firmware/efi/fw_platform_size`

Según el resultado, el modo de arranque será:

| Resultado del comando     | Modo de arranque        |
| ------------------------- | ----------------------- |
| 64                        | UEFI 64 bits            |
| 32                        | UEFI 32 bits (limitado) |
| No such file or directory | BIOS / CSM              |

### 1.6 Conectarse a Internet

Para comprobar si tienes acceso a internet, ejecuta el siguiente comando:

`ping google.com`

Si no estas conectado por cable Ethernet sigue las instrucciones para conectarte por Wi-Fi en el siguiente enlace:

[iwtcl](https://wiki.archlinux.org/title/Iwd#iwctl)

### 1.7 Validar reloj del sistema

Para comprobar que el reloj del sistema está sincronizado, ejecuta el siguiente comando:

`timedatectl`

### 1.8 Particionar el disco

1. Verifica qué discos tienes conectados ejecutando: `lsblk`.
2. Usa `cfdisk` para particionar el disco. Sigue estos pasos:
   1. Ejecuta: `cfdisk /dev/[Nombre-del-disco]`
   2. Si el disco ya tiene particiones, las eliminamos. En el menú inferior selecciona `Delete`. Repite el proceso hasta que el disco quede sin particiones.
   3. Selecciona `New` para crear una nueva partición.
   4. Cuando pregunte el tamaño, escribe `1G` (Esta sera la partición EFI)
   5. Con las flechas del teclado, selecciona la opción `Type` en el menu inferior.
   6. En la lista que aparece, elige `EFI System`
   7. Selecciona el espacio restante (`Free Space`) y pulsa `New`
   8. Asigna el resto del espacio del disco para esta partición (Esta es la raíz)
   9. Verifica que el tipo (`Type`) sea `Linux filesystem`
   10. En el menú inferior, selecciona `Write` y escribe `yes` para guardar los cambios.
   11. Finalmente, selecciona `Quit` para salir.
3. Imagen de ejemplo: ![cfdisk menu](https://upload.wikimedia.org/wikipedia/commons/8/85/Cfdisk_screenshot.png)
4. Para comprobar que las particiones se crearon correctamente, ejecuta nuevamente `lsblk`

### 1.9 Formatear las particiones

Una vez creadas las particiones, debes formatearlas.

El comando general es `mkfs.[file-system] /dev/[partition]`

- `[file-system]` es el sistema de archivos a utilizar.
- `[partition]` es la partición que vas a formatear.

Sistema de archivos recomendados:

| file-system | partition | type             |
| ----------- | --------- | ---------------- |
| ext4        | /         | Linux filesystem |
| fat -F 32   | /boot     | EFI System       |

Ejemplos:

- `mkfs.ext4 /dev/root_partition`
- `mkfs.fat -F 32 /dev/efi_system_partition`

Si el sistema te pide confirmación, escribe `y` y presiona Enter.

### 1.10 Montar los discos

Ahora debes montar las particiones que usara el sistema.

1. Monta la partición raíz con el siguiente comando:

   `mount /dev/[root-partition] /mnt`

2. Monta la partición EFI con el siguiente comando:

   `mount --mkdir /dev/[efi-partition] /mnt/boot`

3. Si creaste particiones adicionales, monta las particiones con:

   `mount --mkdir /dev/[additional-partition] /mnt/[additional-partition]`

4. Para verificar que las particiones se montaron correctamente, ejecuta:

   `lsblk`

   En la columna MOUNTPOINTS podrás ver dónde está montada cada partición.

## Documentación

En caso de necesitarlo se puede volver a consultar la documentación oficial de Arch Linux: [Documentación](https://wiki.archlinux.org/title/Installation_guide)
