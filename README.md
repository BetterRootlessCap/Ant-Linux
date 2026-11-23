# Ant Linux 1.0 (x86_64)

**Ant Linux** es una distribución Linux ultracompacta y endurecida en seguridad, construida desde cero siguiendo la arquitectura de **Linux From Scratch (LFS)** e integrando únicamente las librerías esenciales (`musl libc` y `apk-tools`) de **Alpine Linux** para lograr una ligereza extrema y arranque directo en memoria RAM.

> **Estado del Proyecto y Notas de Versión:**
> Antes, en la primera versión la interfaz gráfica no funcionaba, tenía una falla donde todos los usuarios eran root y en algunos casos no bootea, pero ya arreglé al menos gran parte porque no va a bootear en todas las computadoras ya que tiene errores aún.

## Requisitos del Sistema

### Requisitos Mínimos
* **CPU:** Procesador de 64 bits (`x86_64`) a 1 GHz
* **RAM:** 256 MB
* **Almacenamiento:** 512 MB (o ejecución directa en RAM desde la ISO Live)
* **GPU:** Gráficos básicos compatibles con VGA o VESA
* **Nota sobre la interfaz gráfica:** Incluye entorno gráfico ligero (`JWM` + `Xorg VESA`) con barra de tareas y fondo de pantalla personalizado (funcionalidad gráfica experimental; en clientes VNC/KeX se recomienda usar el modo *Single-handed* para el puntero).
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
* **Instalar Ant Linux en disco físico o generar imagen `.img` desde el sistema:**
  ```sh
  sudo install 4nt-disk
  ```
* **Iniciar la interfaz gráfica (`JWM`):**
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
* **Instalador integrado (`4nt-disk`):** Permite volcar el sistema e instalar el bootloader Syslinux directamente sobre un disco (`/dev/sda`, `/dev/vda`) o crear un archivo `.img` arrancable.
* **Seguridad endurecida:** Aislamiento real entre usuario estándar (`ant`) y superusuario (`root`), mitigaciones activas en kernel y permisos controlados en `/etc/sudoers.d`.
* **Gestión de paquetes:** Incluye el gestor `apk` para instalar utilidades adicionales en memoria.
