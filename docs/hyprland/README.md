# Hyprland

Documentación para instalar y configurar Hyprland como gestor de ventanas en Arch Linux.

## ¿Qué es Hyprland?

Hyprland es un compositor Wayland dinámico y tiling que permite construir tu propio entorno de escritorio minimalista y eficiente. A diferencia de los entornos de escritorio completos, Hyprland te da control total sobre qué componentes instalar.

## 🚀 Empezar

### Instalación

Sigue la guía de [Instalación de Hyprland](getting-started/install-hyprland.md) para instalar Hyprland en tu sistema.

### Primeros Pasos

Una vez instalado, consulta el [Tutorial Base](getting-started/master-tutorial.md) para configurar los componentes esenciales.

## 📦 Componentes Esenciales

Hyprland requiere que configures manualmente varios componentes:

| Componente | Descripción | Guía |
|------------|-------------|------|
| **Terminal** | kitty (recomendado) | Incluido en tutorial base |
| **Authentication Agent** | hyprpolkitagent | [Ver guía](must-have/authentication-agent.md) |
| **Wallpaper** | hyprpaper | [Ver guía](must-have/wallpaper.md) |
| **Notificaciones** | mako | [Ver guía](must-have/notification-daemon.md) |
| **Lanzador** | hyprlauncher | [Ver guía](must-have/application-launcher.md) |
| **Gestor de archivos** | yazi | [Ver guía](must-have/file-manager/yazi.md) |

## 🔧 Componentes Adicionales Recomendados

- **PipeWire** - Servidor de audio y video
- **WirePlumber** - Gestor de sesiones de PipeWire
- **XDG Desktop Portal** - xdg-desktop-portal-hyprland
- **Barra de estado** - waybar, eww, ags, o quickshell
- **Portapapeles** - wl-clipboard (wl-copy)

## 📚 Recursos

- [Hyprland Wiki Oficial](https://wiki.hyprland.org/)
- [Hyprland GitHub](https://github.com/hyprwm/Hyprland)

---

> ⚠️ **Nota importante**: Hyprland NO es un entorno de escritorio completo. La instalación y configuración de aplicaciones adicionales queda bajo tu responsabilidad.
