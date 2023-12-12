---
title: Acceso a tu VM de estudiante
---

# Acceso a tu VM de estudiante

!!! abstract "Resultados de aprendizaje"

    Al finalizar esta sesión práctica, podrás:

    - acceder a tu VM de estudiante mediante SSH y WinSCP
    - verificar que el software necesario para los ejercicios prácticos esté instalado
    - verificar que tienes acceso a los materiales de ejercicio para este entrenamiento en tu VM local de estudiante

## Introducción

Como parte de las sesiones de entrenamiento local de wis2box, puedes acceder a tu VM personal en la red de entrenamiento local llamada "WIS2-training".

Tu VM de estudiante tiene el siguiente software preinstalado:

- Ubuntu 22.0.4.3 LTS [ubuntu-22.04.3-live-server-amd64.iso](https://releases.ubuntu.com/jammy/ubuntu-22.04.3-live-server-amd64.iso)
- Python 3.10.12
- Docker 24.0.6
- Docker Compose 2.21.0
- Editores de texto: vim, nano

!!! note

    Si deseas ejecutar este entrenamiento fuera de una sesión de entrenamiento local, puedes proporcionar tu propia instancia utilizando cualquier proveedor de nube, por ejemplo:

    - GCP (Google Cloud Platform) instancia VM `e2-medium`
    - AWS (Amazon Web Services) instancia ec2 `t3a.medium`
    - Azure (Microsoft) Máquina Virtual Azure `standard_b2s`

    Selecciona Ubuntu Server 22.0.4 LTS como SO.

    Después de crear tu VM, asegúrate de haber instalado Python, Docker y Docker Compose, como se describe en [dependencias de software de wis2box](https://docs.wis2box.wis.wmo.int/en/latest/user/getting-started.html#software-dependencies).

    El archivo de lanzamiento de wis2box utilizado en este entrenamiento se puede descargar de la siguiente manera:

    ```bash
    wget https://github.com/wmo-im/wis2box/releases/download/1.0b5/wis2box-setup-1.0b5.zip
    unzip wis2box-setup-1.0b5.zip
    ```
    
    Siempre puedes encontrar el archivo de lanzamiento más reciente de 'wis2box-setup' en [https://github.com/wmo-im/wis2box/releases](https://github.com/wmo-im/wis2box/releases).

    El material de ejercicio utilizado en este entrenamiento se puede descargar de la siguiente manera:

    ```bash
    wget https://training.wis2box.wis.wmo.int/exercise-materials.zip
    unzip exercise-materials.zip
    ```

    Los siguientes paquetes adicionales de Python son necesarios para ejecutar los materiales de ejercicio:

    ```bash
    pip3 install minio
    pip3 install pywiscat
    pip3 install pywis-pubsub
    ```

    Si estás utilizando la VM de estudiante proporcionada durante las sesiones locales de entrenamiento de WIS2, el software necesario ya estará instalado.

## Conectarse a tu VM de estudiante en la red de entrenamiento local

Utiliza la siguiente configuración para conectar tu PC a la red Wi-Fi local emitida en la sala durante el entrenamiento de WIS2:

- **SSID: WIS2-training**
- **contraseña: dataismagic!**

Utiliza un cliente SSH para conectarte a tu VM de estudiante usando lo siguiente:

- **Host: (proporcionado durante el entrenamiento presencial)**
- **Puerto: 22**
- **Nombre de usuario: (proporcionado durante el entrenamiento presencial)**
- **Contraseña: wis2training** (contraseña predeterminada para cambiar después de iniciar sesión)

!!! tip
    Contacta a un instructor si no estás seguro sobre el nombre del host/usuario o tienes problemas para conectarte.

Una vez conectado, por favor cambia tu contraseña para asegurar que otros no puedan acceder a tu VM:

```bash
limper@student-vm:~$ passwd
Cambiando la contraseña para testuser.
Contraseña actual:
Nueva contraseña:
Vuelve a escribir la nueva contraseña:
passwd: la contraseña se actualizó correctamente
```