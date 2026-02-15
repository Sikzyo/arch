# Keyring

Keyring es un conjunto de componentes diseñados para almacenar de forma segura secretos, contraseñas, llaves y certificados, y ponerlos a disposición de las aplicaciones del sistema de manera controlada.

1. Instalación

   Instala el servicio y la librería de comunicación para gestionar tus claves:

   `sudo pacman -S gnome-keyring libsecret`

---

2. Desbloqueo automático (PAM)

   Para que el llavero se desbloquee automáticamente al iniciar sesión, la contraseña de tu usuario debe coincidir con la del llavero "Login"
