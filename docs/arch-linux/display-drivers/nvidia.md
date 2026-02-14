# NVIDIA

Se recomienda evitar los instaladores del sitio web oficial y utilizar siempre los paquetes disponibles en los repositorios, ya que estos facilita las actualizaciones y el mantenimiento del sistema.

1. Instalación
   - Identifica tu modelo de GPU con:
     `lspci -k -d ::03xx`
   - Instala el paquete adecuado según tu hardware:
     - GPU modernas: `nvidia-open`
     - GPU legacy (Maxwell / Volta): `nvidia-580xx-dkms`
     - Modelos más antiguos: requieren versiones específicas como `nvidia-470xx-dkms` o `nvidia-390xx-dkms`
   - Para soporte de 32 bits, instala `lib32-nvidia-utils`

2. Verificación
   - Ejecuta `nvidia-smi` en la terminal.
   - Puedes usar `nvidia-settings` para revisar información técnica y ajustar parámetros de la tarjeta gráfica.
