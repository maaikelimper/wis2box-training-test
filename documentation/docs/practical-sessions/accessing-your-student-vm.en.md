---
title: Accessing your student VM
---

# Accessing your student VM

!!! abstract "Learning outcomes"

    By the end of this practical session, you will be able to:

    - access your student VM over SSH and WinSCP
    - verify the required software for the practical exercises is installed
    - verify you have access to exercise materials for this training on your local student VM

## Introduction

As part of locally run wis2box training sessions, you can access your personal student VM on the local training network named "WIS2-training".

Your student VM has the following software pre-installed:

- Ubuntu 22.0.4.3 LTS [ubuntu-22.04.3-live-server-amd64.iso](https://releases.ubuntu.com/jammy/ubuntu-22.04.3-live-server-amd64.iso)
- Python 3.10.12
- Docker 24.0.6
- Docker Compose 2.21.0
- Text editors: vim, nano

!!! note

    If you want to run this training outside of a local training session, you can provide your own instance using any cloud provider, for example:

    - GCP (Google Cloud Platform) VM instance `e2-medium`
    - AWS (Amazon Web Services)  ec2-instance `t3a.medium` 
    - Azure (Microsoft) Azure Virtual Machine `standard_b2s`

    Select Ubuntu Server 22.0.4 LTS as OS.
    
    After creating your VM ensure you have installed python, docker and docker compose, as described at [wis2box-software-dependencies](https://docs.wis2box.wis.wmo.int/en/latest/user/getting-started.html#software-dependencies).
    
    The release archive for wis2box used in this training can be downloaded as follows:

    ```bash
    wget https://github.com/wmo-im/wis2box/releases/download/1.0b5/wis2box-setup-1.0b5.zip
    unzip wis2box-setup-1.0b5.zip
    ```
    
    You can always find the latest 'wis2box-setup' archive at [https://github.com/wmo-im/wis2box/releases](https://github.com/wmo-im/wis2box/releases).

    The exercise material used in this training can be downloaded as follows:

    ```bash
    wget https://maaikelimper.github.io/wis2box-training-test/exercise-materials.zip
    unzip exercise-materials.zip
    ```

    The following additional Python packages are required to run the exercise materials:

    ```bash
    pip3 install minio
    pip3 install pywiscat
    pip3 install pywis-pubsub
    ```

    If you are using the student VM provided during local WIS2 training sessions, the required software will already be installed.

## Connect to your student VM on the local training network

Use the following configuration to connect your PC on the local Wi-Fi broadcasted in the room during WIS2 training:

- **SSID: WIS2-training**
- **password: dataismagic!**

Use an SSH client to connect to your student VM using the following:

- **Host: (provided during in-person training)**
- **Port: 22**
- **Username: (provided during in-person training)**
- **Password: wis2training** (default password to be changed after logging in)

!!! tip
    Contact a trainer if you are unsure about the hostname/username or have issues connecting.

Once connected, please change your password to ensure others cannot access your VM:

```bash
limper@student-vm:~$ passwd
Changing password for testuser.
Current password:
New password:
Retype new password:
passwd: password updated successfully
```

## Verificar versiones de software

Para poder ejecutar wis2box, la VM de estudiante debe tener Python, Docker y Docker Compose preinstalados.

Verificar la versión de Python:
```bash
python3 --version
```
devuelve:
```console
Python 3.10.12
```

Verificar la versión de Docker:
```bash
docker --version
```
devuelve:
```console
Docker version 24.0.6, build ed223bc
```

Verificar la versión de Docker Compose:
```bash
docker compose version
```
devuelve:
```console
Docker Compose version v2.21.0
```

Para asegurarte de que tu usuario pueda ejecutar comandos de Docker, tu usuario ha sido agregado al grupo docker.

Para probar que tu usuario pueda ejecutar 'hello-world' de Docker, ejecuta el siguiente comando:
```bash
docker run hello-world
```

devuelve:
```console
Hello from Docker!
This message shows that your installation appears to be working correctly.
...
```

## Inspeccionar los materiales de ejercicio

Inspeccionar el contenido de tu directorio de inicio; estos son los materiales utilizados como parte del entrenamiento y las sesiones prácticas.

```bash
ls ~/
```
devuelve:
```console
exercise-materials  wis2box-1.0b5
```

Puedes usar WinSCP para conectarte a tu instancia e inspeccionar el contenido de tu directorio de inicio y descargar o cargar archivos entre tu VM y tu PC local.

Abre WinSCP y haz clic en "New Site". Puedes crear una nueva conexión SCP a tu VM de la siguiente manera:

![Captura de pantalla de WinSCP](../assets/img/winscp-student-vm-scp.png)

Haz clic en 'Guardar' y luego 'Iniciar sesión' para conectarte a tu VM.

Y deberías poder ver el siguiente contenido:

![Contenido en WinSCP](../assets/img/winscp-student-vm-exercise-materials.png)

## Conclusión

!!! success "¡Felicidades!"
    En esta sesión práctica, aprendiste cómo:

    - acceder a tu VM de estudiante mediante SSH y WinSCP
    - verificar que el software necesario para los ejercicios prácticos esté instalado
    - verificar que tienes acceso a los materiales de ejercicio para este entrenamiento en tu VM local de estudiante
