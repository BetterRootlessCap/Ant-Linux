# Ant Linux 1.0 (x86_64)

**Ant Linux** es una distribución Linux ultracompacta (~36 MB ISO) y endurecida en seguridad, construida desde cero siguiendo la arquitectura de **Linux From Scratch (LFS)** e integrando únicamente las librerías esenciales (`musl libc` y `apk-tools`) de **Alpine Linux** para lograr una ligereza extrema y arranque directo en memoria RAM.

## Requisitos del Sistema

### Requisitos Mínimos
* **CPU:** Procesador de 64 bits (`x86_64`) a 1 GHz
* **RAM:** 256 MB
* **Almacenamiento:** 512 MB (o ejecución directa en RAM desde la ISO Live de 36 MB)
* **GPU:** Gráficos básicos compatibles con VGA o VESA
* **Nota sobre la interfaz gráfica:** La interfaz gráfica (`JWM` / `Xorg`) está incluida, pero no funciona en su totalidad en todos los entornos o tarjetas de video debido a su diseño minimalista.
* **Arquitectura base:** Esta distribución cuenta únicamente con las librerías base de Alpine Linux, pero su estructura y construcción provienen de **Linux From Scratch (LFS)**.

### Requisitos Recomendados
* **CPU:** 4 núcleos (Quad-Core) a 1.0 GHz o superior
* **RAM:** 1 GB
* **Almacenamiento:** 32 GB
* **GPU:** Gráficos compatibles con VESA / Framebuffer

---

## Credenciales por Defecto y Uso Rápido

El sistema inicia sesión automáticamente en una terminal limpia y protegida como usuario estándar (`ant@localhost-$`).

* **Usuario estándar:** `ant`
* **Contraseña por defecto (usuario y root):** `4nt`
* **Subir a superusuario (`root@ant-#`):**
  ```sh
  sudo -i
  ```
* **Iniciar la interfaz gráfica experimental (`JWM`):**
  ```sh
  startx
  ```
* **Ver información del sistema con el logo oficial:**
  ```sh
  fastfetch
  ```
* **Apagar el equipo de forma segura:**
  ```sh
  shutdown
  ```

## Características Principales de Ant Linux
* **Arranque directo:** El gestor de arranque ejecuta el núcleo inmediatamente (`bootall`) sin esperas innecesarias.
* **Seguridad endurecida:** Bloqueo de salida accidental (`exit`) en el usuario estándar para evitar escaladas no autorizadas, mitigaciones activas en kernel y permisos aislados en `/etc/sudoers.d`.
* **Gestión de paquetes:** Incluye el gestor `apk` para instalar utilidades adicionales en memoria.
