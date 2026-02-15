# Documentación de Arch Linux

Este repositorio contiene documentación y guías para instalar y configurar Arch Linux con Hyprland como gestor de ventanas.

## 📚 Índice de Contenidos

### 🐧 Arch Linux

Guías para la instalación y configuración de Arch Linux.

- **[Guía de Instalación](arch-linux/installation-guide.md)** - Instalación paso a paso de Arch Linux sin usar `archinstall`
- **[Post-instalación](arch-linux/pos-installation.md)** - Pasos recomendados después de instalar
- **[Documentación General](arch-linux/README.md)** - Guía completa de administración del sistema

**Administración del Sistema:**
- [Usuarios](arch-linux/users/user.md) - Crear y gestionar usuarios
- [systemctl](arch-linux/systemd/systemctl.md) - Gestión de servicios
- [journalctl](arch-linux/systemd/journalctl.md) - Sistema de logs
- [Mantenimiento](arch-linux/system-maintenance/system-maintenance.md) - Mantenimiento regular del sistema

**Gestión de Paquetes:**
- [pacman](arch-linux/pacman/pacman.md) - Gestor de paquetes oficial
- [Repositorios](arch-linux/repositories/repositories.md) - Configuración de repositorios
- [Espejos](arch-linux/mirrors/mirrors.md) - Optimización de mirrors
- [ABS](arch-linux/abs/abs.md) - Arch Build System
- [AUR](arch-linux/aur/aur.md) - Arch User Repository
- [yay](arch-linux/aur/yay.md) - Helper para AUR

**Seguridad y Controladores:**
- [UFW Firewall](arch-linux/ufw/installation-ufw.md) - Cortafuegos
- [Microcode](arch-linux/microcode/microcode.md) - Actualizaciones de CPU
- [Drivers AMD](arch-linux/display-drivers/amd.md)
- [Drivers Intel](arch-linux/display-drivers/intel.md)
- [Drivers NVIDIA](arch-linux/display-drivers/nvidia.md)

**Configuración:**
- [Fuentes](arch-linux/fonts/fonts.md)
- [Directorios de usuario](arch-linux/user-directories/xdg-user-dirs.md)

---

### 🪟 Hyprland

Guías para instalar y configurar Hyprland como gestor de ventanas.

- **[Instalación de Hyprland](hyprland/getting-started/install-hyprland.md)**
- **[Tutorial Base](hyprland/getting-started/master-tutorial.md)** - Primeros pasos después de instalar

**Componentes Esenciales:**
- [Authentication Agent](hyprland/must-have/authentication-agent.md) - hyprpolkitagent
- [Wallpaper](hyprland/must-have/wallpaper.md) - hyprpaper
- [Notificaciones](hyprland/must-have/notification-daemon.md) - mako
- [Lanzador de aplicaciones](hyprland/must-have/application-launcher.md) - hyprlauncher
- [Gestor de archivos](hyprland/must-have/file-manager/yazi.md) - yazi

---

### 📝 Zed Editor

Configuración del editor Zed.

- **[Configuración de Zed](zed-editor/zed-config.md)**

---

## 📖 Recursos Oficiales

- [Arch Linux Wiki](https://wiki.archlinux.org/)
- [Hyprland Wiki](https://wiki.hyprland.org/)
- [Zed Documentation](https://zed.dev/docs)

---

> 💡 **Nota**: Esta documentación está en constante desarrollo mientras aprendo a usar Arch Linux. Se aceptan sugerencias y correcciones.
