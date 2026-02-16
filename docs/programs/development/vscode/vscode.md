# Vscode

Visual Studio Code (VS Code) es un editor de código ligero y potente

1. Instalación

   Para instalar Vscode, utiliza el siguiente comando en la terminal.

   `yay -S visual-studio-code-bin`

---

2. Configuración

   Para que vscode funcione correctamente realiza lo siguientes pasos:
   - Abre la Paleta de Comandos: `Ctrl+Shift+P`
   - Busca y ejecuta: `Configure Runtime Arguments`
   - En el archivo `argv.json` que se abre, agrega:
     - `"password-store":"gnome-libsecret"`
   - Guarda el archivo

## Documentación

Para mayor información se recomienda visitar la pagina oficial de [Vscode](https://code.visualstudio.com/) y la documentación de Arch Linux en [Vscode Arch](https://wiki.archlinux.org/title/Visual_Studio_Code)
