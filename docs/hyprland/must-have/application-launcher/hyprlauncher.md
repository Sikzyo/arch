# Hyprlauncher

1. ¿Qué es?

   Un lanzador que funciona como daemon persistente:
   - En la primera ejecución inicia el daemon.
   - En las siguientes, simplemente abre la ventana.

   Incluye tres módulos integrados:
   - `desktop`
   - `math`
   - `unicode`

---

2. Instalación

   Para instalarlo ejecuta el siguiente comando:

   `sudo pacman -S hyprlauncher`

---

3. Uso básico

   Hyprlauncher siempre corre como daemon. La primera vez queda activo en segundo plano; las siguientes solo abren la ventana.

   Añade esto a `~/.config/hypr/hyprland.conf`
   - Iniciar el daemon al arrancar la sesión
     - `exec-once = hyprlauncher -d`
   - Abrir el launcher con Super + Espacio
     - `bind = SUPER, SPACE, exec, hyprlauncher`

También puedes lanzarlo manualmente:

`hyprlauncher`

---

4. Configuración

   El archivo de configuración está en:

   `~/.config/hypr/hyprlauncher.conf`

   Si no existe créelo con:

   `touch ~/.config/hypr/hyprlauncher.conf`

   Para conocer todas las opciones disponibles, se recomienda consultar la sección de configuración en la documentación oficial: [Configuración](https://wiki.hypr.land/Hypr-Ecosystem/hyprlauncher/#configuration)

---

1. Finders (cómo se usa)

   | Qué escribes | Qué hace              |
   | ------------ | --------------------- |
   | [nombre]     | Abre una aplicación   |
   | .[emoji]     | Busca Unicode         |
   | =[operación] | Calcula una expresión |

---

6. Tema

   Hyprlauncher usa el tema de hyprtoolkit automáticamente.

   Para más información, consulta la wiki de: [hyprtoolkit](https://wiki.hypr.land/Hypr-Ecosystem/hyprtoolkit/)
