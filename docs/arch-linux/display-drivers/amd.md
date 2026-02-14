# AMD

Este controlador esta destinado a las tarjetas Radeon de la familia Graphics Core Next (GCN) en adelante (desde 2012)

1. Instalación
   - Instala el paquete `mesa` para habilitar la aceleración 3D y la decodificación de video.
   - Para soporte de Vulkan, instala `vulkan-radeon`
   - Para soporte de 32 bits, instala `lib32-vulkan-radeon`

2. Verificación
   - Ejecuta `lspci -k` en la terminal. En la sección correspondiente a la tarjeta gráfica debería aparecer:
     `Kernel driver in use: amdgpu`
   - Para monitorear el uso de la GPU en tiempo real, puedes usar:
     `watch -n 0.5 cat /sys/kernel/debug/dri/0/amdgpu_pm_info`
