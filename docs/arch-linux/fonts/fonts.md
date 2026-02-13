# Fuentes

Esta guía te ayudará a gestionar fuentes en Linux, con un enfoque especial en la familia Google Noto, para que tu sistema tenga una apariencia moderna y una cobertura completa de caracteres.

---

1. ¿Por qué usar fuentes TrueType/OpenType?

Un sistema Linux básico suele incluir únicamente fuentes de mapa de bits (unscalable bitmap), que se ven pixeladas al cambiar el tamaño.

Para una experiencia moderna, se recomienda instalar fuentes TrueType (TTF) u OpenType (OTF), ya que son escalables y se mantienen nítidas en cualquier tamaño.

---

2. Fuentes recomendadas (Noto)

La familia Noto es una de las opciones más completas para la mayoría de los usuarios. Su objetivo es cubrir el estándar Unicode.

Paquetes principales:

- noto-fonts:
  - Paquete base.
- noto-fonts-cjk:
  - Necesario para visualizar caracteres asiáticos.
- noto-font-emoji:
  - Añade compatibilidad con emojis en color.

Otras alternativas populares:

- Liberation fonts
- DejaVu fonts

---

3. Cómo instalar fuentes

- A través del gestor de paquetes (Recomendado)
  Es el método más limpio y seguro, ya que el sistema gestionará automáticamente actualizaciones y desinstalaciones.

  Para instalar la fuente, puedes ejecutar:

  `sudo pacman -S noto-fonts`

  ***
  - Instalación manual
    Si descargas archivos `.ttf` o `otf` directamente de internet:
    1. Para tu usuario:
       1. Copia los archivos a `~/.local/share/fonts`
    2. Para todo el sistema:
       1. Copia los archivos a `/usr/local/share/fonts/`
       2. No modifiques `/usr/share/fonts/` manualmente, ya que está reservado para el gestor de paquetes.
    3. Ejecuta `fc-cache` para que el sistema reconozca las nuevas fuentes.

---

4. Configuración y optimización

Fontconfig es el sistema encargado de decidir qué fuente se utiliza y cómo se renderiza.

- Comandos útiles:
  - `fc-list` muestra todas las fuentes instaladas.
  - `fc-match serif` indica qué fuente se usa por defecto para el estilo serif.
- Mejora visual
  - Normalmente el sistema activa por defecto:
    - Anti-aliasing
    - Hinting
- Configuración personalizada
  - Si desea modificar el comportamiento, puedes crear reglas en:
  - `~/.config/fontconfig/fonts.conf`

---

5. Fuentes en la terminal

Si utilizas la consola virtual, la configuración es diferente. Las fuentes de consola se encuentran en:

`/usr/share/kbd/consolefonts/`

Para hacer un cambio permanente edita el archivo:

`/etc/vconsole.conf`

y define la variable `FONT=`, por ejemplo:

`FONT=lat2-16`
