# Intel

Los controladores de Intel suelen ser casi plug-and-play gracias a su naturaleza de código abierto

1. Instalación
   - Instala `mesa`
   - Para soporte de Vulkan, instala `vulkan-intel`
   - Para soporte de 32 bits, instala `lib32-vulkan-intel`
   - Se recomienda utilizar el controlador `modesetting` en lugar de `xf86-video-intel` en hardware moderno, ya que este último puede ocasionar problemas de rendimiento y estabilidad.
